---
title: 亚马逊默认拿Twitch内容训练AI且承认opt-in无人参与 等 7 条要闻
date: 2026-08-13 17:02:26 +0800
categories: [AI, 安全]
tags: [AI, 亚马逊, Twitch, AI训练, opt-in, 隐私, 数据, privacy]
image:
  path: /assets/img/posts/2026-08-13-ai-daily-20260813-amazon-twitch-ai-training/cover.webp
  alt: 亚马逊默认拿Twitch内容训练AI且承认opt-in无人参与 等 7 条要闻
---

> 本文由钉钉知识库每日要闻同步生成，共 7 条要闻。

> 26年8月13日17时0分，遍历过去24小时的40篇文章，总结出7个热点话题。由claude-opus-4-8提炼，💡部分为模型观点，仅作参考。   

# 📌 今日要闻

**1\. 亚马逊默认拿Twitch内容训练AI且承认opt-in无人参与**

亚马逊将默认使用Twitch主播的直播内容训练AI，主播需主动opt out才能退出。Twitch首席产品官Mike Minton在直播中直言，若采用主动加入(opt-in)机制，将不会有人选择参与。
> 💡 **深度解读** 官方公开承认「只要给用户选择权就没人给数据」，这是数据供给逻辑的一次坦白。头部平台正把自有UGC锁进训练管道，训练数据的竞争从公开抓取转向平台内容主权的封闭化。国内长视频与直播平台手握同类资产，谁先把默认授权写进用户协议，谁就掌握下一轮多模态数据的排他入口。   
> 📰 [TechCrunch - AI](https://techcrunch.com/2026/08/12/amazon-will-train-on-twitch-streamers-content-by-default-unless-they-opt-out/)   

---

**2\. Cognition估值半年从260亿翻到400亿美元**

AI编程公司Cognition据报道正洽谈新一轮融资，估值或达400亿美元，几个月前刚以260亿估值完成10亿融资。同日Lovable以133亿估值融4亿(6月已实现5亿美元年化收入)，Blacksmith估值和营收一年内各增长约10倍。
> 💡 **深度解读** AI编程赛道的估值加速度是今天最集中的资本信号，市场把编码判定为最先跑通PMF的Agent场景。Lovable的5亿ARR证明这不是纯故事，营收在跟上估值。这对国内玩家是压力也是机会窗：编程Agent的护城河仍在模型能力而非产品形态，谁的底模不落后，谁就能在同一套产品逻辑上分食企业付费。   
> 📰 [TechCrunch - AI1](https://techcrunch.com/2026/08/12/ai-coding-startup-cognition-reportedly-already-in-talks-to-raise-at-40b-valuation/) · [TechCrunch - AI2](https://techcrunch.com/2026/08/12/lovable-confirms-new-13-3b-valuation-raises-another-400m/) · [TechCrunch - AI3](https://techcrunch.com/2026/08/12/blacksmiths-valuation-jumps-10x-to-550m-as-ai-coding-fuels-software-validation/)   

---

**3\. AI正在抽掉软件工程的中级岗位而非替代整体**

Hacker News热议文章指出，AI编码工具高效完成常规任务，正在削弱软件工程的「中产阶级」——中级工程师群体，导致行业更依赖资深工程师，初级和中级岗位成长空间被压缩。
> 💡 **深度解读** 这条比任何裁员数字都更精确地描述了AI对就业结构的改造：不是砍总量，而是掏空中间层、抬高进入门槛。人才梯队被从中间截断，长期看资深工程师的供给会枯竭，因为没人再走完初级到资深的爬升路径。国内大厂的校招和培养体系需要正视这个断层，否则三年后招不到能接管Agent的中坚。   
> 📰 [Hacker News - AI](https://blog.florianherrengt.com/ai-removing-middle-class-software-engineering.html)   

---

**4\. 自主AI代理穷举证伪Conway 99图的循环解**

研究者用自主AI代理系统性探究Conway的99-图问题，通过穷举证明在Z/99上的循环图最多只能满足68%的约束(49个差分类中的33个)，且过程可复现、可验证。
> 💡 **深度解读** 继上周未发布模型在黎曼猜想上有进展后，AI在数学上的角色又前进一步：这次不是启发式猜想，而是给出一个可验证的严格否定结论。AI正从「产生想法」转向「完成可审计的证明工作量」，这是数学研究流程被真正接入的信号。可验证性是关键——它让AI的数学产出能被同行接受，而非停留在演示。   
> 📰 [arXiv - Artificial Intelligence](https://arxiv.org/abs/2608.11211)   

---

**5\. 对立目标的双LLM智能体会对话崩溃而非竞争**

arXiv论文指出，两个目标结构对立的LLM智能体在多轮交互中因缺乏共享目标函数，会导致对话崩溃而非形成竞争，最终双方目标均无法达成。作者提出用控制论式治理层(Experience Orchestrator)替代缺失的目标函数。
> 💡 **深度解读** 这条给多智能体系统的乐观叙事泼了冷水：把多个LLM放在一起不会自然涌现出博弈或协作，缺共享目标就是集体死机。它说明多Agent架构的瓶颈不在单体能力，而在缺一个外部治理调度层。谁能把这层orchestration做成可复用的基础设施，谁就掌握了多Agent产品化的关键钥匙。   
> 📰 [arXiv - Artificial Intelligence](https://arxiv.org/abs/2608.11207)   

---

**6\. 有人冒充ClaudeBot爬虫掩护大规模漏洞扫描**

有攻击者伪造ClaudeBot等知名AI爬虫的身份进行大规模漏洞扫描，借此规避安全防护和访问限制。该发现在Hacker News获273分、200条评论。
> 💡 **深度解读** AI爬虫的白名单地位正在被武器化：站点为了不挡AI流量而放行的规则，反而成了攻击者的通行证。这是AI基础设施普及带来的新攻击面——身份信任被反向利用。安全团队过去对AI爬虫的宽容策略需要重估，UA白名单已不再可信，得配合IP段和行为验证。   
> 📰 [Hacker News - AI](https://knownagents.com/insights)   

---

**7\. OpenMontage把编程助手改造成700技能的视频工作室**

OpenMontage自称全球首个开源智能体视频制作系统，包含12条生产流水线、100多种工具、700多个智能体技能与制作知识文件，能将AI编程助手转变为完整视频制作工作室。同期LTX-2音视频生成模型开源，提供推理与LoRA训练。
> 💡 **深度解读** 视频生产正在被拆解成可被Agent调度的流水线\+技能库，而非单个大模型端到端生成。这条路线把「知识文件」外挂给通用编程Agent，说明工作流编排的价值正超过底模本身。对国内做AI视频的团队是提醒：卷模型分辨率不如卷可组合的生产工具链，后者才是难以被单个新模型抹平的壁垒。   
> 📰 [GitHub Trending - Python1](https://github.com/calesthio/OpenMontage) · [GitHub Trending - Python2](https://github.com/Lightricks/LTX-2)   

# 📋 详细内容

## 📰 新闻媒体 (12 篇)

**Anthropic新水印将揭露Claude用户在工作和课堂上使用它，部分用户对此不满**
> Anthropic 为其 AI 生成内容新增了水印系统，用于标识由 Claude 生成的文本。部分用户在社交媒体上表达不满，担心这会暴露他们在工作或课堂中使用该工具的行为。
📎 来源：TechCrunch - AI \| 08-13 06:26 · [阅读原文](https://techcrunch.com/2026/08/12/some-claude-users-are-mad-that-anthropics-new-watermarks-will-catch-them-cheating-at-their-jobs-classes/)   

**亚马逊将默认使用 Twitch 主播的内容进行训练，除非主播选择退出**
> 亚马逊将默认使用 Twitch 主播的内容来训练 AI，主播需主动选择退出（opt out）才能避免。Twitch 首席产品官 Mike Minton 在直播中坦言，若采用主动加入（opt-in）机制，将不会有人选择参与。
📎 来源：TechCrunch - AI \| 08-13 04:10 · [阅读原文](https://techcrunch.com/2026/08/12/amazon-will-train-on-twitch-streamers-content-by-default-unless-they-opt-out/)   

**AI 编程初创公司 Cognition 据报道已在洽谈以 400 亿美元估值融资**
> AI编程初创公司Cognition据报道正洽谈新一轮融资，估值或达400亿美元。就在几个月前，该公司刚以260亿美元估值完成10亿美元融资。
📎 来源：TechCrunch - AI \| 08-13 02:19 · [阅读原文](https://techcrunch.com/2026/08/12/ai-coding-startup-cognition-reportedly-already-in-talks-to-raise-at-40b-valuation/)   

**随着AI安全问题日益凸显，三位先驱为坚持开放发声**
> 在Ai4大会上，AI领域三位权威专家Geoffrey Hinton、李飞飞和吴恩达就监管、开源访问及美国如何应对中国崛起展开辩论。面对日益增长的AI安全担忧，三位先驱主张保持开放。
📎 来源：TechCrunch - AI \| 08-13 01:51 · [阅读原文](https://techcrunch.com/2026/08/12/as-ai-safety-concerns-mount-three-pioneers-make-the-case-for-staying-open/)   

**OpenAI 支持的 Thrive Holdings 融资 20 亿美元，助力企业级 AI 落地**
> Thrive Holdings 以 120 亿美元估值完成 20 亿美元新融资，投资方包括软银、D1 Capital Partners 和 Altimeter Capital，旨在将 AI 引入企业市场。
📎 来源：TechCrunch - AI \| 08-13 01:41 · [阅读原文](https://techcrunch.com/2026/08/12/openai-backed-thrive-holdings-raises-2b-to-bring-ai-to-the-enterprise/)   

**Mesh：Automattic 面向所有人的 CRM，正式登陆安卓**
> Automattic 推出的 AI 联系人管理与客户关系应用 Mesh 现已登陆 Android 平台。
📎 来源：TechCrunch - AI \| 08-13 00:57 · [阅读原文](https://techcrunch.com/2026/08/12/mesh-automattics-crm-for-everyone-comes-to-android/)   

**为什么智能戒指制造商 Sandbar 认为 AI 可穿戴设备的未来在于语音**
> AI笔记硬件近年兴起，各类信用卡大小的设备、吊坠、胸针乃至转录耳机纷纷承诺记录会议并生成摘要和待办事项。如今新一波可穿戴设备（尤其是戒指）押注人们希望用同样方式捕捉零散想法。制造Stream戒指的Sandbar认为，语音将是AI可穿戴设备的未来方向。
📎 来源：TechCrunch - AI \| 08-13 00:46 · [阅读原文](https://techcrunch.com/video/why-stream-ring-maker-sandbar-says-the-future-of-ai-wearables-is-voice/)   

**Lovable 确认最新估值达 133 亿美元，再融资 4 亿美元**
> Lovable 完成 4 亿美元新一轮融资，估值达 133 亿美元。此前该公司于 6 月实现 5 亿美元年化收入。
📎 来源：TechCrunch - AI \| 08-13 00:04 · [阅读原文](https://techcrunch.com/2026/08/12/lovable-confirms-new-13-3b-valuation-raises-another-400m/)   

**一桩2.5亿美元收购如何演变成欺诈与伪造签名指控**
> VideoVerse 一笔 2.5 亿美元的收购交易崩盘，联合创始人 Vinayak Shrivastav 深陷多起法律诉讼。投资者至今仍未拿到应得的收益分成，交易还牵涉欺诈和伪造签名等指控。
📎 来源：TechCrunch - AI \| 08-12 23:44 · [阅读原文](https://techcrunch.com/2026/08/12/how-a-250-million-acquisition-collapsed-into-allegations-of-fraud-and-forged-signatures/)   

**Sandbar为何认为其语音戒指能避开AI硬件的坟场**
> Sandbar 推出一款支持语音功能的智能戒指，希望借助可穿戴设备捕捉用户随时闪现的想法和创意。此举加入了近年兴起的 AI 笔记硬件浪潮，此前已有卡片式设备、吊坠、胸针等产品试图记录会议并生成摘要。
📎 来源：TechCrunch - AI \| 08-12 22:22 · [阅读原文](https://techcrunch.com/podcast/why-sandbar-thinks-its-voice-enabled-ring-can-avoid-the-ai-hardware-graveyard/)   

**Made by Google '26 发布会全汇总：Pixel 11、Pixel Watch 5、Pixel Tag 及众多 Gemini 新功能**
> 谷歌在Made by Google 2026发布会上推出了Pixel 11系列手机、Pixel Watch 5智能手表，以及对标苹果AirTag的全新追踪器Pixel Tag。此外还发布了大量Gemini AI新功能。
📎 来源：TechCrunch - AI \| 08-12 22:20 · [阅读原文](https://techcrunch.com/2026/08/12/google-unveils-pixel-11-lineup-new-airtag-rival-and-gemini-features-at-made-by-google-2026/)   

**AI 代码测试初创公司 Blacksmith 估值不到一年飙升近 10 倍**
> AI代码测试初创公司Blacksmith在不到一年内估值增长近10倍，同期营收也增长超过十倍。
📎 来源：TechCrunch - AI \| 08-12 19:00 · [阅读原文](https://techcrunch.com/2026/08/12/blacksmiths-valuation-jumps-10x-to-550m-as-ai-coding-fuels-software-validation/)   

## 💬 社区信号 (23 篇)

**德国倡导团体就 Meta AI 眼镜提起刑事诉讼**
> 德国一家维权组织就 Meta 的 AI 眼镜提起刑事诉讼，认为该设备可能侵犯隐私。此举反映出各界对可穿戴智能设备潜在监控与隐私风险的担忧。
📎 来源：Hacker News - AI \| 08-12 22:06 · [阅读原文](https://www.reuters.com/legal/government/german-advocacy-group-lodges-criminal-complaint-over-meta-ai-glasses-2026-08-12/)   

**有人正在进行大规模漏洞扫描，冒充ClaudeBot等AI爬虫**
> 有人正在冒充 ClaudeBot 等 AI 爬虫机器人，进行大规模漏洞扫描。攻击者通过伪造这些知名 AI 机器人的身份来规避安全防护和访问限制。该发现在 Hacker News 上引发热议，获得 273 分和 200 条评论。
📎 来源：Hacker News - AI \| 08-12 22:02 · [阅读原文](https://knownagents.com/insights)   

**AI 正在消灭软件工程的中产阶层？**
> 文章探讨了 AI 正在削弱软件工程行业的"中产阶级"——即中级工程师群体，因为 AI 工具能高效完成大量常规编码任务。这一趋势可能导致行业更依赖资深工程师，而初级和中级岗位的成长空间被压缩。该文在 Hacker News 上引发热议，获得 870 分和 778 条评论。
📎 来源：Hacker News - AI \| 08-12 21:20 · [阅读原文](https://blog.florianherrengt.com/ai-removing-middle-class-software-engineering.html)   

**semantica-agi/语义**
> Semantica 是一个用 Python 编写的图原生基础设施项目，专为构建具备上下文管理和可问责性的 AI 系统而设计。该项目在 GitHub 上已获得约 5989 个星标和 642 次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/semantica-agi/semantica)   

**shiyu-coder/Kronos**
> Kronos 是一个面向金融市场"语言"的基础模型，采用 Python 开发。该项目在 GitHub 上颇受欢迎，获得约 3.7 万星标和 6153 次 fork。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/shiyu-coder/Kronos)   

**MediaCrawler（自媒体爬虫）**
> MediaCrawler 是一个基于 Python 的多平台内容爬虫工具，支持抓取小红书、抖音、快手、B站、微博、百度贴吧和知乎等平台的帖子/视频及评论数据。该项目在 GitHub 上广受欢迎，已获得超过 6.2 万 Stars 和 1.2 万 Forks。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/NanmiCoder/MediaCrawler)   

**ppt-master**
> AI 工具 ppt-master 能将文档或主题自动生成原生 PowerPoint 演示文稿，支持原生图形、转场动画、数据图表和表格。它还可根据演讲备注生成音频旁白，并兼容用户自定义的 .pptx 模板。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/hugohe3/ppt-master)   

**SpiderFoot**
> SpiderFoot 是一款基于 Python 的开源工具，能够自动化开源情报（OSINT）收集，用于威胁情报分析和攻击面测绘。该项目在 GitHub 上获得超过 2 万颗星和 3300 多次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/smicallef/spiderfoot)   

**Lightricks/LTX-2**
> LTX-2 是一个音视频生成模型，其官方 Python 包提供推理和 LoRA 训练功能。该项目基于 Python 开发，目前在 GitHub 上已获得 8787 个星标和 1400 次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/Lightricks/LTX-2)   

**cactus-compute/needle**
> Cactus Compute 推出 Needle，一个仅 14MB 的基础模型，专为手机、可穿戴设备、智能家居和机器人等微型设备设计。该项目基于 Python 开发，目前已获得 4529 个星标和 317 次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/cactus-compute/needle)   

**Sherlock 项目**
> Sherlock 是一个用 Python 编写的开源工具，可通过用户名在众多社交网络平台上查找关联账户。该项目在 GitHub 上广受欢迎，已获得约 8.9 万颗星和 1 万余次 fork。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/sherlock-project/sherlock)   

**3b1b/manim**
> Manim 是一个用于制作数学讲解视频动画的 Python 引擎，广泛用于可视化数学概念。该项目在 GitHub 上已获得超过 9 万颗星标和 7500 多次分叉，社区关注度极高。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/3b1b/manim)   

**anthropics/技能**
> 这是 Anthropic 开源的 Agent Skills 公开代码仓库，主要使用 Python 语言开发。该项目已获得约 16.8 万星标和 2 万次分叉，在开发者社区中广受关注。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/anthropics/skills)   

**朱林森/每日股票分析**
> 这是一个由大语言模型驱动的多市场股票智能分析系统，集成多源行情数据、实时新闻、决策看板和自动推送功能。系统支持零成本定时运行，采用 Python 开发。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/ZhuLinsen/daily_stock_analysis)   

**claude-code**
> Claude Code 是一款运行在终端中的智能编程工具，能理解代码库并通过自然语言命令帮助开发者更快地编码。它可以执行日常任务、解释复杂代码并处理 Git 工作流。该项目已获得超过 14 万 Stars。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/anthropics/claude-code)   

**HKUDS/DeepTutor**
> DeepTutor 是一个基于 Python 的终身个性化辅导系统，旨在为用户提供持续的学习支持。该项目在 GitHub 上颇受欢迎，已获得 35332 个星标和 4476 次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/HKUDS/DeepTutor)   

### omnigent-ai/omnigent

Wait — this looks like a repository name (a GitHub-style `owner/repo` identifier), not an English title to translate. Repository names, usernames, and code identifiers are typically kept as-is rather than translated.

If you'd like, could you share the actual English title you want translated? I'm happy to help with that.

*omnigent-ai/omnigent*
- 来源: GitHub Trending - Python \| [原文链接](https://github.com/omnigent-ai/omnigent)
- Omnigent 是一个开源 AI 智能体框架和元框架，可编排 Claude Code、Codex、Cursor、Pi 及自定义智能体。它支持在不重写代码的情况下切换底层框架，并提供策略强制、沙箱隔离等功能。用户还能实时协作，从任意设备进行操作。

**IndexTTS 索引文本转语音**
> IndexTTS 是一个工业级、可控且高效的零样本文本转语音（TTS）系统，基于 Python 开发。该项目在 GitHub 上获得了约 22782 个 Star 和 2768 个 Fork，具有较高的社区关注度。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/index-tts/index-tts)   

**基于项目的学习实践教程**
> 这是一个精选的基于项目的编程教程列表，涵盖多种编程语言，其中包括 Python。该项目在 GitHub 上广受欢迎，获得约 27.9 万星标和 3.5 万次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/practical-tutorials/project-based-learning)   

**OpenMontage**
> OpenMontage 是全球首个开源的智能体视频制作系统，包含12条生产流水线、100多种工具以及700多个智能体技能与制作知识文件。它能将 AI 编程助手转变为完整的视频制作工作室，使用 Python 开发。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/calesthio/OpenMontage)   

### paradigmxyz/centaur

（该标题为 GitHub 仓库名称，属于专有名词，无需翻译）

*paradigmxyz/centaur*
- 来源: GitHub Trending - Python \| [原文链接](https://github.com/paradigmxyz/centaur)
- Centaur 是一个开源的前沿智能体（agentic）基础设施，用户可完全自主拥有。它类似 Claude Tag，但功能更强大，采用 Python 编写，目前已获得 1117 个星标和 204 次分叉。

**huggingface/transformers**
> Hugging Face Transformers 是一个开源的机器学习模型定义框架，支持文本、视觉、音频及多模态等前沿模型，可用于推理和训练。该项目基于 Python 开发，已获得超过 16 万星标和 3.4 万次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/huggingface/transformers)   

**unslothai/unsloth**
> Unsloth 是一个本地 UI 工具，可用于运行和训练大语言模型及扩散模型，支持 Qwen3.8、Kimi K3、Gemma 4、DeepSeek-V4、FLUX 等多种模型。该项目基于 Python 开发，已获得约 7 万颗 GitHub Star。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/unslothai/unsloth)   

## 📚 论文前沿 (5 篇)

**多智能体大模型系统的动态治理：面向协作对话成果**
> 两个目标结构对立的 LLM 智能体在多轮交互中，因缺乏共享目标函数会导致对话崩溃而非竞争，最终双方目标均无法达成。本文提出用控制论式的治理层（Experience Orchestrator）来替代这一缺失的目标函数，以协调多智能体系统实现协作性对话结果。
📎 来源：arXiv - Artificial Intelligence \| 08-13 12:00 · [阅读原文](https://arxiv.org/abs/2608.11207)   

**分布鸟：面向贝叶斯模型校准的文献知情先验分布设计**
> Distribird 是一款智能网络应用，用于自动化贝叶斯模型校准中的信息先验分布构建。它旨在解决研究者因从科学文献构建先验耗时且需专业知识而普遍依赖均匀先验的问题。只需输入参数名称和物理信息，即可自动生成基于文献的先验分布。
📎 来源：arXiv - Artificial Intelligence \| 08-13 12:00 · [阅读原文](https://arxiv.org/abs/2608.11210)   

**康威99图的强制结构约简与可验证界**
> 研究者用自主AI代理系统性地探究了Conway的99-图问题（即是否存在参数为srg(99,14,1,2)的强正则图）。他们通过穷举证明了在Z/99上的循环图最多只能满足68%的约束条件（49个差分类中的33个）。该研究采用可复现、可验证的方法，并按赛道的部分得分标准进行评分。
📎 来源：arXiv - Artificial Intelligence \| 08-13 12:00 · [阅读原文](https://arxiv.org/abs/2608.11211)   

**检测路由翻转比判断是否需要修复更容易：量化专家混合模型中的因果路由介导损伤**
> 量化混合专家（MoE）模型时，4位KV缓存量化会将token推过Top-k路由的决策边界，导致激活的专家发生翻转。本文不提出新的缓解方法，而是提供了因果分析框架、实证结果和检测极限结论，用于量化路由翻转所造成损害的比例（RMF）。研究表明，检测路由翻转比判断是否需要修复要容易得多。
📎 来源：arXiv - Artificial Intelligence \| 08-13 12:00 · [阅读原文](https://arxiv.org/abs/2608.11212)   

**穷人的智能体建模：在笔记本电脑上模拟大规模大语言模型智能体社会**
> 该研究提出一种低成本方法，用少量廉价查询拟合出低参数模型来替代每个大语言模型智能体。此方法基于统计物理学观察，因为对大规模智能体社会的研究通常关注宏观现象（如相变行为、规模效应），而非单个智能体的认知。由此可在普通笔记本上模拟大规模LLM智能体社会。
📎 来源：arXiv - Artificial Intelligence \| 08-13 12:00 · [阅读原文](https://arxiv.org/abs/2608.11215)   

---
