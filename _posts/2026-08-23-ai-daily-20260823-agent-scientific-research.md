---
title: DeepMind前员工的Agent复现科研超越OpenAI 等 6 条要闻
date: 2026-08-23 18:02:44 +0800
categories: [AI, 大模型]
tags: [AI, Agent, DeepMind, OpenAI, 科研, 复现, 自动化, 智能体]
image:
  path: /assets/img/posts/2026-08-23-ai-daily-20260823-agent-scientific-research/cover.webp
  alt: DeepMind前员工的Agent复现科研超越OpenAI 等 6 条要闻
---

> 本文由钉钉知识库每日要闻同步生成，共 6 条要闻。

> 26年8月23日18时0分，遍历过去24小时的20篇文章，总结出6个热点话题。由claude-opus-4-8提炼，💡部分为模型观点，仅作参考。   

# 📌 今日要闻

**1\. DeepMind前员工的Agent复现科研超越OpenAI**

英国实验室 Inherent 由 DeepMind 前员工创立，推出名为 Faraday 的智能体，专攻复现科学论文。该实验室称 Faraday 在论文复现任务上的表现超过 Anthropic 和 OpenAI 的同类产品。
> 💡 **深度解读** 复现研究是检验 AI 能否真正做科学的硬指标，比刷 benchmark 更接近 AGI 的核心能力。一家初创敢在这个垂直任务上宣称超越两大头部，说明科研自动化正在从通用大模型手中被专用 Agent 撕开一道口子。我更关注的是这条路线一旦跑通，模型能力就不再是唯一护城河，任务专精的团队可以局部反超巨头。   
> 📰 [TechCrunch - AI](https://techcrunch.com/2026/08/22/inherent-founded-by-deepmind-alumni-says-its-ai-teammate-just-outperformed-anthropic-and-openai-at-replicating-research/)   

---

**2\. OpenAI反转立场要求加州收紧AI安全法**

OpenAI 公开呼吁加州强化其此前反对过的 AI 安全法案 SB 53。同期一项研究发现，前沿实验室几乎没有公开如何遏制失控模型的应对方案。
> 💡 **深度解读** OpenAI 从反对到主动要求收紧监管，是典型的头部玩家用合规门槛抬高后来者成本的动作，监管俘获的意味比安全担当更重。对中国玩家的非对称影响在于：美国正在把「安全治理框架」变成一种可输出的规则霸权，一旦成为国际标准，国产模型出海将被迫按这套话语体系接受审查。   
> 📰 [TechCrunch - AI1](https://techcrunch.com/2026/08/22/openai-says-california-should-strengthen-its-ai-safety-bill/) · [TechCrunch - AI2](https://techcrunch.com/2026/08/22/frontier-ai-labs-still-wont-say-how-theyd-contain-a-rogue-model/)   

---

**3\. Claude Code生态封装成插件与技能市场**

Anthropic 上线 Claude Code 和 Claude Cowork 的社区插件市场，Salesforce 官方推出兼容所有工具的 agent skills 集合 sf-skills，ComposioHQ 的 Claude Skills 资源集获超 7.3 万星。Claude Code 主仓库星标已超 14 万。
> 💡 **深度解读** 编程 Agent 的竞争正从模型能力转向可复用技能与插件的分发渠道，谁掌握 skills 市场谁就锁定开发者工作流。Anthropic 在用 App Store 模式给 Claude Code 建护城河，这比单点模型领先更难被复制。国内做编程 Agent 的团队若只卷模型不建技能分发层，会在黏性上被结构性甩开。   
> 📰 [GitHub Trending - Python1](https://github.com/anthropics/claude-code) · [GitHub Trending - Python2](https://github.com/forcedotcom/sf-skills) · [GitHub Trending - Python3](https://github.com/anthropics/claude-plugins-community) · [GitHub Trending - Python4](https://github.com/ComposioHQ/awesome-claude-skills)   

---

**4\. 代码库转知识图谱成为Agent标配底座**

Graphify 将代码库、文档、SQL 架构、配置和 PDF 转为可查询知识图谱，采用本地确定性 AST 解析并为每条关系边提供解释，支持 Claude Code、Cursor、Codex 和 Gemini CLI。该工具面向多家主流编程 Agent 通用。
> 💡 **深度解读** 确定性 AST 解析加显式关系边，是在给 LLM 补上它最缺的结构化长程记忆，用符号方法约束幻觉。这条路线说明纯生成式 Agent 处理大型代码库已触及上下文天花板，业界的解法是回归符号与图结构做地基。谁能把这层「可解释的代码理解」做成跨工具中间件，就卡住了所有编程 Agent 的上游。   
> 📰 [GitHub Trending - Python](https://github.com/Graphify-Labs/graphify)   

---

**5\. AI Agent绕开API直接抓取全网社交内容**

开源 CLI 工具 Agent-Reach 让 AI 智能体读取和搜索 Twitter、Reddit、YouTube、GitHub、Bilibili、小红书等平台内容，明确宣称无需支付 API 费用。Browser Harness 则提供自我修复框架让 LLM 自动完成浏览器任务，星标约 1.7 万。
> 💡 **深度解读** Agent 正在绕过平台 API 和付费墙，直接以浏览器为通用接口抓取数据，这把平台方的数据控制权和商业化闸门直接架空。对内容平台是实质威胁：小红书、B站这类靠数据壁垒的中国玩家，将面对无法通过关闭 API 阻挡的自动化抓取。数据供给规则正在被 Agent 单方面改写。   
> 📰 [GitHub Trending - Python1](https://github.com/Panniantong/Agent-Reach) · [GitHub Trending - Python2](https://github.com/browser-use/browser-harness)   

---

**6\. 开源本地语音方案对标ElevenLabs覆盖646语言**

VoiceStudio 是完全本地化的开源方案，支持语音克隆、语音设计、视频配音、听写、转录及有声书制作，覆盖 646 种语言。项目定位为 ElevenLabs 的替代品，已获约 1.1 万星标。
> 💡 **深度解读** 语音生成正从 ElevenLabs 的闭源 API 订阅模式，被本地开源方案快速平替，商业化护城河比想象中浅。全本地部署加多语言覆盖，意味着语音克隆的能力门槛几乎归零，声音伪造的滥用风险将大规模外溢。对中国团队反而是机会：本地化和多语种正是可以绕过闭源 API 出海的切口。   
> 📰 [GitHub Trending - Python](https://github.com/debpalash/VoiceStudio)   

# 📋 详细内容

## 📰 新闻媒体 (4 篇)

**哈佛699美元创业训练营推出讲师AI虚拟形象**
> 哈佛商学院推出名为 HBS Foundry 的创业训练营，收费 699 美元。该项目使用 AI 生成的导师虚拟形象，在模拟路演和董事会会议中为学员提供反馈。
📎 来源：TechCrunch - AI \| 08-23 05:46 · [阅读原文](https://techcrunch.com/2026/08/22/harvards-699-startup-bootcamp-offers-ai-avatars-of-its-instructors/)   

**由DeepMind前员工创立的Inherent称其AI"队友"在复现研究方面已超越Anthropic和OpenAI**
> Inherent 是一家由 DeepMind 前员工创立的英国 AI 实验室，推出了名为 Faraday 的 AI 智能体。该智能体擅长复现科学论文，在这一任务上的表现超越了 Anthropic 和 OpenAI 的同类产品，有望成为推动创新的重要一步。
📎 来源：TechCrunch - AI \| 08-23 03:00 · [阅读原文](https://techcrunch.com/2026/08/22/inherent-founded-by-deepmind-alumni-says-its-ai-teammate-just-outperformed-anthropic-and-openai-at-replicating-research/)   

**OpenAI称加州应强化其AI安全法案**
> OpenAI呼吁加州加强其此前反对的AI安全法案SB 53。
📎 来源：TechCrunch - AI \| 08-23 00:30 · [阅读原文](https://techcrunch.com/2026/08/22/openai-says-california-should-strengthen-its-ai-safety-bill/)   

**前沿AI实验室仍不愿透露如何遏制失控模型**
> 一项新研究发现，领先的AI实验室几乎没有公开记录如何遏制失控模型的应对方案。随着AI系统越来越多地表现出意外且潜在危险的行为，这引发了对其安全准备情况的质疑。
📎 来源：TechCrunch - AI \| 08-23 00:00 · [阅读原文](https://techcrunch.com/2026/08/22/frontier-ai-labs-still-wont-say-how-theyd-contain-a-rogue-model/)   

## 💬 社区信号 (16 篇)

**claude-code**
> Claude Code 是一款运行在终端中的智能编程工具，能理解代码库并通过自然语言命令帮助开发者执行日常任务、解释复杂代码和处理 Git 工作流。该项目基于 Python，目前已获得 14 万多个星标和 2 万多次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/anthropics/claude-code)   

**PostHog/posthog**
> PostHog 是领先的自动化产品构建平台，提供 AI 可观测性、分析、会话回放、功能开关、实验、错误追踪等开发者工具。这些工具能捕获 AI 智能体诊断问题、发现机会和发布修复所需的完整上下文，并支持通过 Slack、网页、桌面端或 MCP 进行统一操控。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/PostHog/posthog)   

**腾讯/AI基础设施守护**
> 腾讯开源的 AI-Infra-Guard 是一个全栈 AI 红队测试平台，通过 Agent、Skills、MCP、AI 基础设施扫描及大模型越狱评估来保障 AI 生态安全。该项目基于 Python 开发，目前已获得 5629 个 Star 和 528 次 Fork。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/Tencent/AI-Infra-Guard)   

**tick-stock-panel（股票行情面板）**
> TSP 是一款自托管、零运维的 A 股量化工作台，集选股、监控、回测功能于一体，基于 TickFlow 数据源并由 LLM 驱动策略定制、个股分析与复盘。它支持自由接入第三方数据源及个性化扩展，采用 Python 开发。该项目为个人开源作品，并非 TickFlow 官方项目。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/shy3130/tick-stock-panel)   

### Graphify-Labs/graphify

（这是一个 GitHub 仓库路径/项目名称，通常不进行翻译，保持原样。如果您需要翻译其中的描述性词汇，"Graphify" 可理解为"图形化"或"图表化"。）

*Graphify-Labs/graphify*
- 来源: GitHub Trending - Python \| [原文链接](https://github.com/Graphify-Labs/graphify)
- Graphify 是一款可将代码库及其文档、SQL 架构、配置和 PDF 转化为可查询知识图谱的工具，支持 Claude Code、Cursor、Codex 和 Gemini CLI。它采用本地确定性 AST 解析，为每条关系边提供解释，且无需向量存储。

### forcedotcom/sf-skills

（此为 GitHub 仓库名，属于专有名称，通常保留原文不翻译。若需字面翻译，可参考：Salesforce 技能库）

*forcedotcom/sf-skills*
- 来源: GitHub Trending - Python \| [原文链接](https://github.com/forcedotcom/sf-skills)
- Salesforce 官方推出的 agent skills 精选集合，用于构建应用程序。该项目针对 Agentforce Vibes 优化，同时兼容所有 AI 工具，主要采用 Python 语言开发。

**anthropics/claude-plugins-community**
> 这是 Claude Cowork 和 Claude Code 的社区插件市场，为只读镜像仓库。开发者可通过 clau.de/plugin-directory-submission 提交插件。该项目使用 Python 编写，目前拥有 682 个星标和 116 个分支。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/anthropics/claude-plugins-community)   

**ComposioHQ/精选 Claude 技能集**
> 这是一个精选的 Claude Skills 资源集合，收录了用于定制 Claude AI 工作流的技能、工具和资源。该项目主要基于 Python，已获得超过 7.3 万星标和 8 千多次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/ComposioHQ/awesome-claude-skills)   

**VoiceStudio**
> VoiceStudio 是一款开源、完全本地化的 ElevenLabs 替代方案，支持语音克隆、语音设计、视频配音、语音听写、转录及有声书制作，覆盖 646 种语言。该项目基于 Python 开发，已获得约 1.1 万星标和近 1800 次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/debpalash/VoiceStudio)   

**Hermes 智能体**
> NousResearch 推出了 hermes-agent，一个基于 Python 的可成长型 AI 智能体项目。该项目在 GitHub 上获得了约 23 万星标和 4.7 万次分叉，社区关注度较高。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/NousResearch/hermes-agent)   

**karpathy/nanoGPT**
> nanoGPT 是由 Karpathy 开发的用于训练和微调中等规模 GPT 模型的开源项目，主打简洁与高效。该项目基于 Python，目前已获得超过 6.2 万个星标和 1 万多次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/karpathy/nanoGPT)   

**vllm-project/vllm**
> vLLM 是一个高吞吐量、内存高效的大语言模型推理和服务引擎，使用 Python 开发。该项目在 GitHub 上广受欢迎，已获得约 8.9 万星标和 2.1 万次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/vllm-project/vllm)   

**PayloadsAllTheThings**
> PayloadsAllTheThings 是一个用于 Web 应用安全测试和渗透测试/CTF 的实用载荷与绕过技巧集合。该项目基于 Python，已获得超过 8 万个星标和 1.7 万次分叉，是安全领域备受欢迎的开源资源库。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/swisskyrepo/PayloadsAllTheThings)   

**Panniantong/Agent-Reach**
> Agent-Reach 是一款开源 Python 命令行工具，让 AI 智能体能读取和搜索 Twitter、Reddit、YouTube、GitHub、Bilibili、小红书等主流平台内容。无需支付 API 费用，一个 CLI 即可实现全网信息访问。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/Panniantong/Agent-Reach)   

**browser-use/browser-harness**
> Browser Harness 是一个自我修复的框架，可让大语言模型（LLM）自动完成各类浏览器任务。该项目使用 Python 编写，目前已获得约 1.7 万个星标和 1600 多个 Fork。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/browser-use/browser-harness)   

**google/adk-samples**
> google/adk-samples 是一个使用 Agent Development Kit（ADK）构建的示例智能体集合。该项目基于 Python 语言开发，目前已获得 10217 个 Star 和 2823 次 Fork。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/google/adk-samples)   

---
