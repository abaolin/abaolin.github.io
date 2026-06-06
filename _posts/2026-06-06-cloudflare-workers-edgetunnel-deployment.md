---
title: 基于 Cloudflare Workers 部署 EdgeTunnel：搭建轻量级代理服务实战
date: 2026-06-06 15:53:43 +0800
categories: [Tech, Cloud]
tags: [Cloud, Tech, Cloudflare, Workers, Serverless, VLESS, Proxy, EdgeComputing]
---

## 核心内容提炼

EdgeTunnel 是运行在 Cloudflare Workers/Pages 上的轻量级代理服务方案，借助边缘网络免服务器部署。本文介绍其部署流程、核心环境变量配置、优选 IP 与订阅功能，以及常见的安全与维护注意事项。

> 由 claude-opus-4-8 模型总结提炼，观点仅供参考。

## 项目概述

EdgeTunnel 是一个基于 Cloudflare 边缘计算平台（Workers 与 Pages）构建的轻量级网络隧道方案。它的核心思路是利用 Cloudflare 遍布全球的边缘节点，将代理流量通过 Worker 脚本进行转发，从而无需自行租用和维护服务器即可获得一个可用的代理出口。

主要特点包括：

- **零服务器成本**：依托 Cloudflare 免费额度即可运行，适合个人轻量使用。
- **全球边缘加速**：借助 Cloudflare 的 Anycast 网络，连接延迟较低。
- **部署方式灵活**：支持 Workers 与 Pages 两种部署形态。
- **支持优选 IP 与订阅**：可结合优选域名/IP 提升连接质量，并生成可导入客户端的订阅链接。

## 部署方式：Workers 与 Pages

EdgeTunnel 提供两种主流部署路径，用户可根据习惯选择：

**1. Workers 部署**

- 登录 Cloudflare 控制台，进入 `Workers & Pages`。
- 创建一个新的 Worker，将项目的 `_worker.js` 脚本内容粘贴进编辑器并部署。
- 在 Worker 的设置中绑定自定义域名（推荐），避免直接使用 `workers.dev` 默认域名被限制。

**2. Pages 部署**

- 通过 GitHub 仓库 Fork 项目后，在 Cloudflare Pages 中连接该仓库。
- 设置构建输出，将 `_worker.js` 作为入口文件部署。
- Pages 部署更适合需要持续与上游仓库同步更新的场景。

两种方式本质相同，区别在于管理与更新的便利性：Pages 便于 Git 集成与版本管理，Workers 则配置更直接。

## 核心环境变量配置

EdgeTunnel 的灵活性主要来自一系列环境变量，常见的关键配置如下：

| 变量名 | 作用 |
|--------|------|
| `UUID` | 用户身份标识，客户端连接时需保持一致 |
| `PROXYIP` | 反代 IP，用于解决部分网站无法直连的问题 |
| `SUB` | 订阅生成器地址，用于聚合节点信息 |
| `SUBAPI` | 订阅转换后端 API |
| `SUBCONFIG` | 订阅转换使用的配置文件 |
| `ADD` / `ADDAPI` | 优选 IP/域名列表或获取地址 |
| `SOCKS5` | 配置 SOCKS5 出口代理（可选） |

配置建议：

- `UUID` 务必使用随机生成的强标识，避免被他人盗用。
- `PROXYIP` 在访问受限站点时尤为关键，可使用社区维护的可用反代地址。
- 通过 `ADDAPI` 接入优选 IP 接口，可动态获取低延迟节点。

## 优选 IP 与订阅功能

Cloudflare 的默认 IP 在不同网络环境下质量参差不齐，因此**优选 IP**是提升体验的核心环节。

- **优选 IP/域名**：通过 `ADD`（静态列表）或 `ADDAPI`（动态接口）填入经过测速筛选的优质 IP，使客户端连接更稳定。
- **订阅链接生成**：访问 `https://你的域名/你的UUID` 即可获取订阅地址，可直接导入主流客户端（如 v2rayN、Clash 等）。
- **订阅转换**：结合 `SUB`、`SUBAPI`、`SUBCONFIG` 可将节点转换为不同客户端所需格式，实现一键导入。

实践中，建议定期更新优选 IP 列表，以应对 Cloudflare IP 段质量的动态变化。

## 安全与维护注意事项

在使用 EdgeTunnel 时，需要注意以下几点：

- **保护 UUID**：UUID 相当于访问凭证，泄露后可能被他人滥用你的服务，应妥善保管并定期更换。
- **遵守服务条款**：Cloudflare 免费额度有使用限制，大流量或商用用途可能触发风控甚至封禁。
- **自定义域名优先**：默认的 `workers.dev` 域名在部分地区易被屏蔽，绑定自有域名更稳定。
- **及时更新脚本**：项目持续迭代，定期同步最新的 `_worker.js` 可获得功能改进与问题修复。
- **合规使用**：请在所在地区法律法规允许的范围内使用，仅作学习与技术研究用途。

## 总结

EdgeTunnel 充分利用了 Cloudflare Workers/Pages 的边缘计算能力，提供了一种**免服务器、低成本、易部署**的轻量代理方案。通过合理配置 UUID、反代 IP、优选 IP 与订阅转换，可以在个人场景下获得不错的连接体验。

对技术爱好者而言，它也是理解 Serverless 与边缘网络转发机制的一个实用案例。但需牢记：任何此类工具都应在合法合规的前提下使用，并注意妥善保护好身份凭证与遵守平台规则。

## 原文链接

- [阅读原文](https://github.com/cmliu/edgetunnel/blob/main/README.md)

