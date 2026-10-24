---
title: "OpenAI停止用实时互联网数据训练前沿模型 等 6 条要闻"
date: 2026-10-24 17:02:06 +0800
categories: ["AI", "大模型"]
tags: ["AI", "OpenAI", "训练数据", "frontier", "LLM", "互联网", "model", "数据"]
image:
  path: /assets/img/posts/2026-10-24-ai-daily-20261024-openai-realtime-web-data/cover.png
  alt: "OpenAI停止用实时互联网数据训练前沿模型 等 6 条要闻"
---

> 本文由钉钉知识库每日要闻同步生成，共 6 条要闻。

> 26年10月24日17时0分，遍历过去24小时的17篇文章，总结出6个热点话题。由claude-opus-4-8提炼，💡部分为模型观点，仅作参考。   

# 📌 今日要闻

**1\. OpenAI停止用实时互联网数据训练前沿模型**

OpenAI 宣布不再使用实时互联网数据训练其前沿模型，理由是存在「重大风险」。此前数周，该公司一名工程师曾公开表示这种做法行不通。
> 💡 **深度解读** 这是数据供给侧的实质转向，不是口号。前沿实验室开始主动切断实时网络数据，意味着数据投毒、对抗样本注入已成为训练安全的一级威胁，攻防对抗从推理端前移到了训练端。对中国玩家的非对称影响在于：当头部实验室转向高质量封闭语料和合成数据时，依赖公开爬取数据追赶的路径会越来越窄，数据壁垒正在从「量」转向「可信来源」。   
> 📰 [TechCrunch - AI](https://techcrunch.com/2026/10/23/openai-says-it-will-no-longer-train-its-ai-models-on-the-live-internet-citing-significant-risks/)   

---

**2\. Anthropic的Claude技能被改造成攻击性安全武器库**

GitHub 出现 claude-red 项目，以结构化 SKILL.md 文件为 Claude 注入 SQL 注入、shellcode、EDR 规避等攻击面方法论。另有 Graphify 等多个项目将 Claude 技能系统作为底座扩展能力。
> 💡 **深度解读** Claude 技能系统正在被社区当作可插拔的能力分发层来用，这比模型本身的能力更值得我盯。攻击性安全技能库的出现说明技能机制的双刃性已经落地——任何人都能把专家级攻击方法论打包成技能分发给 agent。结合近日中国黑客用 AI 代理攻破数千客户的事件，模型厂商的安全护城河正在被自己开放的扩展接口反噬。   
> 📰 [GitHub Trending - Python1](https://github.com/SnailSploit/Claude-Red) · [GitHub Trending - Python2](https://github.com/Graphify-Labs/graphify)   

---

**3\. Claude技能成为知识工作的事实标准分发格式**

GitHub Python 榜出现多个围绕 Claude 技能的项目：book-to-skill 将技术书籍 PDF 转为 Claude Code 技能（3.6 万星），claude-howto 可视化指南（4.4 万星），Graphify 把代码库转为可查询知识图谱并同时支持 Claude Code、Cursor、Codex、Gemini CLI。
> 💡 **深度解读** SKILL.md 正在成为跨 agent 的通用能力封装格式，这是 Anthropic 没大声宣传但已经赢下的一局。当「把一本书变成技能」「把代码库变成图谱技能」成为社区默认动作，知识的组织单元正从 prompt、RAG 文档迁移到结构化技能文件。谁掌握技能格式标准，谁就掌握了下一层 agent 分发入口——这是比模型跑分更隐蔽的平台权力。   
> 📰 [GitHub Trending - Python1](https://github.com/virgiliojr94/book-to-skill) · [GitHub Trending - Python2](https://github.com/luongnv89/claude-howto) · [GitHub Trending - Python3](https://github.com/Graphify-Labs/graphify)   

---

**4\. 多智能体交易框架TradingAgents获11万星，agent进入垂直深水区**

TradingAgents 是基于多智能体大语言模型的金融交易框架，GitHub 获约 11.3 万星、2.2 万 fork，是本次榜单星标最高的 AI 项目。
> 💡 **深度解读** 11 万星的量级说明开发者对「多 agent 做金融决策」有真实需求，而非玩具热度。金融是对准确性和可审计性要求最高的领域之一，社区愿意押注多 agent 架构，意味着市场判断单模型的推理可靠性不足以独立承担高风险决策，必须靠 agent 间的分工制衡来逼近可用。这条路线如果被验证，会率先在量化、风控等场景落地，而不是通用助手。   
> 📰 [GitHub Trending - Python](https://github.com/TauricResearch/TradingAgents)   

---

**5\. 无分词器TTS路线VoxCPM验证，中国团队在语音端领跑**

VoxCPM2 是无需分词器（Tokenizer-Free）的多语言 TTS 工具，支持语音设计和声音克隆，GitHub 超 4 万星。同期百度 Unlimited-OCR 主打一次性长文档解析，获 2.8 万星。
> 💡 **深度解读** 无分词器 TTS 直接从原始信号建模、绕开文本 token 中间层，这条路线在社区获得 4 万星的认可，说明端到端语音生成的架构范式正在收敛。值得我注意的是，VoxCPM 与百度 OCR 都是中国团队主导的开源项目且热度不低——在多模态的感知层（语音、文档解析）上，中国玩家的工程落地和开源影响力并不落后于美国，差距主要集中在前沿大模型的推理能力上。   
> 📰 [GitHub Trending - Python1](https://github.com/OpenBMB/VoxCPM) · [GitHub Trending - Python2](https://github.com/baidu/Unlimited-OCR)   

---

**6\. OpenAI为10亿用户重构存储，读取提速12倍**

OpenAI 通过多租户架构、全球缓存和 Azure Cosmos DB 扩展 Habitat 存储系统，使 ChatGPT 读取速度提升 12 倍，支撑超过 10 亿用户的在线存储。
> 💡 **深度解读** 这篇工程博客的真正信号不是技术细节，而是「10 亿用户在线存储」这个确认过的规模数字。它意味着 ChatGPT 已经不是对话产品，而是一个承载用户长期记忆和状态的个人数据平台——存储层的重投入是在为「有记忆的个人 agent」铺地基。对手要追赶的不只是模型，还有这套支撑 10 亿级有状态会话的基础设施，这是比参数量更难复制的壁垒。   
> 📰 [OpenAI Blog](https://openai.com/index/scaling-storage-one-billion-users-part-two)   

# 📋 详细内容

## 🏢 官方动态 (2 篇)

**快速扩展在线存储以服务超过10亿ChatGPT用户（第二部分）**
> OpenAI 通过可靠的多租户架构、全球缓存和 Azure Cosmos DB 扩展了 Habitat 存储系统。这些改进使 ChatGPT 的读取速度提升了 12 倍。该方案支撑了超过 10 亿 ChatGPT 用户的在线存储需求。
📎 来源：OpenAI Blog \| 10-24 01:00 · [阅读原文](https://openai.com/index/scaling-storage-one-billion-users-part-two)   

**保护我们的前沿模型训练环境**
> OpenAI 介绍了如何加强前沿模型训练与评估的安全防护措施。这些措施包括使用离线隔离环境以及开展高算力的红队测试。
📎 来源：OpenAI Blog \| 10-23 18:00 · [阅读原文](https://openai.com/index/securing-our-frontier-model-training-environment)   

## 📰 新闻媒体 (3 篇)

**OpenAI称将不再使用实时互联网训练AI模型，理由是存在"重大风险"**
> OpenAI宣布将不再使用实时互联网数据训练其前沿AI模型，理由是存在"重大风险"。这一决定出台仅数周前，该公司一名工程师还曾表示这种做法行不通。
📎 来源：TechCrunch - AI \| 10-24 07:05 · [阅读原文](https://techcrunch.com/2026/10/23/openai-says-it-will-no-longer-train-its-ai-models-on-the-live-internet-citing-significant-risks/)   

**圣诞最火玩具？英伟达CEO把玩萌趣Microduck机器人，销量破2万**
> 英伟达CEO黄仁勋展示了一款名为Microduck的可爱机器人，它能跺脚、发出类似R2-D2的声音，并通过语音指令完成坐下、装睡和翻跟头等动作。该产品已售出2万台，成为今年圣诞节的热门玩具。
📎 来源：TechCrunch - AI \| 10-24 05:59 · [阅读原文](https://techcrunch.com/2026/10/23/hottest-toy-for-christmas-nvidia-ceo-plays-with-adorable-microduck-robots-20000-sell/)   

**从吐司到贝塞麦：2026年TechCrunch创始人峰会上创始人将听到谁的声音**
> TechCrunch 将与 Fidelity Private Shares 合作举办为期一天的 Founder Summit 2026，内容超越融资和 AI 话题。活动将探讨寻找客户、组建团队、打磨路演、培养创始人领导力，以及在传统创业中心内外扩展公司的实际挑战。
📎 来源：TechCrunch - AI \| 10-24 03:06 · [阅读原文](https://techcrunch.com/2026/10/23/from-toast-to-bessemer-who-founders-will-hear-from-at-techcrunch-founder-summit-2026/)   

## 💬 社区信号 (12 篇)

**anthropics/知识工作插件**
> Anthropic 开源了面向知识工作者的 Claude 插件仓库，主要用于 Claude Cowork 场景。该项目以 Python 为主，已获得约 3.2 万星标和 3584 次 fork。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/anthropics/knowledge-work-plugins)   

**SnailSploit/Claude-Red**
> claude-red 是专为 Claude 技能系统打造的攻击性安全技能库，每个技能以结构化的 SKILL.md 文件呈现，为 Claude 注入针对特定攻击面的专家级方法论。涵盖从 SQL 注入、shellcode 到 EDR 规避、漏洞开发等多个领域。该项目使用 Python 编写，拥有 8701 个星标和 1116 个分支。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/SnailSploit/Claude-Red)   

**OpenBMB/VoxCPM**
> VoxCPM2 是一款无需分词器（Tokenizer-Free）的多语言文本转语音（TTS）工具，支持创意语音设计和逼真的声音克隆。该项目使用 Python 开发，目前已获得超过 4 万个 Star。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/OpenBMB/VoxCPM)   

**baidu/Unlimited-OCR**
> 百度推出 Unlimited-OCR，这是一个基于 Python 的开源 OCR 项目，主打一次性长文档解析能力。该项目在 GitHub 上已获得 2.8 万星标和 3000 次分叉，受到广泛关注。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/baidu/Unlimited-OCR)   

### TauricResearch/TradingAgents

Hmm，这个标题看起来是一个 GitHub 仓库的路径（用户名/仓库名），而不是需要翻译的句子。这类标识符通常保持原样。

如果你希望我翻译其中的含义，可以这样：

**Tauric 研究 / 交易智能体**

请告诉我你的具体需求。

*TauricResearch/TradingAgents*
- 来源: GitHub Trending - Python \| [原文链接](https://github.com/TauricResearch/TradingAgents)
- TradingAgents 是一个基于多智能体大语言模型的金融交易框架，采用 Python 开发。该项目目前在 GitHub 上获得约 11.3 万颗 Star 和 2.2 万次 Fork，受到广泛关注。

### Graphify-Labs/graphify

(这是一个 GitHub 仓库名称，属于专有名词，通常保持原样不翻译。)

*Graphify-Labs/graphify*
- 来源: GitHub Trending - Python \| [原文链接](https://github.com/Graphify-Labs/graphify)
- Graphify 能将包含文档、SQL 架构、配置和 PDF 的代码库转化为可查询的知识图谱。它作为一项技能支持 Claude Code、Cursor、Codex 和 Gemini CLI，采用本地确定性 AST 解析，每条关系边均有明确解释，且无需向量存储。

**Mailu/Mailu**
> Mailu 是一个基于 Docker 镜像的开源邮件服务器，提供简单可靠的自托管邮件解决方案。该项目采用 Python 开发，已获得 7587 个 Star 和 1024 次 Fork。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/Mailu/Mailu)   

**book-to-skill**
> 该项目可将任意技术书籍的 PDF 转换为 Claude Code 技能，便于在工作中学习、查阅和使用。基于 Python 开发，目前已获得约 3.6 万星标和 3800 个分支。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/virgiliojr94/book-to-skill)   

### Onyx 点应用/Onyx

**注：**`onyx-dot-app/onyx` 看起来是一个 GitHub 仓库名称（格式为"组织名/仓库名"），通常这类标识符保持原样不翻译。如果需要翻译标题文本，建议提供具体的标题内容。

*onyx-dot-app/onyx*
- 来源: GitHub Trending - Python \| [原文链接](https://github.com/onyx-dot-app/onyx)
- Onyx 是一个开源 AI 平台，提供支持所有大语言模型的高级 AI 聊天功能。该项目基于 Python 开发，已获得约 3.3 万星标和 4600\+ 次 fork。

**vllm-project/vllm**
> vLLM 是一个高吞吐量、内存高效的大语言模型推理与服务引擎，采用 Python 开发。该项目在 GitHub 上广受欢迎，已获得超过 9.5 万星标和 2.3 万次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/vllm-project/vllm)   

**open-duet（开源二重奏）**
> Open-duet 是一个开源、可自托管的 Claude Duet 替代方案，提供具名 AI 智能体，具备指令、记忆、例行任务、独立隔离的计算机环境，并在执行操作前需经用户批准。它同时也是 OpenAI Dots、Meta Muse、Grok Bot、Manus Cue 和 ChatGPT agent 的替代品，基于 Python 开发，目前已获 6126 星标。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/Anil-matcha/open-duet)   

**claude-howto 使用指南**
> 这是一份以示例驱动的 Claude Code 可视化指南，内容涵盖从基础概念到高级智能体的应用，并提供可直接复制使用的模板。该项目使用 Python 编写，已获得约 4.4 万 star。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/luongnv89/claude-howto)   

---
