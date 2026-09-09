---
title: Mistral 210亿欧元估值坐实主权AI叙事 等 7 条要闻
date: 2026-09-09 17:03:08 +0800
categories: [AI, 大模型]
tags: [AI, Mistral, 估值, 主权AI, 融资, 欧洲, LLM]
image:
  path: /assets/img/posts/2026-09-09-ai-daily-20260909-mistral-sovereign-ai/cover.webp
  alt: Mistral 210亿欧元估值坐实主权AI叙事 等 7 条要闻
---

> 本文由钉钉知识库每日要闻同步生成，共 7 条要闻。

> 26年9月9日17时0分，遍历过去24小时的41篇文章，总结出7个热点话题。由claude-opus-4-8提炼，💡部分为模型观点，仅作参考。   

# 📌 今日要闻

**1\. Mistral 210亿欧元估值坐实主权AI叙事**

Mistral 以 210 亿欧元估值完成 30 亿欧元 D 轮融资，由三星、Scaleup Europe 和 PSG Equity 领投。此轮估值较前一轮大幅抬升，融资定位为「主权 AI」需求。
> 💡 **深度解读** 这轮融资告诉我，欧洲资本正把「非美国、非中国的第三极模型供应」当成一个独立可投的品类，而不是技术领先度的赌注——Mistral 模型能力并不领先 OpenAI 和 DeepSeek，但地缘属性本身成了溢价来源。对中国玩家的启示是：主权 AI 逻辑同样成立，各国政府采购会天然排斥中美模型，这为国产模型出海制造了政治天花板，但也意味着「本地部署\+可控」的产品形态比参数竞赛更值钱。   
> 📰 [TechCrunch - AI](https://techcrunch.com/2026/09/08/mistral-raises-e3b-as-sovereign-ai-becomes-big-business/)   

---

**2\. Cognition 480亿估值否定AI编程赢家通吃**

Cognition 完成新一轮融资，估值达 480 亿美元，估值倍数高于 Cursor 被 SpaceX 收购前的水平。多家 AI 编程公司同时维持高估值。
> 💡 **深度解读** AI 编程是目前 LLM 最先跑通的商业化场景，一年前市场认为 Cursor 会通吃，现在 Cognition 以更高倍数融资，说明投资人判断编程市场会长期多头竞争、切分为不同工作流（补全、agent、企业交付）。这对国内厂商是个窗口信号：编程赛道尚未固化，字节、通义们仍有卡位机会，但前提是做出差异化的 agent 形态而非再造一个补全工具。   
> 📰 [TechCrunch - AI](https://techcrunch.com/2026/09/08/cognition-hits-48b-valuation-signaling-investors-believe-ai-coding-is-far-from-a-winner-take-all-market/)   

---

**3\. OpenAI千禧年难题证明被指造假注水**

OpenAI 公布用 AI 生成的纳维-斯托克斯千禧年大奖难题解答，含 Lean 形式化证明。纽约大学一位数学家指控 OpenAI 采取不正当手段，该难题首个解答者可获 100 万美元奖金。陶哲轩另指出 AI 正「不可再生」地消耗现有开放数学难题。
> 💡 **深度解读** 这件事把「AI 做出重大数学突破」的宣传拉回现实：一个未经同行评议、被专业数学家当场质疑的 Lean 证明，说明当前模型在真正原创数学上仍不可信，营销领先于能力。更关键的是陶哲轩的判断——开放数学难题作为评测基准正在被耗尽，这意味着我们很快会失去衡量模型推理能力上限的可靠标尺，未来的 benchmark 焦虑会比模型焦虑更严重。   
> 📰 [OpenAI Blog](https://openai.com/index/navier-stokes-solution) · [TechCrunch - AI](https://techcrunch.com/2026/09/08/openai-fought-dirty-on-career-making-math-problem-says-nyu-mathematician/) · [Hacker News - AI](https://mathstodon.xyz/@tao/117237320796901560)   

---

**4\. Meta以Muse押上消费级数据信任赌注**

Meta 推出个人 AI 助手 Muse，寻求访问用户的邮件、日历、支付和健康数据。这是 Meta 迄今最大的消费级 AI 布局，Hacker News 讨论获 495 分。
> 💡 **深度解读** Muse 的核心不是模型能力而是数据授权——Meta 想用它十亿级用户绕过 OpenAI 和 Google 在「记忆型个人 agent」上的先发。真正的变量是信任：一家有隐私前科的公司要求最敏感的支付和健康权限，用户是否买单将定义消费级 agent 的准入门槛。对国内的映射是，微信/支付宝这类已握有全域数据的超级 App，做个人 agent 的起跑线远高于 Meta，这是中国厂商罕见的结构性优势。   
> 📰 [TechCrunch - AI](https://techcrunch.com/2026/09/08/meta-debuts-its-muse-ai-agent-will-consumers-trust-it/) · [Hacker News - AI](https://ai.meta.com/muse/)   

---

**5\. Claude令牌遭批量盗刷暴露agent信用风险**

多名 Claude 用户发现账户闲置时 token 仍被消耗，怀疑令牌遭盗用。Anthropic 随后向用户发出黑客攻击警告。
> 💡 **深度解读** 当 token 直接等于金钱、且 agent 能自主消耗算力时，被盗令牌就从数据泄露升级为可被无限套现的资金漏洞。这是 agent 商业化后出现的新型攻击面——过去盗号偷的是数据，现在偷的是可执行的算力额度。任何做 API 计费型 agent 平台的公司（包括国内所有大模型开放平台）都得重新设计令牌的权限隔离和消耗熔断机制，否则一次泄露就是直接财务损失。   
> 📰 [TechCrunch - AI](https://techcrunch.com/2026/09/08/hackers-are-stealing-claude-tokens-from-subscribers/)   

---

**6\. GitHub渗透测试agent将安全工具全面自动化**

HexStrike AI 是一款 MCP 服务器，可让 Claude、GPT、Copilot 等 agent 自主调用 150 多种网络安全工具，支持自动化渗透测试、漏洞发现和赏金自动化。同期 Google 将 Chrome 更新周期从每月缩短至每两周以应对 AI 加速的威胁。
> 💡 **深度解读** 攻防两端同时被 AI 加速：HexStrike 让单个操作员就能编排百级安全工具做全自动渗透，而 Chrome 被迫把补丁节奏翻倍，说明漏洞的发现和利用速度已经超过人类修复速度。这标志攻击方比防守方更早吃到 agent 红利——自动化攻击的边际成本趋近于零，而防守仍受限于人工审核和发布流程。国内安全厂商如果不把响应体系 agent 化，会在这轮不对称竞赛中系统性落后。   
> 📰 [GitHub Trending - Python](https://github.com/0x4m4/hexstrike-ai) · [TechCrunch - AI](https://techcrunch.com/2026/09/08/chrome-is-now-shipping-updates-every-2-weeks-as-ai-changes-the-security-landscape/)   

---

**7\. LibreOffice靠去AI标签冲下载纪录**

LibreOffice 公开宣布其软件不含 AI 功能后，下载量创新纪录，相关讨论在 Hacker News 获 679 分。
> 💡 **深度解读** 这是我连续第二次看到「无 AI」成为卖点（上次是去 AI 写作工具）。它验证了一个被大厂集体忽视的市场：相当规模的用户对被强塞 AI 功能、数据被采集感到反感，愿意为「干净、可控、不联网」付费。对国内那些把 AI 按钮硬塞进每个产品的 PM，这是一个逆向信号——AI 不是普适加分项，在生产力工具里，可选和可关闭比默认开启更重要。   
> 📰 [Hacker News - AI](https://manualdousuario.net/en/libreoffice-download-record-no-ai/)   

# 📋 详细内容

## 🏢 官方动态 (4 篇)

**GPT-5.6 Sol 如何助力量子计算实验**
> 一位 MIT 研究者利用 GPT-5.6 Sol 搭配 Codex，自主运行量子计算实验、分析结果并校准量子比特。
📎 来源：OpenAI Blog \| 09-09 01:00 · [阅读原文](https://openai.com/index/codex-quantum-computing-experiments)   

**The Work Now Within Reach**
> 更强大且更实惠的AI正在扩展个人与企业所能完成的工作范围。这些进步让增长变得更加经济可行。
📎 来源：OpenAI Blog \| 09-08 21:00 · [阅读原文](https://openai.com/index/the-work-now-within-reach)   

**介绍 ChatGPT 图像 2.5**
> ChatGPT Images 2.5 能将你的创意、草图和参考照片转化为更个性化、更精致的图像，更好地呈现你的想法。
📎 来源：OpenAI Blog \| 09-08 19:30 · [阅读原文](https://openai.com/index/introducing-chatgpt-images-2-5)   

**纳维-斯托克斯千禧年大奖难题**
> 这篇文章公布了一份由AI生成的纳维-斯托克斯千禧年大奖难题的解决方案，包含书面论述和用Lean语言编写的形式化证明。
📎 来源：OpenAI Blog \| 09-08 18:00 · [阅读原文](https://openai.com/index/navier-stokes-solution)   

## 📰 新闻媒体 (7 篇)

**黑客正在窃取订阅用户的 Claude 令牌**
> 有Claude用户发现自己未使用账户时token仍被消耗，怀疑遭到盗用。Anthropic随后就此向用户发出黑客攻击警告。
📎 来源：TechCrunch - AI \| 09-09 05:10 · [阅读原文](https://techcrunch.com/2026/09/08/hackers-are-stealing-claude-tokens-from-subscribers/)   

**Cognition估值达480亿美元，表明投资者认为AI编程远非赢家通吃的市场**
> Cognition 完成新一轮融资，估值达到 480 亿美元，其估值倍数高于 Cursor 出售给 SpaceX 前的水平。这表明投资者认为 AI 编程市场竞争格局远未定型，尚未形成赢家通吃的局面。
📎 来源：TechCrunch - AI \| 09-09 05:04 · [阅读原文](https://techcrunch.com/2026/09/08/cognition-hits-48b-valuation-signaling-investors-believe-ai-coding-is-far-from-a-winner-take-all-market/)   

**Meta推出Muse AI智能体，消费者会信任它吗？**
> Meta 推出个人 AI 助手 Muse，希望获取用户的邮件、日历、支付和健康服务等数据访问权限。这是该公司迄今最大的消费级 AI 布局，也成为检验用户是否仍愿信任 Meta 处理其数据的重要考验。
📎 来源：TechCrunch - AI \| 09-09 03:00 · [阅读原文](https://techcrunch.com/2026/09/08/meta-debuts-its-muse-ai-agent-will-consumers-trust-it/)   

**纽约大学数学家称OpenAI在成名数学难题上耍手段**
> 一位纽约大学数学家指控OpenAI在纳维-斯托克斯存在性与光滑性问题上采取了不正当竞争手段，该问题的首个解答者可获得100万美元奖金。
📎 来源：TechCrunch - AI \| 09-09 01:32 · [阅读原文](https://techcrunch.com/2026/09/08/openai-fought-dirty-on-career-making-math-problem-says-nyu-mathematician/)   

**谷歌云携手埃森哲，加速追赶AI部署竞赛**
> 谷歌云与埃森哲达成合作，扩大企业级AI布局。该合作依托前置部署工程师推动AI落地，旨在破解部署瓶颈、加快企业采用步伐。
📎 来源：TechCrunch - AI \| 09-09 00:20 · [阅读原文](https://techcrunch.com/2026/09/08/google-cloud-races-to-catch-up-in-the-ai-deployment-wars-with-accenture-deal/)   

**Chrome 现在每两周发布一次更新，人工智能正在改变安全格局**
> Google 将 Chrome 的发布周期从每月缩短至每两周一次，以更快地推送安全补丁和新功能。这一调整是为了应对 AI 改变安全形势、威胁出现速度加快的挑战。
📎 来源：TechCrunch - AI \| 09-08 23:04 · [阅读原文](https://techcrunch.com/2026/09/08/chrome-is-now-shipping-updates-every-2-weeks-as-ai-changes-the-security-landscape/)   

**Mistral 融资 30 亿欧元，主权 AI 成为大生意**
> Mistral以210亿欧元估值完成30亿欧元D轮融资，由三星、Scaleup Europe和PSG Equity领投。此轮融资凸显了主权AI正成为一门大生意。
📎 来源：TechCrunch - AI \| 09-08 22:17 · [阅读原文](https://techcrunch.com/2026/09/08/mistral-raises-e3b-as-sovereign-ai-becomes-big-business/)   

## 💬 社区信号 (25 篇)

**人工智能责任——OpenAI 与 Anthropic**
> 该文章通过一条推特链接讨论了 OpenAI 和 Anthropic 两家公司在 AI 责任方面的话题，在 Hacker News 上获得了 76 分和 22 条评论。由于原文仅为社交媒体链接，具体内容需查看推特原帖了解详情。
📎 来源：Hacker News - AI \| 09-09 09:32 · [阅读原文](https://twitter.com/hilbertspaess/status/2097476196791709843)   

**陶哲轩：数学未解难题正被人工智能不可再生地挖掘殆尽**
> 陶哲轩指出，AI 正在"不可再生"地消耗现有的开放数学难题，就像开采有限资源一样。这引发了关于这类问题作为衡量 AI 能力的基准正被快速耗尽的讨论。
📎 来源：Hacker News - AI \| 09-09 05:00 · [阅读原文](https://mathstodon.xyz/@tao/117237320796901560)   

**Muse——Meta的个人AI智能体**
> 很抱歉，你提供的内容中只有文章的链接和评论数据，没有实际的正文内容可供总结。
📎 来源：Hacker News - AI \| 09-09 03:25 · [阅读原文](https://ai.meta.com/muse/)   

根据现有信息，这篇文章介绍的是 Meta 推出的个人 AI 智能体产品 Muse，在 Hacker News 上获得了 495 分和 534 条评论的较高关注度。如需准确摘要，请提供文章正文。

**LLM 注意力可视化**
> 这是一个可视化大语言模型注意力机制的工具，帮助用户直观理解 LLM 在生成文本时如何关注输入内容的不同部分。该项目在 Hacker News 上获得 156 分和 24 条评论的关注。
📎 来源：Hacker News - AI \| 09-09 00:59 · [阅读原文](https://ishamf.dev/p/llm-attention-visualizer/)   

**Connecting the machines**
> 该文章仅提供了标题和链接信息，缺乏正文内容，无法准确概括其核心要点。根据标题"Connecting the machines"（连接机器）推测，文章可能涉及机器互联或网络连接相关技术主题。
📎 来源：Hacker News - AI \| 09-09 00:43 · [阅读原文](https://herdr.dev/blog/connecting-the-machines/)   

**LibreOffice 宣布不含 AI 功能后下载量创纪录**
> LibreOffice 在公开宣布其不含 AI 功能后，下载量创下新纪录。这一现象引发了社区的广泛讨论，反映出部分用户对无 AI 软件的青睐。相关文章在 Hacker News 上获得 679 分和 226 条评论。
📎 来源：Hacker News - AI \| 09-08 22:05 · [阅读原文](https://manualdousuario.net/en/libreoffice-download-record-no-ai/)   

**我们必须返回办公室以便当面使用 AI**
> 这是一篇发表在幽默网站 McSweeney's 上的讽刺文章，以荒诞逻辑主张员工必须重返办公室"当面"使用 AI。文章通过戏仿企业推动返岗（RTO）的说辞，讽刺了这类政策缺乏合理依据的现象。
📎 来源：Hacker News - AI \| 09-08 21:41 · [阅读原文](https://www.mcsweeneys.net/articles/why-we-must-return-to-the-office-to-use-ai-in-person)   

### i-have-adhd（我有多动症）

Note: I've kept the username/repo format since "ayghri/i-have-adhd" appears to be a GitHub-style repository path. The repository name itself translates to "我有多动症" (I have ADHD).

If you just want the phrase translated:

**我有多动症**

*ayghri/i-have-adhd*
- 来源: GitHub Trending - Python \| [原文链接](https://github.com/ayghri/i-have-adhd)
- 这是一个让编码 AI 助手直接给出答案、避免冗长铺垫的技能工具，主打适合 ADHD 用户的简洁输出。项目基于 Python，已获得约 3.2 万星标。

**OpenAI/技能**
> OpenAI 推出了面向 Codex 的技能目录（Skills Catalog），使用 Python 语言开发。该项目在 GitHub 上已获得约 2.67 万星标和 1792 次 fork。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/openai/skills)   

**microsoft/markitdown**
> MarkItDown 是微软开源的 Python 工具，用于将各类文件和 Office 文档转换为 Markdown 格式。该项目在 GitHub 上已获得约 18 万星标和 1.3 万次复刻。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/microsoft/markitdown)   

### browser-use/browser-use

（注：这是一个 GitHub 仓库名称，通常保留原文不翻译。如果需要意译项目名称 "browser-use"，可译为"浏览器操控"。）

*browser-use/browser-use*
- 来源: GitHub Trending - Python \| [原文链接](https://github.com/browser-use/browser-use)
- browser-use 是一个基于 Python 的开源项目，可让 AI 智能体操作和使用浏览器。该项目在 GitHub 上广受欢迎，已获得约 11.4 万个星标和 1.25 万次分叉。

**The-Swarm-Corporation/AutoHedge 自动对冲**
> AutoHedge 是一个 Python 开源项目，利用群体智能和 AI 智能体来构建自主对冲基金，可在几分钟内自动完成市场分析、风险管理和交易执行。该项目已获得 5869 个星标和 850 次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/The-Swarm-Corporation/AutoHedge)   

**免费电视/网络电视**
> 这是一个提供免费电视频道 M3U 播放列表的开源项目，使用 Python 开发。该项目在 GitHub 上已获得 20448 个星标和 2958 次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/Free-TV/IPTV)   

**TauricResearch/交易智能体**
> TradingAgents 是一个基于多智能体大语言模型的金融交易框架，采用 Python 开发。该项目在 GitHub 上广受欢迎，获得超过 10 万个星标和近 2 万次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/TauricResearch/TradingAgents)   

**HexStrike AI**
> HexStrike AI MCP Agents 是一款高级 MCP 服务器，可让 Claude、GPT、Copilot 等 AI 智能体自主调用 150 多种网络安全工具。它支持自动化渗透测试、漏洞发现、漏洞赏金自动化及安全研究，将大语言模型与实际攻防能力无缝对接。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/0x4m4/hexstrike-ai)   

**HKUDS/Vibe-Trading**
> Vibe-Trading 是一个用 Python 开发的个人交易智能体项目。该项目在 GitHub 上广受欢迎，已获得约 3.3 万星标和 5385 次 fork。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/HKUDS/Vibe-Trading)   

### PostHog/posthog

（此为项目名称，通常保留原文不翻译。）

*PostHog/posthog*
- 来源: GitHub Trending - Python \| [原文链接](https://github.com/PostHog/posthog)
- PostHog 是一个用于构建自动化产品的开发者平台，集成了 AI 可观测性、数据分析、会话回放、功能标记、A/B 实验、错误追踪和日志等工具。它能捕获 AI 智能体诊断问题、发现机会所需的全部上下文，并支持通过 Slack、网页、桌面端或 MCP 进行统一操作。

**Open-Sora**
> Open-Sora 是一个开源项目，旨在让高效的视频生成技术普及化，人人皆可使用。该项目基于 Python 开发，已获得约 2.97 万星标和 3084 个分支。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/hpcaitech/Open-Sora)   

**AgriciDaniel/claude-ads**
> 一个面向 Claude Code 的付费媒体运营工具，支持 Google、Meta、YouTube、LinkedIn、TikTok 等 12 个广告平台。它提供基于数据源的审计、确定性评分、版本化的 JSON 报告，并通过权限控制来管理账户变更。该项目使用 Python 编写，已获 9080 星标。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/AgriciDaniel/claude-ads)   

**AI 工程从零开始**
> 这是一个名为「ai-engineering-from-scratch」的Python开源项目，主打从零开始学习AI工程。项目理念为"学习、构建、并交付给他人使用"，已获得超过5.3万星标和9千多次分叉，颇受开发者欢迎。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/rohitg00/ai-engineering-from-scratch)   

**freecad-mcp**
> FreeCAD MCP 是一个基于模型上下文协议（MCP）的服务器，使用 Python 开发。它可将 FreeCAD 与 AI 助手连接，实现通过 MCP 协议控制 FreeCAD。该项目已获得 2125 个星标和 280 次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/neka-nat/freecad-mcp)   

**k2-fsa/OmniVoice**
> OmniVoice 是一款支持 600 多种语言的高质量语音克隆文本转语音（TTS）工具。该项目使用 Python 开发，在 GitHub 上已获得约 1.08 万星标和 1696 次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/k2-fsa/OmniVoice)   

**Zie619/n8n-workflows**
> 这是一个收集了大量 n8n 工作流的开源项目，涵盖了作者从各处（包括 n8n 官网）搜集的工作流。该项目基于 Python，在 GitHub 上已获得约 5.6 万星标和 7600 次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/Zie619/n8n-workflows)   

**shareAI 实验室/学习 Claude Code**
> 这是一个名为 learn-claude-code 的开源项目，用 Python 从零构建了一个类似 Claude Code 的轻量级 AI agent 框架。其核心理念是"Bash 即一切"，强调通过命令行工具实现智能体能力。该项目已获得超过 7.6 万星标和 1.2 万次 fork。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/shareAI-lab/learn-claude-code)   

**体验实验室/体验**
> Experiential 是一个开源、零加价的模型网关，支持 BYOK、自托管及 1000 多种市场模型。它能从流量中学习，帮助降低成本、推荐更优模型，并训练出用户自有的专用模型。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/experientiallabs/experiential)   

## 📚 论文前沿 (5 篇)

**超越对错：评估大型语言模型的二阶社会推理能力**
> 该研究指出，以往AI对齐主要关注第一层级社会规范（判断行为是否可接受），却忽视了"元规范"——即预测谁会执行规范以及如何执行（如公开羞辱或监禁）。作者提出评估大型语言模型二阶社会推理能力的方法，考察模型能否理解人们在规则被打破时的反应机制。
📎 来源：arXiv - Artificial Intelligence \| 09-09 12:00 · [阅读原文](https://arxiv.org/abs/2609.05437)   

**CriticGen：作为可执行反馈的生成感知评估**
> CriticGen 是一个细粒度、生成感知的评估框架，将模型评估转化为可指导答案改进的实用控制手段。它会针对每个样本生成特定的评估维度和评分标准，从而克服现有评估方法粗粒度、与生成脱节、只能提供泛泛解释的缺陷。
📎 来源：arXiv - Artificial Intelligence \| 09-09 12:00 · [阅读原文](https://arxiv.org/abs/2609.05439)   

**记忆何时有用？工具使用型大语言模型智能体中长期记忆的成本感知评估**
> MERIT 是一个新基准和测试框架，用于评估长期记忆对执行工具调用任务的 LLM 智能体的边际效用，并引入了显式的成本核算。与现有仅测量对话历史问答能力的记忆基准（如 LoCoMo、LongMemEval）不同，MERIT 关注记住的事实是否真正改变了智能体的行为。
📎 来源：arXiv - Artificial Intelligence \| 09-09 12:00 · [阅读原文](https://arxiv.org/abs/2609.05441)   

**AutoFyn 技术报告：面向长程智能体的非参数化专家迭代**
> AutoFyn 是一个受专家迭代算法启发的智能体框架，它通过更新持久化状态（而非模型权重）来适配冻结模型，依靠验证奖励信号进行多轮迭代。每轮从全新的模型会话开始，仅通过持久内存文件、报告和仓库状态等显式接口引入持久信息。在每轮内部，编排器负责探索、规划和构建。
📎 来源：arXiv - Artificial Intelligence \| 09-09 12:00 · [阅读原文](https://arxiv.org/abs/2609.05446)   

**面向视觉与语言Transformer的损伤感知Bandit剪枝**
> 该研究将Transformer的结构化剪枝问题建模为损伤感知的多臂老虎机问题，在固定评估预算下选择可移除的功能单元（注意力头和MLP通道组）。方法通过在校准数据上临时屏蔽单元，测量其相对基线损失的"配对损伤"来指导剪枝决策，从而在有限的候选评估预算内实现性能退化最小的语言和视觉Transformer压缩。
📎 来源：arXiv - Artificial Intelligence \| 09-09 12:00 · [阅读原文](https://arxiv.org/abs/2609.05448)   

---
