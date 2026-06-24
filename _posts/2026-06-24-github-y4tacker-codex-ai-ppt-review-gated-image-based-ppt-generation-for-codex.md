---
title: Codex AI PPT：用可审阅流程生成图片式 PPT
date: 2026-06-24 21:52:19 +0800
categories: [Tech, DevOps]
tags: [Tech, AI, Codex, PPT, Plugin]
image:
  path: /assets/img/posts/2026-06-24-github-y4tacker-codex-ai-ppt-review-gated-image-based-ppt-generation-for-codex/cover.png
  alt: codex-ai-ppt GitHub 项目封面
---

## 核心内容提炼

`codex-ai-ppt` 是一个面向 Codex 的 PPT 生成插件，目标不是把一句模糊需求直接变成幻灯片，而是把选题、风格、结构、页面描述、图片提示词、渲染版本和 PPTX 导出拆成一套可确认、可追踪、可恢复的流程。它特别适合需要先审稿再生成、并且接受“每页一张完整图片”的演示文稿场景。

> 由 GPT-5 Codex 模型总结提炼，观点仅供参考。

## 项目定位

传统 AI PPT 生成常见的问题，是需求还没澄清就开始出片：受众、页数、风格、信息密度和页面重点都可能被模型自行猜测。`codex-ai-ppt` 的设计思路更偏工程化，它把 PPT 生成拆成多个明确阶段，让用户在关键节点确认后再进入下一步。

这个插件会在当前项目下创建 `.codex-ai-ppt/<slug>-NNN/` 运行目录，用一组持久化文件保存中间产物，例如 `CONTRACT.md`、`OUTLINE.md`、`DESCRIPTIONS.md`、`IMAGE_PLAN.md`、`GOAL.md`、`STATE.json`、逐页 prompt、渲染 PNG、历史版本和最终导出的 `deck.pptx`。这些文件既是审阅界面，也是恢复和排错依据。

## 它解决什么问题

`codex-ai-ppt` 主要处理几类 PPT 自动化中的失控点：

- 主题描述过于宽泛，模型直接跳到成稿，导致范围和受众偏离。
- 用户提供了大纲，但生成过程悄悄重排或改写结构。
- 页面文字、视觉提示词和最终图片混在聊天记录里，难以审阅。
- 风格来源不明确，模型只能猜测“商务”“科技”等抽象词。
- 部分页面图片缺失或过期时，仍然可能导出不完整 PPT。
- 修改记录不可追踪，重生成图片覆盖了旧版本。

它的核心选择是“先确认，再生成”。插件先准备可审阅的文本与提示词产物，随后通过 `/goal` 进入图片渲染与导出阶段。

## 安装方式

命令行安装分两步：先添加插件市场源，再安装插件包。

```bash
codex plugin marketplace add Y4tacker/codex-ai-ppt --ref main
codex plugin add codex-ai-ppt@codex-ai-ppt
```

如果之前添加过同名旧市场源，需要先移除再重新添加：

```bash
codex plugin marketplace remove codex-ai-ppt
codex plugin marketplace add Y4tacker/codex-ai-ppt --ref main
codex plugin add codex-ai-ppt@codex-ai-ppt
```

在 Codex App 中，也可以从插件市场入口添加 `Y4tacker/codex-ai-ppt` 作为 marketplace source，然后从 `codex-ai-ppt` marketplace 安装 `codex-ai-ppt`。

## 三种启动模式

插件提供三种用户入口，对应不同成熟度的输入。

`spark` 适合只有一个主题或一句想法的场景。用户可以直接说明主题、受众、页数和风格：

```text
[@codex-ai-ppt](plugin://codex-ai-ppt@codex-ai-ppt) /codex-ai-ppt:spark 做一个关于 AI 历史的 PPT，面向产品团队，8 页，科技现代风格
```

`outline` 适合已经有结构化大纲的场景。插件会尽量保留原始结构，并把它转成后续页面描述与图片计划：

```text
[@codex-ai-ppt](plugin://codex-ai-ppt@codex-ai-ppt) /codex-ai-ppt:outline 根据下面大纲生成图片式 PPT，商务简约风格
# AI 产品路线图
## 背景
- 市场变化
- 用户需求
## 机会
- 场景一
- 场景二
## 计划
- 近期动作
- 风险控制
```

`brief` 适合用户已经给出逐页描述的场景。每页的可见文字和视觉要求都可以直接写清楚：

```text
[@codex-ai-ppt](plugin://codex-ai-ppt@codex-ai-ppt) /codex-ai-ppt:brief 使用科技现代风格，把下面页面描述直接生成 PPT
## page-001 封面
Visible text: AI 产品路线图 2026 Strategy Review
Visual: 深色背景，中央标题，高对比光效，右侧抽象数据流。
```

## 风格闸门

项目强调 Style Source Gate：每次运行必须明确选择一种风格来源。风格可以来自模板图片、PPT 截图、视觉参考图，也可以来自文字风格描述。插件不会在风格含糊时自动套默认风格，而是要求先澄清，避免后续页面全部沿着错误视觉方向生成。

这对 PPT 生成很关键。风格一旦进入逐页图片 prompt，会影响版式、字体气质、配色、信息密度和图形语言。如果入口阶段没有固定风格，后续返工成本会很高。

## 运行目录与状态机

一次典型运行会形成类似结构：

```text
.codex-ai-ppt/<slug>-NNN/
  CONTRACT.md
  OUTLINE.md
  DESCRIPTIONS.md
  IMAGE_PLAN.md
  GOAL.md
  STATE.json
  prompts/page-001.md
  slides/page-001.png
  versions/page-001/v001.png
  exports/deck.pptx
  events.jsonl
  reports/final.md
```

项目状态从 `draft` 开始，依次经过风格确认、合同确认、大纲确认、页面描述确认、图片计划确认、进入 `/goal`、图片生成、导出和完成。页面状态也会从 planned 走到 prompt ready、image generated 和 exported。

这种状态机设计的价值在于：用户可以知道当前停在哪一步，工具也能判断哪些产物已经确认、哪些还不能被当成最终输入。

## 图片式 PPT 的取舍

`codex-ai-ppt` 导出的是 image-only deck：每页 PowerPoint 幻灯片包含一张完整 PNG。优点是最终视觉效果和 GPT Images 或 `image_gen` 渲染结果一致，不需要再用 PowerPoint 形状重建复杂版式。

代价也很明确：导出的 PPT 不是可逐字编辑的文本和形状层。如果团队的核心需求是演讲前快速改字、统一替换图标或继续做精细排版，这种方式并不适合；如果核心需求是快速产出视觉完整、风格统一、可审稿的演示稿，它的路径更直接。

## `/goal` 执行与完成校验

插件初始化结束后，会生成一条可粘贴的 `/goal` 命令，要求 Codex 读取运行目录里的 `GOAL.md`，完成逐页图片渲染、版本记录、PPTX 导出和最终校验。

完成状态不靠主观判断，而是以 `final-status --json` 为准。只有当返回结果包含 `ready: true`，并且存在有效的 `exports/deck.pptx`，运行才算完成。`ready=true` 需要满足以下条件：风格来源有效、页面描述可解析、每页都有 prompt、每页都有 active slide PNG、导出的 PPTX 是有效 zip 包。

这套完成闸门能避免“看似导出了文件，实际缺页或图片状态不一致”的问题。

## 适用场景

`codex-ai-ppt` 更适合这些场景：

- 需要先审阅大纲和页面文案，再进入图片生成。
- PPT 以视觉呈现为主，不要求后续在 PowerPoint 中逐字编辑。
- 希望保留每页图片版本，方便对比和回退。
- 需要把 PPT 生成过程沉淀成目录、状态文件和报告，而不是只留一段聊天记录。
- 使用 Codex 插件体系，并愿意通过 `/goal` 执行最终渲染和导出。

如果只是生成一个可编辑的 Office 模板，或者需要每个文本框、图表、形状都能在 PowerPoint 中独立调整，那么应优先选择基于 PPTX 对象模型的生成方案。

## 小结

从这个项目可以看到一种更稳健的 AI 内容生成思路：不要把复杂交付物压缩成一次性 prompt，而是把它拆成可确认的工程流程。对 PPT 这类同时包含结构、文案、视觉和交付格式的产物来说，`codex-ai-ppt` 的价值不只在“能生成 PPT”，更在于它让生成过程可审阅、可追踪、可验收。

## 原文链接

- [Y4tacker/codex-ai-ppt](https://github.com/Y4tacker/codex-ai-ppt/tree/main#install)
