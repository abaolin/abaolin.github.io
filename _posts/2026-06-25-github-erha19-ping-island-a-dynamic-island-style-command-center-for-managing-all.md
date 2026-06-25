---
title: Ping Island：把 AI 编程代理状态放进 macOS 菜单栏
date: 2026-06-25 14:01:47 +0800
categories: [Tech, DevOps]
tags: [Tech, AI, macOS, Claude-Code, Codex, Gemini-CLI, DevOps]
image:
  path: /assets/img/posts/2026-06-25-github-erha19-ping-island-a-dynamic-island-style-command-center-for-managing-all/cover.png
  alt: Ping Island：把 AI 编程代理状态放进 macOS 菜单栏
---

## 核心内容提炼

Ping Island 是一个面向 macOS 的菜单栏应用，试图把 Claude Code、Codex、Gemini CLI、Qwen Code、Kimi CLI、OpenCode、Cursor、GitHub Copilot 等 AI 编程代理的会话状态统一收进一个类似 Dynamic Island 的原生界面。它关注的不是再造一个 IDE，而是解决多代理并行工作时最容易打断开发者节奏的问题：审批请求、补充输入、任务完成提醒、错误状态，以及如何快速回到正确的终端、tmux pane 或 IDE 窗口。

> 由 claude-opus-4-8 模型总结提炼，观点仅供参考。

## 项目概览

Ping Island 的定位是 **AI coding session monitor for the macOS menu bar**。它会监听不同 AI 编程工具暴露出来的 hooks、插件事件、会话 transcript 或 app-server 事件，然后在 macOS 菜单栏、刘海区域或浮动 Buddy 中展示统一后的会话状态。

项目 README 给出的核心场景很直接：

- 观察当前正在运行的 AI 编码会话
- 在代理需要权限或输入时及时提醒
- 直接从菜单栏批准、拒绝或回复
- 一键跳回对应的终端、tmux pane 或 IDE 窗口
- 在远程 SSH 主机上的代理活动也回流到本机界面

如果你同时使用 Claude Code、Codex、Gemini CLI 等多个工具，Ping Island 解决的是“我到底哪个窗口里有代理在等我”的问题。

## 安装方式

最简单的安装方式是 Homebrew Cask：

```bash
brew install --cask ping-island
```

也可以从项目官网或 GitHub Releases 下载最新 DMG，然后把 `Ping Island.app` 移到 Applications 文件夹。首次启动时，macOS 可能会要求确认应用来源，或者授予 Accessibility / Apple Events 权限，用于窗口聚焦等功能。

如果从源码构建，需要 macOS 14+ 和可构建 Xcode 项目、Swift 6.1 Prototype package 测试的 Xcode 工具链：

```bash
git clone https://github.com/erha19/ping-island.git
cd ping-island

xcodebuild -project PingIsland.xcodeproj -scheme PingIsland -configuration Debug build
xcodebuild -project PingIsland.xcodeproj -scheme PingIsland -configuration Release build
```

本地测试 unsigned 安装包可运行：

```bash
./scripts/package-unsigned.sh
```

## 主要能力

Ping Island 的功能集中在 AI 代理会话管理，而不是通用通知中心。

**注意力优先的界面。** 默认保持紧凑，只有当会话需要审批、输入、复查或干预时才突出显示，减少对开发流程的持续打扰。

**从刘海或菜单栏直接操作。** 对工具调用请求进行批准或拒绝，回答代理提出的 follow-up 问题，不必在多个终端标签之间来回寻找。

**Claude Code 自动批准。** 对特定会话开启 auto-approve，减少频繁权限确认带来的中断。

**一键返回现场。** 支持回到 iTerm2、Ghostty、Terminal.app、tmux pane 或兼容 VS Code 的 IDE 窗口，适合多个代理、多窗口并行工作。

**SSH 远程主机支持。** 可在远程主机 bootstrap `PingIslandBridge`，重写远端 hooks 指向本机，并把远程 Codex app-server 活动转发回本地 Ping Island UI。

**自定义声音和角色。** 支持 macOS 系统声音、内置 8-bit 音效和本地 sound pack，也可以为不同客户端配置动画 mascot，方便区分多个代理来源。

## 支持的客户端

README 中列出的覆盖面很广，包括：

- Claude Code
- Codex
- Gemini CLI
- Hermes Agent
- Pi Agent
- Qwen Code
- Kimi CLI
- OpenClaw
- OpenCode
- Cursor
- Qoder
- CodeBuddy / WorkBuddy
- GitHub Copilot

其中 Codex 既支持 CLI hook，也支持 live app-server websocket monitor，并在必要时通过 rollout parsing fallback 补充会话状态。Gemini CLI、Qwen Code、Kimi CLI、OpenCode 等工具则分别通过各自配置文件、hook、插件或 transcript 机制接入。

## 工作原理

Ping Island 的数据链路可以概括为：

```text
AI 编程代理
  -> hook / plugin / app-server event
  -> Ping Island monitor + normalization layer
  -> SessionStore
  -> SessionMonitor / NotchViewModel
  -> notch、列表、hover preview、completion popup
```

不同客户端的接入方式并不完全一样：

- Claude-family 工具通过 managed hook files 和内嵌的 `PingIslandBridge` launcher 接入
- Codex 可来自 hook events 或 live Codex app-server websocket monitor
- Gemini CLI hooks 写入 `~/.gemini/settings.json`
- Qwen Code hooks 写入 `~/.qwen/settings.json`
- Kimi CLI hooks 写入 `~/.kimi/config.toml`，并尽量保留无关 TOML 内容
- OpenCode 通过 `~/.config/opencode/plugins/` 下的插件文件和全局配置启用
- 远程 SSH 场景通过远端 bridge 与本地 Ping Island UI 建立事件回流

这类“归一化层”是项目的关键价值：上层 UI 不必理解每个代理的事件差异，只需要消费统一后的会话状态。

## 设置与声音系统

当前设置面板分为四类：

- **General**：开机启动和基础应用行为
- **Display**：刘海屏目标显示器与位置行为
- **Mascot**：客户端 mascot 预览、覆盖配置和动画状态
- **Sound**：事件声音、sound pack 模式和本地导入

声音系统支持三种模式：

- macOS system sounds
- 内置 8-bit 音效
- 本地 OpenPeon / CESP 兼容 sound pack

一个最小 sound pack 包含 `openpeon.json` 和若干 `.wav`、`.mp3` 或 `.ogg` 文件。Ping Island 会把事件映射到 `task.acknowledge`、`input.required`、`task.complete`、`task.error`、`resource.limit` 等类别；如果包里没有对应声音，则回退到用户选择的 macOS 系统声音。

## 测试与发布

项目提供了全仓回归脚本：

```bash
./scripts/test.sh
```

README 中说明该脚本会覆盖 Swift package 测试、Xcode Debug 测试以及相关 UI 测试路径。对于更细粒度的验证，也可以只跑指定 package filter 或 `PingIslandTests` / `PingIslandUITests`。

发布方面，项目包含本地 unsigned 打包脚本，也支持通过 GitHub Actions 创建签名和 notarized release packages。官方 Homebrew Cask 发布说明、Sparkle appcast 和 notarization 流程分别记录在项目文档中。

## 适用场景

Ping Island 更适合下面几类用户：

- 同时使用多个 AI 编程代理，经常忘记哪个会话正在等待输入
- 在 macOS 上大量使用终端、tmux、IDE 与远程 SSH 环境
- 希望把审批、提醒和完成通知从终端标签中抽离出来
- 想要一个开源、原生 macOS 的 AI coding session 监控界面

它不是 AI 代理本身，也不是替代 Claude Code、Codex 或 Cursor 的 IDE，而是把这些工具的“等待我处理”的状态集中起来。

## 原文链接

- [阅读原文](https://github.com/erha19/ping-island)
