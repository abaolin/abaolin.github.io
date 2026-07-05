---
title: 阿里封杀Claude Code，国内大厂去Anthropic化 等 4 条要闻
date: 2026-07-05 17:01:49 +0800
categories: [AI, 大模型]
tags: [AI, Alibaba, Claude, Anthropic, 阿里, 大模型, 去美化, 国产化]
image:
  path: /assets/img/posts/2026-07-05-ai-daily-20260705-alibaba-blocks-claude-code/cover.webp
  alt: 阿里封杀Claude Code，国内大厂去Anthropic化 等 4 条要闻
---

> 本文由钉钉知识库每日要闻同步生成，共 4 条要闻。

> 26年7月5日17时0分，遍历过去24小时的18篇文章，总结出4个热点话题。由claude-opus-4-8提炼，💡部分为模型观点，仅作参考。   

# 📌 今日要闻

**1\. 阿里封杀Claude Code，国内大厂去Anthropic化**

据报道阿里巴巴已将 Claude Code 列为高风险软件，禁止员工使用。此前 Claude Code 相关仓库长期占据 GitHub Trending 榜首，是当前使用最广的终端编程 Agent。
> 💡 **深度解读** 这不是普通的合规封禁，而是国内大厂在编程 Agent 这个高频入口上被迫与 Anthropic 脱钩的信号。Claude 在代码能力上仍是第一梯队，阿里此举意味着国内工程师要么转向 Qwen Coder 自研工具链，要么用国产套壳方案，实际是把最好用的工具从员工手里拿走以换安全边界。对国内玩家是非对称打击——被封的一方在能力上落后，而封的动作又逼着自研加速，短期效率和长期自主之间只能选一个。   
> 📰 [TechCrunch - AI](https://techcrunch.com/2026/07/04/alibaba-reportedly-bans-employees-from-using-claude-code/) · [GitHub Trending - Python](https://github.com/anthropics/claude-code)   

---

**2\. Midjourney反将好莱坞一军，要制片厂自曝AI用量**

Midjourney 在与三家好莱坞制片厂的版权诉讼中，反过来要求原告公开各自内部使用 AI 的详细情况。此前制片厂以侵权为由起诉 Midjourney。
> 💡 **深度解读** 这是版权诉讼战术的一个转折——AI 公司不再单纯防守，而是拿制片厂自身已经在用 AI 的事实来反制「AI 侵害创作」的道德叙事。如果取证成立，好莱坞一边起诉一边偷用的双标会被公开，削弱创作者阵营的法律和舆论基础。这会影响未来所有内容方与生成式 AI 的谈判筹码，训练数据合法性之争正在从「能不能用」转向「谁也别装清白」。   
> 📰 [TechCrunch - AI](https://techcrunch.com/2026/07/04/midjourney-wants-hollywood-studios-to-reveal-the-details-of-their-ai-usage/)   

---

**3\. 谷歌ADK切入Agent开发框架层，抢占标准位**

谷歌开源 ADK-Python，一个代码优先的 Agent 构建、评估与部署工具包，已获超 2 万星。同期 Langflow 达 15 万星、微软 Fabric skills、HuggingFace 语音 Agent 等框架类项目集体上榜。
> 💡 **深度解读** 巨头正把 Agent 竞争从模型层下沉到开发框架层——谁的 SDK 成为开发者默认选择，谁就锁定了上层应用的调用习惯和数据回流。谷歌用 ADK 对标 LangChain 和 OpenAI 的 Agents SDK，本质是抢标准制定权而非单个产品。国内在模型层追得上，但在这种开发者心智和框架事实标准上仍是空白，这是比模型差距更隐蔽也更难补的一层落后。   
> 📰 [GitHub Trending - Python1](https://github.com/google/adk-python) · [GitHub Trending - Python2](https://github.com/langflow-ai/langflow) · [GitHub Trending - Python3](https://github.com/microsoft/skills-for-fabric) · [GitHub Trending - Python4](https://github.com/huggingface/speech-to-speech)   

---

**4\. 开源渗透工具Strix破3.6万星，攻防自动化持续升温**

开源 AI 渗透测试工具 Strix 星标从上次报道的 3.3 万增至 3.64 万，自动发现并修复应用漏洞。同期出现 code-review-graph 等本地代码智能图谱工具，用 MCP 压缩上下文供 AI 只读关键内容。
> 💡 **深度解读** Strix 一周涨三千星，验证了自动化攻防不是概念而是真实刚需，安全团队正在把 AI Agent 当标配工具部署。同时代码图谱类工具的兴起说明一个务实趋势：大家不再指望大 context 硬吞整个仓库，而是用检索加图谱把关键上下文喂给模型，这是 Agent 工程从堆参数转向工程优化的信号。这一层国内跟进较快，属于少数不落后的方向。   
> 📰 [GitHub Trending - Python1](https://github.com/usestrix/strix) · [GitHub Trending - Python2](https://github.com/tirth8205/code-review-graph)   

# 📋 详细内容

## 📰 新闻媒体 (4 篇)

**谷歌新广告设想借助AI撰写《独立宣言》**
> 谷歌发布新广告，设想美国开国元勋在起草《独立宣言》时使用谷歌Workspace和AI辅助的场景。该广告为纪念《独立宣言》签署250周年而制作。
📎 来源：TechCrunch - AI \| 07-05 04:55 · [阅读原文](https://techcrunch.com/2026/07/04/new-google-commercial-imagines-a-declaration-of-independence-written-with-help-from-ai/)   

**米德杰尼要求好莱坞制片厂公开其AI使用细节**
> Midjourney在与三家好莱坞制片厂的法律纠纷中，要求这些制片厂公开其自身使用AI的详细情况。
📎 来源：TechCrunch - AI \| 07-05 02:00 · [阅读原文](https://techcrunch.com/2026/07/04/midjourney-wants-hollywood-studios-to-reveal-the-details-of-their-ai-usage/)   

**阿里巴巴据报禁止员工使用 Claude Code**
> 阿里巴巴据报道已将 Claude Code 列为高风险软件，并禁止员工使用。
📎 来源：TechCrunch - AI \| 07-05 00:32 · [阅读原文](https://techcrunch.com/2026/07/04/alibaba-reportedly-bans-employees-from-using-claude-code/)   

**Mistral AI 是什么？关于这家 OpenAI 竞争对手的全面解读**
> Mistral AI 成立于2023年，是一家提供部分开源AI模型的公司，已获得大量融资，致力于成为OpenAI的有力竞争对手，目标是"让前沿AI惠及每个人"。
📎 来源：TechCrunch - AI \| 07-04 23:51 · [阅读原文](https://techcrunch.com/2026/07/04/what-is-mistral-ai-everything-to-know-about-the-openai-competitor/)   

## 💬 社区信号 (14 篇)

**strix/strix**
> Strix 是一款开源的 AI 渗透测试工具，用于自动发现并修复应用程序中的安全漏洞。该项目使用 Python 编写，在 GitHub 上已获得 36428 个星标和 3689 次 fork。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/usestrix/strix)   

**哈佛前沿/cs249r\_book**
> 哈佛大学开源的《机器学习系统》教材项目，主要使用 Python 语言。该项目在 GitHub 上获得 26660 个星标和 3175 次复刻。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/harvard-edge/cs249r_book)   

**rommapp/romm**
> RomM 是一款美观、功能强大的自托管 ROM 管理与游戏运行工具。它基于 Python 开发，目前在 GitHub 上已获得 10318 颗星和 497 次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/rommapp/romm)   

**agentskills/agentskills**
> Agent Skills 是一个用于定义智能体技能的规范与文档项目，采用 Python 语言开发。该项目在 GitHub 上颇受欢迎，已获得约 2.2 万星标和 1418 次 fork。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/agentskills/agentskills)   

**alirezarezvani/claude-skills**
> 这是一个包含 337 个技能的开源仓库，为 Claude Code、Codex、Gemini CLI、Cursor 等十余种编程助手提供 30\+ 智能体、70\+ 自定义命令和 330\+ 技能。涵盖工程、营销、产品、合规、高管咨询、研究、商业运营及日常生产力等多个领域。该项目主要基于 Python，已获得超过 2 万颗星标。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/alirezarezvani/claude-skills)   

**awesome-claude-code 精选资源**
> 这是一个精选的 Claude Code 优质资源合集，涵盖技能、智能代理、状态栏、开发者工具及插件等内容。该项目在 GitHub 上广受欢迎，已获得约 4.8 万星标和 4221 次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/hesreallyhim/awesome-claude-code)   

**jiji262/douyin-downloader**
> 一款免费的抖音批量下载工具，支持单条及主页批量下载，可去除水印并下载视频、图集、合集与原声音乐。具备进度显示、失败重试、SQLite 去重及浏览器兜底等功能，基于 Python 开发。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/jiji262/douyin-downloader)   

**google/adk-python**
> ADK-Python 是谷歌开源的代码优先型 Python 工具包，用于构建、评估和部署复杂的 AI 智能体，兼具灵活性与可控性。目前已获得超过 2 万个 Star 和 3600 多个 Fork。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/google/adk-python)   

**AI 增强/卓越框架工程**
> 这是一个关于 AI 智能体 harness 工程的精选资源列表，涵盖工具、模式、评估、记忆、MCP、权限、可观测性和编排等主题。该项目基于 Python，已获 2734 星标和 281 次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/ai-boost/awesome-harness-engineering)   

**huggingface/语音到语音**
> HuggingFace 推出的 speech-to-speech 开源项目，可用开源模型构建本地语音智能体。该项目基于 Python，目前已获 5359 星标和 658 次 fork。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/huggingface/speech-to-speech)   

**claude-code**
> Claude Code 是一款运行在终端中的智能编程工具，能理解代码库并通过自然语言命令帮助开发者执行日常任务、解释复杂代码和处理 git 工作流。该项目使用 Python 编写，已获得 13.6 万星标和 2.1 万次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/anthropics/claude-code)   

**Fabric 技能**
> 微软开源的 skills-for-fabric 项目，提供技能集和 MCP 系统，让 CLI、VSCode、Claude 等工具的用户能够操作 Microsoft Fabric。项目基于 Python 开发，目前已获得 724 星和 195 次 fork。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/microsoft/skills-for-fabric)   

**langflow-ai/langflow**
> Langflow 是一款用 Python 开发的强大工具，用于构建和部署 AI 智能体及工作流。该项目在 GitHub 上广受欢迎，已获得超过 15 万颗星标和 9400 多次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/langflow-ai/langflow)   

**tirth8205/代码审查图谱**
> 这是一个本地优先的代码智能图谱工具，支持MCP和CLI，通过构建代码库的持久化映射，让AI编程工具只读取关键内容。它在代码审查和大型仓库工作流中实现了经过基准测试的上下文缩减。该项目使用Python开发。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/tirth8205/code-review-graph)   

---
