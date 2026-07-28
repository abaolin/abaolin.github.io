---
title: 给真正工程师的 AI 技能包：如何让编码智能体产出可靠代码
date: 2026-07-28 10:57:33 +0800
categories: [Tech, DevOps]
tags: [DevOps, Tech, AI, Coding Agents, Claude Code, TDD, Software Design, Domain Modeling]
image:
  path: /assets/img/posts/2026-07-28-skills-for-real-engineers-ai-agents/cover.png
  alt: 给真正工程师的 AI 技能包：如何让编码智能体产出可靠代码
---

## 核心内容提炼

面向 Claude Code、Codex 等编码智能体，一套小巧、可组合、可自定义的技能集，通过对齐意图、构建共享语言、建立反馈回路和重视代码设计四条主线，帮助工程师用 AI 做真正的软件工程，而非无脑 vibe coding。

> 由 claude-opus-4-8 模型总结提炼，观点仅供参考。

## 设计理念：小而可组合，而非绑架流程

开发真实应用很难。GSD、BMAD、Spec-Kit 这类方法试图通过接管整个流程来帮你，但代价是你失去了控制权，流程一旦出 bug 就难以排查。

这套技能走的是相反路线：

- **小巧**——每个技能职责单一，容易理解
- **易改造**——你可以随手 hack，改成自己的样子
- **可组合**——技能之间可以相互调用
- **模型无关**——不绑定任何特定模型

它们基于数十年工程经验凝练而成，目标不是替你思考，而是把软件工程的基本功变成可复用的实践。

## 两种安装方式，两种哲学

**快速开始（30 秒）** 使用 skills.sh 安装器：

```bash
npx skills@latest add mattpocock/skills
```

选择需要的技能和目标智能体，务必勾选 `/setup-matt-pocock-skills`，然后在智能体里运行它，回答几个配置问题（用哪个 issue 追踪器、triage 标签、文档保存位置）即可。

**作为 Claude Code 插件安装** 如果你想要开箱即用、不用自己维护的版本：

```bash
claude plugin marketplace add mattpocock/skills
claude plugin install mattpocock-skills@mattpocock
```

两种方式对应两种理念：

- **skills.sh** 把技能复制进你的项目，你可以随意修改，让它成为你自己的东西
- **插件** 保持只读、始终最新的托管包，你不改它，作者更新时你自动跟进

Codex 及其他遵循 Agent-Skills 标准的环境已被 skills.sh 支持，原生 Codex 插件在路线图上。

## 失败模式一：智能体没做我想要的

软件开发最常见的失败模式是**意图错位**。你以为开发者懂你要什么，等看到成品才发现完全理解错了。在 AI 时代这毫无二致——你和智能体之间存在沟通鸿沟。

> "没有人能确切说清自己想要什么。" —— The Pragmatic Programmer

**解决办法是一场审问（grilling）**，让智能体反过来向你提出大量细节问题，逼你在动手前把想法想清楚：

- `/grill-me`——用于非代码场景
- `/grill-with-docs`——同上，但附带更多能力（见下节）

这是最受欢迎的技能。每次要做变更前都用一次，先对齐再开工。

## 失败模式二：智能体太啰嗦

项目初期，开发者和领域专家往往说着不同的语言。智能体被丢进项目后也是如此——它得自己摸索行话，于是常常用 20 个词表达 1 个词的意思。

> "有了通用语言，开发者之间的对话和代码表达都源自同一个领域模型。" —— Eric Evans, DDD

**解决办法是构建共享语言**——一份帮助智能体解码项目行话的文档（如 `CONTEXT.md`）。对比一下：

- **之前**："当课程某个章节里的一节课被'落实'（即在文件系统中获得位置）时出现了问题"
- **之后**："materialization cascade（物化级联）出问题了"

这份简洁性会在一次次会话中持续回报。它被内建进 `/grill-with-docs`：一边审问你，一边和 AI 共建术语表，并把难以解释的决策记录进 ADR。

共享语言的额外收益：

- 变量、函数、文件命名一致
- 代码库对智能体更易导航
- 智能体思考消耗的 token 更少

## 失败模式三：代码跑不起来

即便你和智能体对目标已经对齐，它仍可能产出垃圾代码。此时该检查你的**反馈回路**了——没有对代码实际运行情况的反馈，智能体就是在盲飞。

> "永远迈小而审慎的步子。反馈的速率就是你的速度上限。" —— The Pragmatic Programmer

必备的反馈回路：静态类型、浏览器访问、自动化测试。其中：

- `/tdd`——推动红-绿-重构循环，先写失败测试再修复，并指导什么是好测试、什么是坏测试
- `/diagnosing-bugs`——把最佳调试实践封装成简单循环：复现 → 最小化 → 假设 → 埋点 → 修复 → 回归测试

## 失败模式四：写成了一团烂泥

智能体能极大加速编码，但也在以前所未有的速度加速**软件熵增**——代码库变得越来越复杂、越来越难改。

> "每天都要投资于系统的设计。" —— Kent Beck
> "最好的模块是深的：通过简单接口暴露大量功能。" —— John Ousterhout

**解决办法是把'关心代码设计'贯穿每一层：**

- `/to-spec`——在写规格前先追问你会动到哪些模块
- `/improve-codebase-architecture`——扫描代码库寻找可深化的机会，救回已经烂成泥的代码，建议每隔几天跑一次

软件工程的基本功比以往任何时候都更重要，这些技能就是把基本功浓缩成可重复的实践。

## 技能参考：用户调用 vs 模型调用

技能按**谁能触发**分为两类：

- **用户调用型**——只有你手动输入才会触发（如 `/grill-me`），职责是编排流程
- **模型调用型**——你可以调用，智能体在合适时也会自动触及，承载可复用的纪律

用户调用型可以调用模型调用型，但永远不会调用另一个用户调用型。

**工程类（用户调用）**：`ask-matt`（技能路由）、`grill-with-docs`、`triage`、`improve-codebase-architecture`、`setup-matt-pocock-skills`、`to-spec`、`to-tickets`、`implement`、`wayfinder`（把超出单次会话的大工程规划为共享地图）。

**工程类（模型调用）**：`prototype`、`diagnosing-bugs`、`research`、`tdd`、`domain-modeling`、`codebase-design`、`code-review`（按标准与规格两个维度并行子代理评审）、`resolving-merge-conflicts`（按意图逐个 hunk 解决冲突，绝不 --abort）。

**生产力类**：`grill-me`、`handoff`（把对话压缩成交接文档）、`teach`（跨多次会话教学）、`writing-great-skills`、`grilling`（grill-me 与 grill-with-docs 背后的复用循环）。

## 原文链接

- [阅读原文](https://github.com/mattpocock/skills)

