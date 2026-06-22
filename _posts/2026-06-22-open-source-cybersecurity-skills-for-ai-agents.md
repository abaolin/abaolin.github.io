---
title: 为 AI 智能体注入资深安全分析师能力：开源网络安全技能库解析
date: 2026-06-22 18:11:29 +0800
categories: [Tech, Security]
tags: [Security, Tech, AI Agent, MITRE ATT&CK, DFIR, NIST, Cybersecurity, agentskills]
image:
  path: /assets/img/posts/2026-06-22-open-source-cybersecurity-skills-for-ai-agents/cover.png
  alt: 为 AI 智能体注入资深安全分析师能力：开源网络安全技能库解析
---

## 核心内容提炼

这是一个开源的网络安全技能库，包含 754 个结构化技能，覆盖 26 个安全领域，并统一映射到 MITRE ATT&CK、NIST CSF 2.0、MITRE ATLAS、D3FEND、NIST AI RMF 及 MITRE F3 六大框架。它遵循 agentskills.io 标准，可让 Claude Code、Copilot、Cursor 等 20 多个 AI 平台的智能体获得资深分析师级别的安全决策能力。

> 由 claude-opus-4-8 模型总结提炼，观点仅供参考。

## 项目定位：把实战经验喂给 AI

一名初级安全分析师知道面对可疑内存转储该跑哪个 Volatility3 插件、哪些 Sigma 规则能抓到 Kerberoasting、以及如何跨三家云厂商界定一次入侵的影响范围。但通用大模型并不具备这些经验——除非你把这些技能交给它。

该项目提供 **754 个结构化网络安全技能**，覆盖 26 个安全领域，每个技能都遵循 agentskills.io 开放标准。它不是脚本集合，也不是检查清单，而是一个面向 AI 智能体从零构建的实战知识库。

> 注意：这是一个独立的社区项目，与 Anthropic PBC 无任何隶属关系。

## 六大框架，统一映射

该库最大的差异化在于：每一个技能都同时映射到六大行业框架，做到「一个技能、六个合规勾选项」。

- **MITRE ATT&CK v19.1**：全部 754 个技能均通过官方 `mitreattack-python` 库验证，覆盖 286 个不同技术，横跨 15 个 Enterprise 战术，并兼顾 ICS 与 Mobile，无任何废弃 ID。
- **NIST CSF 2.0**：对齐全部 22 个类别并引用 106 个子类别，新增的 Govern 函数也被纳入。
- **MITRE ATLAS v5.4**：覆盖 16 个战术、84 个技术，专注 AI/ML 对抗威胁，包括上下文投毒、工具调用滥用、MCP 服务器入侵等智能体攻击向量。
- **MITRE D3FEND v1.3**：NSA 资助的防御技术知识图谱，267 个防御技术分布在 Model、Harden、Detect、Isolate、Deceive、Evict、Restore 七大类。
- **NIST AI RMF 1.0 + GenAI Profile**：定义 Govern/Map/Measure/Manage 四大核心功能，并新增针对生成式 AI 的 12 类风险。
- **MITRE Fight Fraud Framework (F3)**：94 个与欺诈相关的技能，新增 ATT&CK 未涵盖的 Positioning 与 Monetization 两个欺诈专属战术。

## 快速上手

安装方式非常简单，开箱即用：

```bash
# 方式一：npx（推荐）
npx skills add mukul975/Anthropic-Cybersecurity-Skills

# 方式二：Git 克隆
git clone https://github.com/mukul975/Anthropic-Cybersecurity-Skills.git
cd Anthropic-Cybersecurity-Skills
```

该库可立即与 Claude Code、GitHub Copilot、OpenAI Codex CLI、Cursor、Gemini CLI 以及任何兼容 agentskills.io 标准的平台协同工作，无需额外配置。

## 为什么需要它

据 ISC2 统计，2024 年全球网络安全人才缺口高达 480 万个岗位。AI 智能体本可以帮助填补这一缺口，但前提是它们要拥有结构化的领域知识可供调用。

现有的安全工具仓库提供的是字典、Payload 或漏洞利用代码，却没有一个能给 AI 智能体提供资深分析师所遵循的**结构化决策工作流**：何时使用某项技术、需要检查哪些前置条件、如何逐步执行、以及如何验证结果。这正是本项目要填补的空白。

它通过三层结构实现 AI 原生：

- YAML frontmatter——支持亚秒级技能发现；
- 结构化 Markdown——提供逐步执行指引；
- 参考文件——承载深度技术上下文。

## AI 智能体如何使用这些技能

每个技能仅需约 30 个 token 即可扫描其 frontmatter，完整加载工作流则需 500–2000 个 token。这种「渐进式披露」架构让智能体能在单次扫描中检索全部 754 个技能，而不会撑爆上下文窗口。

以一个真实场景为例：

```text
用户提示：分析这个内存转储，查找凭据窃取迹象

智能体的内部流程：
1. 扫描 754 个技能的 frontmatter（每个约 30 token）
   → 通过匹配标签、描述、领域识别出 12 个相关技能
2. 加载排名前 3 的匹配项：
   • performing-memory-forensics-with-volatility3
   • hunting-for-credential-dumping-lsass
   • analyzing-windows-event-logs-for-credential-access
3. 逐步执行 Workflow 章节
   → 运行 Volatility3 插件、检查 LSASS 访问模式、关联事件日志证据
4. 通过 Verification 章节验证结果
   → 确认 IOC，并映射到 ATT&CK T1003（凭据转储）
```

没有这些技能，智能体只能瞎猜命令、漏掉关键步骤；有了它们，智能体便能遵循资深 DFIR 分析师的同款 playbook。

## 技能结构剖析

每个技能都遵循一致的目录结构：

```text
skills/performing-memory-forensics-with-volatility3/
├── SKILL.md          ← 技能定义（YAML frontmatter + Markdown 正文）
├── references/
│   ├── standards.md   ← ATT&CK、ATLAS、D3FEND、NIST 映射
│   └── workflows.md   ← 深度技术流程参考
├── scripts/
│   └── process.py     ← 可运行的辅助脚本
└── assets/
    └── template.md    ← 填好的检查清单与报告模板
```

YAML frontmatter 示例：

```yaml
name: performing-memory-forensics-with-volatility3
description: >-
  使用 Volatility3 框架分析内存转储，提取运行中的进程、
  网络连接、注入代码与恶意软件痕迹。
domain: cybersecurity
subdomain: digital-forensics
tags: [forensics, memory-analysis, volatility3, incident-response, dfir]
atlas_techniques: [AML.T0047]
d3fend_techniques: [D3-MA, D3-PSMD]
nist_ai_rmf: [MEASURE-2.6]
nist_csf: [DE.CM-01, RS.AN-03]
version: "1.2"
author: mukul975
license: Apache-2.0
```

Markdown 正文则固定包含四个章节：**When to Use（触发条件）**、**Prerequisites（前置条件）**、**Workflow（逐步执行）** 与 **Verification（结果验证）**。

## 兼容平台与社区

凡是支持 agentskills.io 标准的平台均可零配置加载这些技能，覆盖范围广泛：

- **AI 代码助手**：Claude Code、GitHub Copilot、Cursor、Windsurf、Cline、Aider、Continue、Amazon Q Developer、JetBrains AI 等；
- **CLI 智能体**：OpenAI Codex CLI、Gemini CLI；
- **自主智能体**：Devin、Replit Agent、SWE-agent、OpenHands；
- **智能体框架与 SDK**：LangChain、CrewAI、AutoGen、Semantic Kernel、Haystack、Vercel AI SDK 以及任何兼容 MCP 的智能体。

项目采用 Apache 2.0 许可证，允许在个人与商业项目中自由使用、修改和分发。社区欢迎贡献：新增技能（如欺诈检测、合规治理等领域最缺人手）、完善框架映射、修复工作流或上报问题，每个 PR 都会在 48 小时内完成技术准确性与标准合规性审查。

## 原文链接

- [阅读原文](https://github.com/mukul975/Anthropic-Cybersecurity-Skills)
