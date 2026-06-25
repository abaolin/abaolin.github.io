---
title: CodeIsland：在 macOS 灵动岛实时掌控 AI 编程助手状态
date: 2026-06-25 14:28:53 +0800
categories: [Tech, DevOps]
tags: [DevOps, Tech, macOS, AI, Swift, DynamicIsland, ClaudeCode, DeveloperTools]
image:
  path: /assets/img/posts/2026-06-25-codeisland-ai-agent-status-notch/cover.png
  alt: CodeIsland：在 macOS 灵动岛实时掌控 AI 编程助手状态
---

## 核心内容提炼

CodeIsland 是一款驻留在 MacBook 刘海区域的原生工具，通过 Unix socket IPC 实时展示 13 种 AI 编程助手的会话状态、工具调用和权限请求，让你无需切换窗口即可掌控 AI agent 的工作进度，并支持直接审批权限、回答问题，以及同步到 iPhone 和 Apple Watch。

> 由 claude-opus-4-8 模型总结提炼，观点仅供参考。

## CodeIsland 是什么

CodeIsland 把 MacBook 顶部的刘海（Notch）区域变成了一块实时的 AI 编程助手状态面板。它的核心价值在于解决一个高频痛点：**你不再需要频繁切换窗口去确认 Claude 是不是在等你审批，或者 Codex 的任务有没有跑完。**

它通过 Unix socket IPC 连接多达 13 种 AI 编程工具，在一个紧凑的像素风面板里展示：

- 会话状态（session status）
- 工具调用（tool calls）
- 权限请求（permission requests）
- AI 实时回复内容

所有信息都呈现在刘海区域，空闲时自动收起，工作时自动展开。

## 核心功能

CodeIsland 的功能围绕「不打断工作流地掌控 AI agent」展开：

- **刘海原生 UI**：从刘海展开，空闲自动收起，与 macOS 系统观感融为一体
- **支持 13 种 AI 工具**：Claude Code、Codex、Gemini CLI、Cursor、Copilot、Trae/Traecli、Qoder、Factory、CodeBuddy、OpenCode、Kimi Code CLI、Cline、Pi / Oh My Pi
- **实时状态追踪**：活跃会话、工具调用、AI 响应一目了然
- **权限管理**：直接在面板上批准或拒绝工具权限
- **问题应答**：无需离开当前应用即可回复 agent 的提问
- **像素风吉祥物**：每个 AI 工具都有专属的动画角色
- **一键跳转**：点击会话即可跳到对应的终端标签页或 IDE 窗口
- **智能抑制（Smart Suppress）**：基于标签页级别的终端检测，只有当你正盯着对应会话标签页时才抑制通知，而非整个终端应用
- **8-bit 音效**：可选的复古音效提示会话事件
- **自动钩子安装**：自动为所有检测到的 CLI 工具配置 hook，支持自动修复和版本追踪
- **iPhone 与 Apple Watch 联动**：将会话状态镜像到灵动岛、锁屏、待机显示和 Apple Watch
- **双语界面**：中英文自动跟随系统语言
- **多显示器支持**：兼容外接显示器，自动识别带刘海的屏幕

## 安装方式

### Homebrew（推荐）

```bash
brew tap wxtsky/tap
brew install --cask codeisland
```

### 手动下载

1. 进入 Releases 页面
2. 下载 `CodeIsland.dmg`
3. 打开 DMG，把 `CodeIsland.app` 拖到「应用程序」文件夹
4. 启动 CodeIsland，它会自动为所有检测到的 AI 工具安装 hook

> 提示：首次启动时 macOS 可能弹出安全警告。前往「系统设置 → 隐私与安全性」，点击「仍要打开」即可。

### 从源码构建

需要 macOS 14+ 和 Swift 5.9+。

```bash
git clone https://github.com/wxtsky/CodeIsland.git
cd CodeIsland

# 开发模式（debug 构建并启动；Buddy 蓝牙功能需用下方的 .app）
swift build && ./.build/debug/CodeIsland

# 发布模式（通用二进制：Apple Silicon + Intel）
./build.sh
open .build/release/CodeIsland.app
```

## iPhone 与 Apple Watch 联动

配套的 **Code Island Buddy** 已上架 App Store，完全免费且开源，无需账号或外部服务器。

它的工作方式是：

- 当 iPhone 应用打开时，Mac 端通过**本地网络**发布轻量级的会话快照
- 对于灵动岛 Live Activities、Watch 更新等后台刷新场景，则通过**蓝牙**发送紧凑的状态摘要

这样你的 Mac 会话状态就能镜像到 iPhone 的灵动岛、锁屏、待机显示和 Apple Watch 上。配套客户端的源码也在本仓库内，位于 `ios/CodeIslandCompanion` 和 `apple-companion` 目录。

## 工作原理

CodeIsland 的事件流转链路非常清晰：

```text
AI 工具 (Claude/Codex/Gemini/Cursor/...)
  → 触发 hook 事件
  → codeisland-bridge (原生 Swift 二进制, ~86KB)
  → Unix socket → /tmp/codeisland-<uid>.sock
  → CodeIsland 应用接收事件
  → 实时更新 UI
  → （可选）本地同步到 iPhone / Apple Watch
```

核心机制是：CodeIsland 会向每个 AI 工具的配置中注入轻量级 hook。当工具触发事件（会话开始、工具调用、权限请求等）时，hook 通过 Unix socket 发送一条 JSON 消息；CodeIsland 监听该 socket 并即时更新刘海面板。

值得一提的是，对于 OpenCode，它用一个 JS 插件**直接连接 socket**，无需 bridge 二进制中转。

## 设置面板

CodeIsland 提供 7 个标签页的设置面板：

- **通用（General）**：语言、开机自启、显示器选择
- **行为（Behavior）**：自动隐藏、智能抑制、会话清理
- **外观（Appearance）**：面板高度、字体大小、AI 回复行数
- **吉祥物（Mascots）**：预览所有像素风角色及其动画
- **音效（Sound）**：会话事件的 8-bit 音效
- **钩子（Hooks）**：查看 CLI 安装状态，重装或卸载 hook
- **关于（About）**：版本信息与链接

## 系统要求与开源信息

**系统要求：**

- macOS 14.0 (Sonoma) 或更高版本
- 在带刘海的 MacBook 上体验最佳，外接显示器同样可用

**技术栈构成（语言占比）：**

- Swift 83.5%
- Kotlin 6.4%
- C 3.1%
- C++ 2.4%
- Shell 1.8%
- JavaScript 1.2%

本项目灵感来自 @farouqaldori 的 claude-island，感谢其将 AI agent 状态搬进 macOS 刘海的原始创意。项目采用 **MIT 许可证**开源。

## 原文链接

- [阅读原文](https://github.com/wxtsky/CodeIsland)

