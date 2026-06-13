---
title: 当前服务器 Docker Compose 服务部署与运维记录
date: 2026-06-13 20:37:04 +0800
categories: [Ops, Docker]
tags: [docker-compose, caddy, vaultwarden, trojan-go, relay-service]
---

这台机器上的长期服务统一放在 `/opt/<service>/` 下，目前主要由两个 Docker Compose 项目承载：

- `/opt/proxy-stack`：统一入口层，运行 Caddy、Vaultwarden、trojan-go。
- `/opt/relay-service`：Claude API 中转服务，运行 relay-service 和 Redis。

外部流量只从 `proxy-stack` 进入。`relay-service` 自己只把服务端口绑定到本机 `127.0.0.1:3000`，公网入口通过 Caddy 的 `api.openicloud.win` 反向代理到容器网络里的 `claude-relay:3000`。

## 当前运行状态

当前 Compose 项目如下：

```text
NAME                STATUS              CONFIG FILES
proxy-stack         running(3)          /opt/proxy-stack/docker-compose.yml
relay-service       running(2)          /opt/relay-service/docker-compose.yml
```

当前运行容器如下：

| 容器 | 镜像 | 状态 | 端口 |
|---|---|---|---|
| `proxy-stack-caddy` | `caddy:2` | running | `80/tcp`、`443/tcp`、`443/udp` 对外开放 |
| `proxy-stack-vaultwarden` | `vaultwarden/server:latest` | running, healthy | 仅容器内 `80/tcp` |
| `proxy-stack-trojan-go` | `alpine:3.20` | running | 仅容器内 `8443/tcp` |
| `relay-service-claude-relay-1` | `weishaw/claude-relay-service:latest` | running, healthy | `127.0.0.1:3000->3000/tcp` |
| `relay-service-redis-1` | `redis:7-alpine` | running, healthy | 仅容器内 `6379/tcp` |

另外有一个停止状态的旧容器 `optimistic_tesla`，不属于当前两个 Compose 项目。后续清理前应先确认它是否还有保留价值。

## 部署拓扑

整体结构可以理解为：

```text
Internet
   |
   | 80 / 443 / 443 UDP
   v
proxy-stack-caddy
   |
   |-- vaultwarden.openicloud.win   -> proxy-stack-vaultwarden:80
   |-- vaultwardenus.openicloud.win -> proxy-stack-vaultwarden:80
   |-- api.openicloud.win          -> relay-service-claude-relay-1:3000
   |-- us2.openicloud.win /usicloud -> proxy-stack-trojan-go:8443
   |-- m.openicloud.win            -> trojan-go:9090
```

`proxy-stack` 是唯一公网入口。新增域名、调整反代、申请证书等都应从 `/opt/proxy-stack/Caddyfile` 入手。

`relay-service` 同时接入两个网络：

- `relay-service_claude-relay-network`：relay 内部网络，连接 `claude-relay` 和 `redis`。
- `proxy-stack_default`：由 `proxy-stack` 创建，`relay-service` 作为 external network 接入，供 Caddy 跨栈反代。

这意味着 `proxy-stack` 必须先启动。否则 `relay-service` 会因为 external 网络 `proxy-stack_default` 不存在而启动失败。

## proxy-stack

目录：

```bash
/opt/proxy-stack
```

配置文件：

```bash
/opt/proxy-stack/docker-compose.yml
/opt/proxy-stack/Caddyfile
```

服务组成：

| 服务 | 作用 | 暴露方式 |
|---|---|---|
| `caddy` | 统一 HTTPS 入口、自动证书、反向代理 | 对外开放 `80`、`443`、`443/udp` |
| `vaultwarden` | Bitwarden 兼容密码管理服务 | 仅暴露给 Caddy |
| `trojan-go` | trojan-go 服务 | 仅暴露给 Caddy |

持久化数据：

| 数据 | 位置 |
|---|---|
| Caddy 证书与运行数据 | Docker volume `proxy-stack_caddy_data` |
| Caddy 配置数据 | Docker volume `proxy-stack_caddy_config` |
| Vaultwarden 数据库和密钥 | `/opt/proxy-stack/vaultwarden-data` |
| trojan-go 二进制、配置和证书 | `/opt/proxy-stack/trojan-go` |

Caddy 当前站点：

| 域名 | 后端 |
|---|---|
| `vaultwarden.openicloud.win` | `vaultwarden:80` |
| `vaultwardenus.openicloud.win` | `vaultwarden:80` |
| `api.openicloud.win` | `claude-relay:3000` |
| `us2.openicloud.win` | `trojan-go:8443`，仅处理 `/usicloud` WebSocket |
| `m.openicloud.win` | `trojan-go:9090` |

## relay-service

目录：

```bash
/opt/relay-service
```

配置文件：

```bash
/opt/relay-service/docker-compose.yml
/opt/relay-service/.env
```

服务组成：

| 服务 | 作用 | 当前状态 |
|---|---|---|
| `claude-relay` | Claude API 中转服务 | 运行中 |
| `redis` | relay-service 的 Redis 数据存储 | 运行中 |
| `redis-commander` | Redis Web 管理界面 | monitoring profile，可选，当前未运行 |
| `prometheus` | 监控采集 | monitoring profile，可选，当前未运行 |
| `grafana` | 监控面板 | monitoring profile，可选，当前未运行 |

持久化数据：

| 数据 | 位置 |
|---|---|
| relay 日志 | `/opt/relay-service/logs` |
| relay 应用数据和证书 | `/opt/relay-service/data` |
| Claude OAuth 凭据 | 宿主机 `/root/.claude` 挂载到容器 `/root/.claude` |
| Redis 数据 | `/opt/relay-service/redis_data` |
| Prometheus 数据 | Docker volume `relay-service_prometheus_data` |
| Grafana 数据 | Docker volume `relay-service_grafana_data` |

注意：`/opt/relay-service/.env` 包含 `JWT_SECRET`、`ENCRYPTION_KEY` 等敏感配置，写文档或贴日志时不要暴露具体值。

## 启动顺序

正常启动必须先启动入口层，再启动依赖入口层网络的 relay：

```bash
cd /opt/proxy-stack
sudo docker compose up -d

cd /opt/relay-service
sudo docker compose up -d
```

如果整机重启后需要手动拉起服务，也按这个顺序执行。

## 关闭顺序

关闭时建议反过来，先停业务依赖方，再停入口层：

```bash
cd /opt/relay-service
sudo docker compose stop

cd /opt/proxy-stack
sudo docker compose stop
```

`stop` 只停止容器进程，容器、网络和数据都保留，适合日常维护和短暂停机。

如果需要移除容器和项目网络，可使用 `down`：

```bash
cd /opt/relay-service
sudo docker compose down

cd /opt/proxy-stack
sudo docker compose down
```

`down` 会删除容器和 Compose 创建的网络，但默认不会删除 named volumes。涉及配置重建、网络重建时可以用它。日常维护优先用 `stop`。

## 重启命令

重启整个 `proxy-stack`：

```bash
cd /opt/proxy-stack
sudo docker compose restart
```

重启整个 `relay-service`：

```bash
cd /opt/relay-service
sudo docker compose restart
```

只重启 Caddy：

```bash
cd /opt/proxy-stack
sudo docker compose restart caddy
```

只重启 Vaultwarden：

```bash
cd /opt/proxy-stack
sudo docker compose restart vaultwarden
```

只重启 trojan-go：

```bash
cd /opt/proxy-stack
sudo docker compose restart trojan-go
```

只重启 Claude relay：

```bash
cd /opt/relay-service
sudo docker compose restart claude-relay
```

只重启 Redis：

```bash
cd /opt/relay-service
sudo docker compose restart redis
```

## 查看状态

查看所有 Compose 项目：

```bash
sudo docker compose ls
```

查看所有容器：

```bash
sudo docker ps
```

查看包含已停止容器在内的完整列表：

```bash
sudo docker ps -a
```

查看 `proxy-stack` 状态：

```bash
cd /opt/proxy-stack
sudo docker compose ps
```

查看 `relay-service` 状态：

```bash
cd /opt/relay-service
sudo docker compose ps
```

不进入目录也可以指定 compose 文件：

```bash
sudo docker compose -f /opt/proxy-stack/docker-compose.yml ps
sudo docker compose -f /opt/relay-service/docker-compose.yml ps
```

## 查看日志

查看 `proxy-stack` 全部日志：

```bash
cd /opt/proxy-stack
sudo docker compose logs -f
```

查看 Caddy 日志：

```bash
cd /opt/proxy-stack
sudo docker compose logs -f caddy
```

查看 Vaultwarden 日志：

```bash
cd /opt/proxy-stack
sudo docker compose logs -f vaultwarden
```

查看 trojan-go 日志：

```bash
cd /opt/proxy-stack
sudo docker compose logs -f trojan-go
```

查看 `relay-service` 全部日志：

```bash
cd /opt/relay-service
sudo docker compose logs -f
```

查看 Claude relay 日志：

```bash
cd /opt/relay-service
sudo docker compose logs -f claude-relay
```

查看 Redis 日志：

```bash
cd /opt/relay-service
sudo docker compose logs -f redis
```

## 配置变更流程

### 修改 Caddy 反代

编辑：

```bash
sudo vim /opt/proxy-stack/Caddyfile
```

检查配置：

```bash
cd /opt/proxy-stack
sudo docker compose exec caddy caddy validate --config /etc/caddy/Caddyfile
```

重载 Caddy：

```bash
cd /opt/proxy-stack
sudo docker compose exec caddy caddy reload --config /etc/caddy/Caddyfile
```

如果重载失败，检查日志：

```bash
cd /opt/proxy-stack
sudo docker compose logs -f caddy
```

新增域名首次访问时，需要等待 Let's Encrypt 签发证书。可在 Caddy 日志中确认是否出现证书签发成功信息。

### 修改 Compose 配置

如果改了 `docker-compose.yml`，通常执行：

```bash
cd /opt/proxy-stack
sudo docker compose up -d
```

或：

```bash
cd /opt/relay-service
sudo docker compose up -d
```

如果需要强制重建容器：

```bash
sudo docker compose up -d --force-recreate
```

如果需要拉取新镜像：

```bash
sudo docker compose pull
sudo docker compose up -d
```

## monitoring profile

`relay-service` 定义了 monitoring profile，包含：

- `redis-commander`
- `prometheus`
- `grafana`

当前这些服务没有运行。需要启用时：

```bash
cd /opt/relay-service
sudo docker compose --profile monitoring up -d
```

启用后默认只绑定本机地址：

| 服务 | 默认端口 |
|---|---|
| Redis Commander | `127.0.0.1:8081` |
| Prometheus | `127.0.0.1:9090` |
| Grafana | `127.0.0.1:3001` |

关闭 monitoring profile：

```bash
cd /opt/relay-service
sudo docker compose --profile monitoring stop redis-commander prometheus grafana
```

## 备份约定

集中备份目录：

```bash
/opt/_backups
```

当前主要内容：

| 目录 | 内容 |
|---|---|
| `/opt/_backups/vaultwarden` | Vaultwarden 迁移或升级前的数据快照 |
| `/opt/_backups/caddy` | Caddyfile 历史备份 |
| `/opt/_backups/home-archive` | 旧 relay 部署副本、旧 compose 文件和管理脚本 |

建议继续保持这个约定：所有 `*.bak`、`*.backup` 或临时迁移快照都放在 `/opt/_backups/<service>/`，不要散落在服务目录里。

## 常见排障

### relay-service 启动失败，提示 external network 不存在

原因通常是 `proxy-stack_default` 不存在。先启动 `proxy-stack`：

```bash
cd /opt/proxy-stack
sudo docker compose up -d
```

再启动 `relay-service`：

```bash
cd /opt/relay-service
sudo docker compose up -d
```

### 域名无法访问

先确认 Caddy 是否运行：

```bash
cd /opt/proxy-stack
sudo docker compose ps caddy
```

再看 Caddy 日志：

```bash
cd /opt/proxy-stack
sudo docker compose logs -f caddy
```

如果是新域名，重点看 DNS 是否已解析到本机，以及 Let's Encrypt 证书是否签发成功。

### Claude relay 不通

先确认容器健康状态：

```bash
cd /opt/relay-service
sudo docker compose ps
```

查看 relay 日志：

```bash
cd /opt/relay-service
sudo docker compose logs -f claude-relay
```

再确认 Caddy 是否能通过跨栈网络访问 `claude-relay:3000`。`relay-service` 必须接入 `proxy-stack_default` 网络。

### Redis 异常

查看 Redis 状态：

```bash
cd /opt/relay-service
sudo docker compose ps redis
```

查看 Redis 日志：

```bash
cd /opt/relay-service
sudo docker compose logs -f redis
```

Redis 当前只在容器网络内部暴露 `6379`，没有映射到公网，这是生产环境更稳妥的方式。

## 运维原则

- 使用 Compose v2 命令：`docker compose`，不要使用旧版 `docker-compose`。
- 外部入口只放在 `proxy-stack`，新增域名优先改 Caddyfile。
- 启动顺序：先 `proxy-stack`，后 `relay-service`。
- 停止顺序：先 `relay-service`，后 `proxy-stack`。
- 日常停机优先用 `stop`，需要重建容器或网络时再用 `down`。
- 不要把 `.env`、OAuth 凭据、Vaultwarden 数据库、证书私钥写进博客或公开仓库。
- 变更前先备份关键配置，备份统一放到 `/opt/_backups/<service>/`。
