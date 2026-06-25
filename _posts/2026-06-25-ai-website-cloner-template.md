---
title: 用 AI 重建网站前端：AI Website Cloner 模板实践
date: 2026-06-25 09:25:18 +0800
categories: [Tech, Frontend]
tags: [Frontend, Tech, AI, Next.js, shadcn, Tailwind, Claude-Code, Web-Scraping]
image:
  path: /assets/img/posts/2026-06-25-ai-website-cloner-template/cover.png
  alt: 用 AI 重建网站前端：AI Website Cloner 模板实践
---

## 核心内容提炼

AI Website Cloner Template 是一个可复用的项目模板，借助 AI 编码代理（推荐 Claude Code）把已有网页逆向重建为干净、现代的 Next.js 代码库。只需指定目标 URL 并运行 /clone-website，代理会自动截图、提取设计令牌与资源、生成组件规格说明，并派发并行构建代理逐区块重建页面。实际使用时应优先面向自己拥有或有授权的网站，避免用于冒充、钓鱼或违反服务条款的复制行为。

> 由 claude-opus-4-8 模型总结提炼，观点仅供参考。

## 项目概览

AI Website Cloner Template 提供了一套自动化流程，把现有网站逆向工程成结构清晰的 Next.js 代码库。它的核心理念很简单：

- 指向一个 URL
- 运行 `/clone-website` 技能
- AI 代理自动检查站点、抽取设计令牌与资源、编写组件规格，并派发并行构建代理重建每个区块

官方推荐搭配 **Claude Code（Opus 4.7）** 获得最佳效果，但也兼容多种 AI 编码代理。

## 快速开始

**重要：** 请使用 GitHub 的 **Use this template** 按钮创建你自己的副本，不要直接克隆模板仓库，也不要把生成的网站作为 PR 提交回模板。

1. 在项目 GitHub 页面点击 **Use this template** → **Create a new repository**，命名并选择公开或私有。

2. 克隆你自己的新仓库到本地：

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-NEW-REPOSITORY.git
cd YOUR-NEW-REPOSITORY
```

3. 安装依赖：

```bash
npm install
```

4. 启动 AI 代理（推荐 Claude Code）：

```bash
claude --chrome
```

5. 运行技能：

```bash
/clone-website <target-url1> [<target-url2> ...]
```

如果使用其他代理，可打开 `AGENTS.md` 查看项目说明，大多数代理会自动识别。

## 前置条件与技术栈

**前置条件：**

- Node.js 24+
- 一个 AI 编码代理

**技术栈：**

- **Next.js 16** — App Router、React 19、TypeScript strict 模式
- **shadcn/ui** — 基于 Radix primitives 与 Tailwind CSS v4
- **Tailwind CSS v4** — 采用 oklch 设计令牌
- **Lucide React** — 默认图标，克隆过程中会被提取的 SVG 替换

## 工作原理

`/clone-website` 技能运行一条多阶段流水线：

1. **侦察（Reconnaissance）** — 截图、提取设计令牌、交互扫描（滚动、点击、悬停、响应式）
2. **基础（Foundation）** — 更新字体、颜色、全局样式，下载所有资源
3. **组件规格（Component Specs）** — 在 `docs/research/components/` 写入详细规格文件，包含精确的计算 CSS 值、状态、行为与内容
4. **并行构建（Parallel Build）** — 在 git worktree 中派发构建代理，每个区块/组件一个
5. **组装与质检（Assembly & QA）** — 合并 worktree、接线页面、与原站做视觉差异比对

关键点在于：每个构建代理都会内联收到完整的组件规格——精确的 `getComputedStyle()` 值、交互模型、多状态内容、响应式断点和资源路径，无需靠猜测。

## 适用与不适用场景

**适用场景：**

- **平台迁移** — 把自己拥有的站点从 WordPress/Webflow/Squarespace 重建为现代 Next.js 代码库
- **源码丢失** — 站点仍在线但仓库不见了、开发者离职或技术栈老旧，借此拿回现代格式的代码
- **学习用途** — 通过真实代码拆解生产级站点如何实现特定布局、动画与响应式行为

**不适用场景：**

- **钓鱼或冒充** — 不得用于欺骗、冒充或任何违法活动
- **盗用他人设计** — Logo、品牌资源和原创文案归属其所有者
- **违反服务条款** — 部分站点明确禁止抓取或复制，请先确认

## 项目结构

```text
src/
  app/            # Next.js 路由
  components/     # React 组件
    ui/           # shadcn/ui primitives
    icons.tsx     # 提取的 SVG 图标
  lib/utils.ts    # cn() 工具函数
  types/          # TypeScript 接口
  hooks/          # 自定义 React Hooks
public/
  images/         # 从目标站下载的图片
  videos/         # 从目标站下载的视频
  seo/            # Favicons、OG 图
docs/
  research/       # 抽取输出与组件规格
  design-references/ # 截图
scripts/
  sync-agent-rules.sh  # 重新生成代理指令文件
  sync-skills.mjs      # 为所有平台重新生成 /clone-website
AGENTS.md         # 代理指令（唯一真相来源）
CLAUDE.md         # Claude Code 配置（导入 AGENTS.md）
GEMINI.md         # Gemini CLI 配置（导入 AGENTS.md）
```

## 常用命令

```bash
npm run dev        # 启动开发服务器
npm run build      # 生产构建
npm run lint       # ESLint 检查
npm run typecheck  # TypeScript 检查
npm run check      # 运行 lint + typecheck + build
```

**使用 Docker：**

```bash
docker compose up app --build  # 构建并运行应用
docker compose up dev --build  # 以开发模式在 3001 端口运行
```

## 多平台支持的维护方式

整个平台支持由两个「唯一真相来源」文件驱动。修改源文件后运行同步脚本，即可自动重新生成各平台的专属副本。能够原生读取源文件的代理无需重新生成。

这种设计让模板维护者只需在一处编辑指令，就能保持 Claude Code、Gemini CLI 等多种代理配置的一致性。项目以 MIT 协议开源。

## 原文链接

- [阅读原文](https://github.com/JCodesMore/ai-website-cloner-template)

