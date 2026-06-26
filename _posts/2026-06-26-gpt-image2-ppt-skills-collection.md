---
title: 用一句话生成专业配图：GPT Image 2 的 32 套 PPT 风格 Skills 实战
date: 2026-06-26 13:43:47 +0800
categories: [Tech, Product]
tags: [Product, Tech, GPT-Image, AIGC, PPT, CodeX, Prompt, Illustration]
image:
  path: /assets/img/posts/2026-06-26-gpt-image2-ppt-skills-collection/cover.png
  alt: 用一句话生成专业配图：GPT Image 2 的 32 套 PPT 风格 Skills 实战
---

## 核心内容提炼

awesome-gpt-image2-ppt-skills 是一套基于 GPT Image 2 的配图 Skills 合集，包含 32 种风格定义，涵盖漫画、工程手稿、白板手绘、PPT 信息图和 Notion 插画等。通过在 CodeX 中安装这些 Skills，用户只需用自然语言描述需求即可生成风格一致、专业级的配图，大幅降低了 AI 配图的门槛。

> 由 claude-opus-4-8 模型总结提炼，观点仅供参考。

## 项目概览

`awesome-gpt-image2-ppt-skills` 是由作者悟鸣维护的一套高质量配图 Skills 合集。它的核心思路是：把每一种视觉风格固化为一个独立的 Skill，每个 Skill 都内置了完整的风格定义与参考规范，开箱即用。

- **适用平台**：CodeX
- **图片模型**：GPT Image 2（通过 `imagegen` / `image_gen` 调用）
- **风格数量**：32 个 Skill
- **默认比例**：多数 PPT 类 Skill 为 16:9

借助这些 Skill，你不需要反复打磨 Prompt，只要一句话描述主题，AI 就能输出风格统一、信息清晰的专业级配图。

## 风格分类一览

32 个 Skill 大致可以归为几个方向，方便按场景挑选：

**手绘与说明图类**
- 漫画式说明图、四格漫画说明图：用简单线条和表情解释概念、流程与前后对比。
- 工程手稿插画：图纸风格的产品设计草图、结构示意。
- 真实办公室白板手绘、白板手绘说明图：摄影感白板与 Marker 线条，适合会议复盘与 Problem → Analysis → Solution。
- 黑板粉笔技术架构图：板书质感的中心放射架构图。

**PPT 信息图类**
- 科技蓝绿、纯白手绘、多色系统架构、绿色产业汇报、金橙商务、暖橙极简、柔紫轻盈等信息图，覆盖方法论拆解、流程步骤、数据概览和 Agent / Skills 工作流。

**商务与汇报 PPT 类**
- 蓝白 3D 科技商务、红白政企培训、红蓝正能量培训、浅蓝鎏金商务、蓝白极简企业介绍、暗色霓虹科技、薄荷水彩、红白项目进度、幻彩柔紫玻璃拟态等，适配企业汇报、项目方案与产品说明。

**教育与中国风类**
- 淡雅新中式简历、秋日校园答辩、青绿通用教育课件、纸纹童趣手绘、清雅中国风课件、暖黄美术课件，覆盖答辩、课件、简历等场景。

**插画角色类**
- 黄色 Notion 女孩、黄色 Notion 大熊猫：官方插画风格的角色配图，适合知识卡片与文章配图。

## 安装方式

**前提条件**：本地已安装 CodeX。

**让 AI 自动安装**：把仓库地址直接发给你的 AI 编程助手，让它自动下载并安装到本地 Skills 目录。

```text
请从这个 GitHub 仓库下载并安装里面的所有 Skills：
https://github.com/chujianyun/awesome-gpt-image2-ppt-skills
```

**只安装单个 Skill**：把 Skill 名称一起告诉 AI 即可。

```text
请从这个 GitHub 仓库只安装 comic-explainer-illustration 这个 Skill：
https://github.com/chujianyun/awesome-gpt-image2-ppt-skills
```

**验证安装**：安装后重启 CodeX，输入 `/skills` 或相关触发词，即可看到已安装的 Skill 列表。

## 使用方法

安装完成后，直接在 CodeX 中用自然语言描述配图需求，就能触发对应的 Skill。无需记忆复杂参数，关键是说清楚**风格 + 主题**。

```text
帮我画一张漫画式说明图，主题是 AI Agent 的工作流程
```

```text
用工程手稿风格画一张产品架构图
```

```text
生成一张科技蓝绿风格的 PPT 信息图，讲解 RAG 的流程
```

```text
用黑板粉笔技术架构图风格讲解：从零散资料到可复用 Skills 的持续优化闭环
```

```text
用黄色 Notion 风格画一张大熊猫配图，内容为：你需要挖掘工作场景，打造并持续优化 Skills
```

同一段文案套用不同 Skill，就能快速生成多套风格的版本，方便对比挑选。

## 价值与适用场景

这套 Skills 合集的本质，是把「设计审美 + Prompt 工程」沉淀为可复用的资产：

- **降低门槛**：非设计背景的人也能产出风格统一的专业配图。
- **风格一致性**：每个 Skill 内置规范，避免同一份 PPT 里配图风格东拼西凑。
- **效率提升**：从写文案到出图，省去反复调 Prompt 的时间成本。
- **场景全覆盖**：产品发布、企业汇报、课程课件、毕业答辩、技术架构讲解、文章配图等都能找到对应风格。

它也很好地诠释了一个理念——**装更多工具解决不了问题，真正有价值的是挖掘工作场景，打造并持续优化可复用的 Skills**。项目以 MIT 协议开源，欢迎按需取用与扩展。

## 原文链接

- [阅读原文](https://github.com/chujianyun/awesome-gpt-image2-ppt-skills)

