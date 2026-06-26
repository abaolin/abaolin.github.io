---
title: Prompt as Code：把 GPT-Image2 提示词工程化为可复用资产
date: 2026-06-26 13:46:48 +0800
categories: [Tech, DevOps]
tags: [DevOps, Tech, GPT-Image2, Prompt Engineering, AI, Agent Skill, Automation, Template]
image:
  path: /assets/img/posts/2026-06-26-gpt-image2-prompt-as-code/cover.png
  alt: Prompt as Code：把 GPT-Image2 提示词工程化为可复用资产
---

## 核心内容提炼

当 AI 画图从“能不能出图”升级为“能不能稳定、可控、可复用地出图”，单纯堆砌提示词已经不够。该项目通过对 470+ 案例做逆向工程，提炼出 20+ 套工业级模板，核心思路是把散文式提示词压缩成结构化协议（Prompt-as-Code），并以原子化 Schema、Agent Skill 和可视化平台的形式，让提示词真正接入 Agent 与自动化生产流程。

> 由 claude-opus-4-8 模型总结提炼，观点仅供参考。

## 项目愿景：从案例堆叠到结构化协议

GPT-Image2 全量开放后，行业关注点发生了转移：不再纠结“能不能出图”，而是追求**稳定、可控、可复用**的批量生产能力。

这个项目的目标只有一个——把“散文式提示词”压缩成“结构化协议”。当你需要批量出图、搭建模板系统或接入生产流程时，结构化整理远比单纯收集案例更有价值。

核心设计原则：

- 🧱 **原子化 Schema**：把主体、光影、材质、排版等视觉要素拆成可组合的组件
- ⚙️ **工作流友好**：面向 Agent、脚本和自动化系统，而非只供人肉复制粘贴
- 🧬 **结构化控制**：尽可能提升版式、文案、信息层级的可控性

## 分类概览：从画册到模板

使用方法分两步：先看案例画册快速定位你想要的视觉类型，再看提示词模板，把对应类型拆解成可复用结构。

案例画册按场景分类，覆盖了从产品到艺术的主要需求：

| 分类 | 数量 | 分类 | 数量 |
|------|------|------|------|
| UI 与界面 | 73 | 海报与排版 | 80 |
| 图表与信息可视化 | 52 | 摄影与写实 | 73 |
| 插画与艺术 | 53 | 商品与电商 | 38 |
| 品牌与标志 | 25 | 人物与角色 | 25 |
| 场景与叙事 | 20 | 历史与古风 | 16 |
| 建筑与空间 | 12 | 文档与出版物 | 10 |

每个案例类型都对应着可拆解的提示词模板，把视觉风格转化为可填充的变量结构。

## Agent Skill：让 Agent 直接调用风格库

仓库提供了 Agent Skill，用同一份风格库数据为 Claude Code、Codex 等 Agent 选择 GPT-Image2 的模板、分类、风格和场景标签，实现真正的 Prompt-as-Code 落地。

**一键安装到指定 Agent**（推荐 Claude Code、Codex、Cursor 等）：

```bash
npx skills add freestylefly/awesome-gpt-image-2 \
  --skill gpt-image-2-style-library \
  --agent claude-code codex --global --yes --copy
```

**安装到所有支持的本地 Agent**：

```bash
npx skills add freestylefly/awesome-gpt-image-2 --global --all --copy
```

**Claude Code 插件市场**：

```bash
/plugin marketplace add freestylefly/awesome-gpt-image-2
/plugin install gpt-image-2-style-library@awesome-gpt-image-2
```

安装完成后即可这样调用：

```text
使用 gpt-image-2-style-library 技能，帮我生成介绍 Codex 的信息图
```

## npm CLI 安装方式

如果你更习惯 npm，可以先安装 CLI，再同步到本地 Agent 技能目录：

```bash
npm install -g gpt-image-2-style-library
gpt-image-2-style-library install all
```

不想全局安装也可以直接运行：

```bash
npx gpt-image-2-style-library install all
```

`install all` 会写入 Codex 和 Claude Code 常用的本地技能目录，包括 `~/.codex/skills`、`~/.claude/skills`、`~/.agents/skills`。安装完成后记得**重启 Agent 会话**。

本地源码开发时：

```bash
npm run generate:style-skill
npm run install:skill
```

Skill 源码位于 `agents/skills/gpt-image-2-style-library`，生成索引来自 `data/style-library.json`——网站和 Agent 工作流共用这一份风格库，保证数据一致性。

## 可视化网站与生成测试

配套的可视化网站支持产品化方式浏览案例：查看大图、复制完整 Prompt、按风格或场景筛选、登录后测试生成，并可快速跳回 GitHub 源案例。

网站的登录与生成测试能力，底层使用 **Supabase Auth + Supabase Postgres**，并通过 **Vercel Function** 代理 GPT Image 2 API。

部署时需要在 Vercel 配置一系列环境变量，关键项包括：

```text
VITE_SUPABASE_URL=
VITE_SUPABASE_ANON_KEY=
SUPABASE_SERVICE_ROLE_KEY=   # 仅放服务端环境
CIYUAN_API_KEY=
STRIPE_SECRET_KEY=           # 仅放服务端环境
STRIPE_WEBHOOK_SECRET=       # 仅放服务端环境
```

几个部署要点：

- 依次应用 `supabase/migrations` 下的多个 SQL 迁移，分别添加用户积分、会员计费、账户用量统计、定价看板和案例收藏等表与逻辑。
- 在 Supabase Auth Redirect URLs 中加入生产域名和本地开发地址（如 `http://127.0.0.1:5173`）。
- 配置 Google OAuth Provider，如需强制 Google 登录可关闭 Email Provider。
- 配置 Stripe Checkout Webhook，订阅 `checkout.session.completed`、`invoice.payment_succeeded`、`customer.subscription.updated`、`customer.subscription.deleted` 等事件。
- 创建 GA4 property 并通过 `npm run ga4:oauth` 完成授权，将刷新令牌作为敏感环境变量加入 Vercel。

**安全提醒**：`SUPABASE_SERVICE_ROLE_KEY`、`STRIPE_SECRET_KEY` 等敏感密钥只应放在服务端环境变量中，绝不要暴露到前端。

## 怎么用好这个库

高效使用这个提示词资产库，推荐三步走：

1. **定型**：先在精选案例里确定你要模仿的输出类型。
2. **抄结构**：再去完整画廊找相近案例，**抄结构而不是只抄风格词**——结构才是可复用的核心。
3. **填变量**：最后回到模板页，把你的业务变量填进通用模板或 JSON 模板。

这套流程的本质，是把每次出图都当作一次“调用结构化协议”，而非一次性灵感发挥，从而让结果稳定、可控、可批量。

## 声明与开源协议

项目在整理与研究过程中参考并使用了 YouMind 与 OpenNana 的公开提示词库内容，仅用于学习、归纳与方法论研究，相关内容版权归原作者或原平台所有。

关于来源与合规：

- 尽力保留原始来源，包括作者主页、原帖链接与原仓库链接。
- 涉及第三方内容时遵循来源仓库声明、CC BY 4.0 等许可及平台规则。
- 原作者或权利人若认为某条内容不应展示，可发起 Issue 并附链接，核验后将快速下架。
- **不保证第三方内容可用于商业用途**，商业使用前请自行取得原权利方授权。

项目本身采用 **MIT License** 开源，可在保留许可声明的前提下自由使用、修改、分发与二次开发。

## 原文链接

- [阅读原文](https://github.com/freestylefly/awesome-gpt-image-2/blob/main/README.zh-CN.md)

