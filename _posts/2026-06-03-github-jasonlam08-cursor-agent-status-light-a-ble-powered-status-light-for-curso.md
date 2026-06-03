---
title: CursorLight：用 ESP32-C3 和 BLE 给 Cursor Agent 做一盏桌面状态灯
date: 2026-06-03 08:37:00 +0800
categories: [Tech, DevOps]
tags: [Tech, Cursor, ESP32, BLE, IoT, Cursor Hooks, AI Agents, Arduino]
image:
  path: /assets/img/posts/2026-06-03-github-jasonlam08-cursor-agent-status-light-a-ble-powered-status-light-for-curso/cover.png
  alt: CursorLight 项目封面图
---

## 核心内容提炼

CursorLight 是一个把红绿灯挂件改造成 AI 编程状态灯的开源项目。它用 ESP32-C3 SuperMini 复用原有三色灯板，通过 BLE 接收电脑端指令，再结合 Cursor Hooks，把 Cursor Agent 的分析、生成、执行、成功、失败、等待人工确认等状态映射成桌面灯效。这个项目的价值不在硬件复杂度，而在于把不可见的 Agent 工作流变成可感知的物理反馈。

> 由 claude-opus-4-8 模型总结提炼，观点仅供参考。

## 项目定位

CursorLight 面向的是使用 Cursor Agent 或类似 AI 编程工具的开发者。AI Agent 在后台分析需求、生成代码、执行命令或等待用户确认时，屏幕上的状态并不总是足够醒目。这个项目用一盏小型红绿灯把这些状态外显出来，让开发者不用一直盯着终端或编辑器，也能知道当前任务处于什么阶段。

项目核心思路很直接：

- 用 **ESP32-C3 SuperMini** 做主控。
- 改造一个红绿灯挂件或玩具交通灯。
- 复用原有红、黄、绿三色灯板。
- 通过 **BLE 蓝牙** 接收电脑端状态指令。
- 通过 **Cursor Hooks** 把 Agent 事件转换成灯效模式。

它不依赖 Wi-Fi，因此不会影响电脑继续连接 5GHz 网络。ESP32-C3 只负责 BLE 通信和灯效控制。

## 状态灯效设计

项目把 AI 编程过程拆成多个可视化状态，每个状态对应一个灯效模式：

| 场景 | mode | 灯效 |
|---|---|---|
| 开机展示 | `demo` | 自动展示多种灯效 |
| AI 正在分析 | `thinking` | 连贯跑马灯 |
| AI 正在生成 | `ai` | 柔和慢速跑马灯 |
| 正在执行命令 | `busy` | 黄灯慢闪 |
| 任务成功 | `success` | 绿灯常亮 |
| 任务失败 | `error` | 红灯快闪 |
| 严重异常或阻塞 | `alarm` | 红黄交替警灯 |
| 等待人工确认 | `yellow` | 黄灯常亮 |
| 展示模式 | `traffic` | 模拟红绿灯 |
| 关闭 | `off` | 全灭 |

这套映射的优点是直观。绿色代表完成，黄色代表处理中或等待，红色代表失败或告警，符合常见交通灯语义。对长时间运行的 Agent 任务来说，这种低成本的环境提示比频繁切回编辑器更自然。

## 硬件方案

硬件部分保持了非常低的门槛，主要物料包括：

- 红绿灯挂件或玩具交通信号灯模型
- ESP32-C3 SuperMini 开发板
- 3 个 220Ω 电阻
- 细导线、热缩管或绝缘胶带
- USB-C 数据线
- 电烙铁、焊锡、镊子、剪线钳
- 可选的万用表

项目当前适配的是**公共正极灯板**。实测灯位和 ESP32 引脚对应关系如下：

| 灯位 | 颜色 | ESP32 引脚 |
|---|---|---|
| L1 | 绿灯 | IO2 |
| L2 | 黄灯 | IO3 |
| L3 | 红灯 | IO4 |

接线方式：

```text
ESP32 3.3V  -> 原灯板 + / 原电池正极
ESP32 IO2   -> 220Ω -> L1 控制点 = 绿灯
ESP32 IO3   -> 220Ω -> L2 控制点 = 黄灯
ESP32 IO4   -> 220Ω -> L3 控制点 = 红灯
```

公共正极逻辑是：

```text
GPIO LOW  = 灯亮
GPIO HIGH = 灯灭
```

固件里已经处理了反相输出，使用者通常不需要手动关心高低电平。

## 固件与 BLE 协议

项目固件文件是：

```text
ESP32_C3_ToyBoard_CommonAnode_BLE_Enhanced_CursorLight.ino
```

固件能力包括：

- BLE 广播名：`CursorLight`
- 通过 BLE GATT 写入字符串控制模式
- 默认开机模式：`demo`
- 支持多种状态灯效
- 内置自动超时，避免灯长时间高亮

BLE 参数：

```text
Device Name: CursorLight
Service UUID: b8b7e001-7a6b-4f4f-9a8b-11c0ffee0001
Mode Characteristic UUID: b8b7e002-7a6b-4f4f-9a8b-11c0ffee0001
```

自动超时规则也做了保护：大多数状态最多运行 5 分钟后进入 `traffic`，`traffic` 最多运行 10 分钟后自动 `off`。这可以避免任务异常结束后状态灯一直保持高亮。

## 烧录与调试流程

烧录流程基于 Arduino IDE：

1. 安装 Arduino IDE 2.x。
2. 在 Boards Manager 中安装 `esp32 by Espressif Systems`。
3. 选择开发板 `ESP32C3 Dev Module`。
4. 打开 `.ino` 固件并上传。
5. 串口监视器使用 `115200` 波特率检查日志。

推荐配置：

| 设置项 | 建议值 |
|---|---|
| USB CDC On Boot | Enabled |
| Upload Speed | 921600 或默认值 |
| Flash Size | 4MB 或默认值 |

如果上传停在 `Connecting...`，可以尝试按住 `BOOT` 后点击上传，开始写入后再松开。

## 电脑端控制脚本

电脑端通过 Python 脚本控制 BLE 灯效：

```text
cursor_light_ble_enhanced.py
```

依赖安装：

```bash
python3 -m pip install bleak
```

手动测试示例：

```bash
python3 cursor_light_ble_enhanced.py demo
python3 cursor_light_ble_enhanced.py thinking
python3 cursor_light_ble_enhanced.py ai
python3 cursor_light_ble_enhanced.py busy
python3 cursor_light_ble_enhanced.py success
python3 cursor_light_ble_enhanced.py error
python3 cursor_light_ble_enhanced.py alarm
python3 cursor_light_ble_enhanced.py off
```

在 macOS 上，如果系统蓝牙已打开但脚本提示 `Bluetooth device is turned off`，通常是终端应用没有蓝牙权限，需要到系统设置里给 Terminal、iTerm、Cursor 或当前终端授权。

## Cursor Hooks 集成

CursorLight 的关键集成点是 Cursor Hooks。推荐目录结构：

```text
~/.cursor/hooks/cursor-light/
├─ install-cursor-light.sh
├─ hooks.json.snippet
├─ agent-light.sh
├─ ble_gate.py
├─ cursor_light_ble_enhanced.py
├─ hook-*.sh
└─ README.md
```

几个文件的职责比较清晰：

- `cursor_light_ble_enhanced.py`：向 ESP32-C3 BLE GATT 特征写入 mode。
- `ble_gate.py`：做防抖和并发去重，避免多个 Hook 同时触发导致灯效乱跳。
- `agent-light.sh`：统一处理 Agent 状态判断和模式切换。
- `hook-*.sh`：不同 Cursor Hook 事件入口。
- `hooks.json.snippet`：Cursor Hooks 配置片段。

推荐状态映射：

| Cursor / 开发场景 | 推荐 mode |
|---|---|
| Agent 开始分析需求 | `thinking` |
| Agent 正在生成或修改代码 | `ai` |
| 执行终端命令、构建、测试 | `busy` |
| 命令成功、构建通过、测试通过 | `success` |
| 普通失败或报错 | `error` |
| 严重阻塞或需要立即处理 | `alarm` |
| 等待用户确认 | `yellow` |
| 关闭灯效 | `off` |

典型流程可以抽象成：

```text
普通任务：thinking -> busy -> success / error
等待确认：thinking -> yellow
严重异常：busy -> alarm
```

## 适合什么场景

这个项目适合三类开发者：

1. **重度使用 Cursor Agent 的开发者**  
   当 Agent 经常在后台执行长任务时，物理状态灯能减少对编辑器状态的频繁检查。

2. **喜欢桌面硬件反馈的工程师**  
   ESP32-C3、BLE、Python 控制脚本和 Cursor Hooks 的组合，足够简单，也有改造空间。

3. **想把 AI 工作流外设化的人**  
   当前很多 AI 编程工具的反馈仍停留在软件界面里。CursorLight 展示了一种方向：让 Agent 状态成为桌面环境的一部分。

## 需要注意的问题

项目涉及硬件改造，使用前需要注意：

- 焊接时只焊裸露焊盘、元件焊脚或电阻焊点，不要焊在阻焊层表面。
- 接 USB 供电前先检查是否短路。
- 如果用于长期使用，建议用热熔胶或 UV 胶固定飞线。
- Windows 目前如果只有 `.sh` Hook 入口，可能需要 Git Bash，或者自行改写为 PowerShell 版本。
- 如果灯效频繁跳变，优先检查 `ble_gate.py` 是否存在，以及 Hook 是否重复注册。

## 原文链接

- [阅读原文](https://github.com/JasonLam08/cursor_agent_status_light/tree/main)
