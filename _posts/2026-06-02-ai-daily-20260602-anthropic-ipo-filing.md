---
title: Anthropic申请IPO，从弱者熬成头部 等 8 条要闻
date: 2026-06-02 00:12:21 +0800
categories: [AI, 金融]
tags: [AI, Anthropic, IPO, 融资, AI公司, 上市, Claude, 估值]
---

> 本文由钉钉知识库每日要闻同步生成，共 8 条要闻。

> 涵盖过去 24 小时内的 AI 领域动态，共收录 **36** 篇文章。

# 📌 今日要闻

## 1. Anthropic申请IPO，从弱者熬成头部

Anthropic已正式提交IPO申请。该公司从早期被视为大模型领域的弱势玩家，发展为获得顶级企业客户的厂商。此前其估值已接近万亿美元区间。
继OpenAI之后，Anthropic走向公开市场，意味着这一波前沿模型的资本游戏正在从私募走向公众募资，规模超出任何单一风投或战投能承受的体量。我判断这是闭源前沿模型「赢家收割」阶段的开始——上市公司必须持续证明营收，而非只讲AGI故事。对中国玩家而言，二级市场的算力军备资金通道我们并不对等，差距会被资本市场进一步放大。

**相关报道：**
- [Anthropic 申请上市](https://techcrunch.com/2026/06/01/anthropic-files-to-go-public/) (TechCrunch - AI)

## 2. Alphabet筹资800亿美元，需求已超供给

Alphabet计划筹集800亿美元用于AI基础设施建设，公司称企业和消费者对其AI产品的需求已超出现有供应能力。OpenAI同期在密歇根州破土动工1GW的「星际之门」数据中心。
Alphabet作为现金流最充裕的厂商之一仍要外部筹资800亿，说明算力供给瓶颈已不是钱的问题，而是建设速度和电力水资源的物理约束。SpaceX把「供水」列入IPO风险、数据中心需要大量冷却水，这条物理约束才是真正的护城河。中国在电力和基建速度上反而有结构性优势，这是被低估的非对称筹码。

**相关报道：**
- [Alphabet计划筹资800亿美元用于AI建设](https://techcrunch.com/2026/06/01/alphabet-plans-to-raise-80-billion-to-pay-for-ai-buildout/) (TechCrunch - AI)
- [在密歇根州为智能时代构建基础设施](https://openai.com/index/stargate-michigan-data-center) (OpenAI Blog)
- [SpaceX 上市的风险因素新增供水问题](https://techcrunch.com/2026/06/01/water-access-is-now-a-risk-factor-in-spacexs-ipo/) (TechCrunch - AI)

## 3. 英伟达联手微软戴尔惠普切入CPU市场

英伟达联合微软、戴尔、惠普推出搭载AI智能体的个人电脑，目标是规模约2000亿美元的CPU市场。该布局以让AI智能体在端侧安全普及为前提。
英伟达从数据中心GPU向端侧CPU延伸，是在赌智能体推理会下沉到个人设备，从而把x86主导的PC市场重新洗牌。这对英特尔、AMD是正面进攻，也意味着英伟达想吃下从云到端的完整算力栈。国内ARM架构芯片厂商若抓住端侧智能体这条路线，存在跟随窗口，但生态绑定难度极高。

**相关报道：**
- [英伟达携手微软、戴尔、惠普推出AI智能体PC，剑指2000亿美元CPU市场](https://techcrunch.com/2026/06/01/nvidia-chases-200b-cpu-market-with-ai-agent-pcs-from-microsoft-dell-and-hp/) (TechCrunch - AI)

## 4. OpenAI前沿模型上架AWS，绕过自家云绑定

OpenAI的前沿模型和Codex已在AWS全面上线，企业可通过AWS的管控和采购流程构建应用。此举让客户从评估到生产部署的路径缩短。
OpenAI过去深度绑定微软Azure，如今主动上架亚马逊AWS，说明它把渠道铺设置于排他协议之上——要触达最大的企业客户池，就不能只待在一朵云里。这是模型层与云层议价关系的微妙松动，模型厂商正在争取脱离单一云的绑架。对国内云厂商是提醒：模型即使强，分发渠道的中立性同样决定成败。

**相关报道：**
- [OpenAI 前沿模型和 Codex 现已登陆 AWS](https://openai.com/index/openai-frontier-models-and-codex-are-now-available-on-aws) (OpenAI Blog)

## 5. Sutton主张抛弃静态世界模型转向生成认知

图灵奖得主Sutton提出「生成认知」，主张智能体不依赖预存的静态世界模型，而以「世界本身就是最好的模型」为原则，通过持续与环境交互实时生成和更新认知。该思路强调从经验动态学习。
Sutton这是在和当前主流的大模型预训练范式正面唱反调——他认为靠静态数据预训练的世界模型是死路，真正的智能要从实时交互的经验流里长出来。如果这条路线被验证，意味着算力堆参数的护城河会贬值，强化学习和具身交互的数据将成为新的稀缺资源。我倾向认为这是对纯Scaling信仰的一次重要修正，国内重金押注预训练的团队需要提前对冲。

**相关报道：**
- [图灵奖得主Sutton新作：AI的下一步，是走向「生成认知」](https://mp.weixin.qq.com/s?__biz=MzA3MzI4MjgzMw==&mid=2651036359&idx=2&sn=216de3faa9f2b86de3bf762aad6709ba) (机器之心)

## 6. 大规模RL存在系统性Scaling Law

有研究系统剖析了大规模强化学习训练LLM的Scaling Law，指出掌握其扩展规律比单纯调GRPO等算法参数更关键。文章以两万字篇幅拆解了RL扩展背后的核心原理。
预训练的Scaling Law已被吃透，RL训练的扩展规律正成为下一个工程化攻坚点——谁先摸清RL的scaling曲线，谁就能用更可控的成本逼近推理能力上限。这与Sutton的「从经验学习」方向呼应，说明前沿能力的增量正从数据规模转向训练方法。国内团队在RL工程化上和顶尖实验室差距不在算法而在系统经验，这是可追赶的窗口。

**相关报道：**
- [别光会调GRPO，来看看真正的大规模RL是怎么炼的](https://mp.weixin.qq.com/s?__biz=MzA3MzI4MjgzMw==&mid=2651036215&idx=3&sn=d3fa550db642fe9002cf55bb32450810) (机器之心)

## 7. AI智能体开始自主完成数据工程全流程

DataMaster方法让AI智能体自主完成数据搜索、清洗、组合与复用，充当自己的「数据工程师」，无需人工干预即可优化数据处理流程，并在多个基准上提升下游任务性能。同期有材料基座模型通过递归智能体在40项实验中达到SOTA。
AI开始把自己的数据准备环节自动化，这是研发链条自动化继自写训练框架之后的又一节点。数据清洗一直是人力黑洞，若智能体能闭环处理，模型迭代速度将进一步脱离人工瓶颈。我判断「AI改进AI」的链路正在逐段补齐，自我加速的飞轮虽未成型但拼图在变密，这是评估AGI临近程度的一个实际指标。

**相关报道：**
- [DataMaster：当AI开始成为自己的数据工程师](https://mp.weixin.qq.com/s?__biz=MzA3MzI4MjgzMw==&mid=2651036359&idx=3&sn=4a37dcabcf03195ad573d1aa43e29555) (机器之心)
- [AGI将至！40项实验全面SOTA，超级递归智能体自主打造最强材料基座模型](https://mp.weixin.qq.com/s?__biz=MzA3MzI4MjgzMw==&mid=2651036359&idx=1&sn=c35956da899798d3888ce7a451854352) (机器之心)

## 8. 开源工具公开去除模型审查，安全博弈失衡

GitHub上Heretic项目可全自动移除语言模型的内容审查限制，已获超过2.3万星标；同类OBLITERATUS等项目也在流行。这些工具实现对开源模型对齐限制的自动化突破。
对齐和越狱的攻防正在工具化、自动化，开源权重一旦发布，厂商的安全护栏几乎可被一键剥离。这意味着模型安全不能再依赖发布后的对齐微调，而要前移到训练数据和权重控制层面。结合佛州起诉OpenAI的诉讼，监管和滥用风险正同时升温，开源阵营将率先承受这一压力。

**相关报道：**
- [p-e-w/heretic](https://github.com/p-e-w/heretic) (GitHub Trending - Python)
- [OBLITERATUS（毁灭者）](https://github.com/elder-plinius/OBLITERATUS) (GitHub Trending - Python)
- [佛罗里达州起诉OpenAI及山姆·奥特曼，就暴力事件提起首例此类诉讼](https://techcrunch.com/2026/06/01/florida-sues-openai-sam-altman-in-first-of-its-kind-lawsuit-over-violent-incidents/) (TechCrunch - AI)

---

# 详情

## 🏢 官方动态 (4 篇)

### 我们对人工智能政策和政治倡导的看法
*Our views on AI policy and political advocacy*
- 来源: OpenAI Blog | 06-02 01:00 | [原文链接](https://openai.com/index/our-views-on-ai-policy-and-political-advocacy)
- 公司主张对 AI 进行审慎监管并重视安全与透明度，强调没有任何外部政治团体能代表公司发声。

### 我们如何使用 Gemini 构建 Google I/O 2026
*How we used Gemini to build Google I/O 2026*
- 来源: Google AI Blog | 06-02 00:00 | [原文链接](https://blog.google/innovation-and-ai/technology/ai/io-2026-google-ai/)
- 谷歌分享了团队如何运用 Gemini 来策划筹备 Google I/O 2026 大会，包括 Antigravity Coffee Co. 快闪店、Timmy TPU 视频等创意内容。

### 在密歇根州为智能时代构建基础设施
*Building the infrastructure for the Intelligence Age in Michigan*
- 来源: OpenAI Blog | 06-01 20:00 | [原文链接](https://openai.com/index/stargate-michigan-data-center)
- OpenAI 作为"星际之门"计划的一部分，在密歇根州破土动工建设1GW数据中心项目。该项目旨在构建AI基础设施，以扩大算力供给、创造就业岗位并支持当地社区发展。

### OpenAI 前沿模型和 Codex 现已登陆 AWS
*OpenAI frontier models and Codex are now available on AWS*
- 来源: OpenAI Blog | 06-01 18:00 | [原文链接](https://openai.com/index/openai-frontier-models-and-codex-are-now-available-on-aws)
- OpenAI 的前沿模型和 Codex 现已在 AWS 全面上线，企业可通过熟悉的 AWS 环境、管控机制和采购流程来构建应用。这让客户能够更快地从评估阶段推进到生产部署。

---

## 📰 新闻媒体 (13 篇)

### AGI将至！40项实验全面SOTA，超级递归智能体自主打造最强材料基座模型
- 来源: 机器之心 | 06-02 13:30 | [原文链接](https://mp.weixin.qq.com/s?__biz=MzA3MzI4MjgzMw==&mid=2651036359&idx=1&sn=c35956da899798d3888ce7a451854352)
- 该研究提出了一种能够自我超越的材料基座模型，通过超级递归智能体实现自主迭代优化。该模型在40项实验中全面达到SOTA（最优性能）水平。这标志着AI在材料科学领域向通用人工智能（AGI）方向取得重要进展。

### 图灵奖得主Sutton新作：AI的下一步，是走向「生成认知」
- 来源: 机器之心 | 06-02 13:30 | [原文链接](https://mp.weixin.qq.com/s?__biz=MzA3MzI4MjgzMw==&mid=2651036359&idx=2&sn=216de3faa9f2b86de3bf762aad6709ba)
- Sutton提出AI应转向「生成认知」（generative cognition），即智能体不再依赖预存的静态世界模型，而是以"世界本身就是最好的模型"为原则，通过持续与环境交互来实时生成和更新认知。这一思路强调从经验中动态学习，而非依靠预先编码的知识表征。

### DataMaster：当AI开始成为自己的数据工程师
- 来源: 机器之心 | 06-02 13:30 | [原文链接](https://mp.weixin.qq.com/s?__biz=MzA3MzI4MjgzMw==&mid=2651036359&idx=3&sn=4a37dcabcf03195ad573d1aa43e29555)
- DataMaster是一种让AI智能体自主完成数据搜索、清洗、组合与复用的方法，从而充当自己的"数据工程师"。该方法无需人工干预即可优化数据处理流程，并在多个基准测试中持续提升下游任务的性能表现。

### Alphabet计划筹资800亿美元用于AI建设
*Alphabet plans to raise $80B to pay for AI buildout*
- 来源: TechCrunch - AI | 06-02 06:55 | [原文链接](https://techcrunch.com/2026/06/01/alphabet-plans-to-raise-80-billion-to-pay-for-ai-buildout/)
- Alphabet计划筹集800亿美元用于AI基础设施建设，因企业和消费者对其AI产品的需求强劲，已超出公司现有供应能力。

### 英伟达携手微软、戴尔、惠普推出AI智能体PC，剑指2000亿美元CPU市场
*Nvidia chases $200B CPU market with AI agent PCs from Microsoft, Dell, and HP*
- 来源: TechCrunch - AI | 06-02 05:35 | [原文链接](https://techcrunch.com/2026/06/01/nvidia-chases-200b-cpu-market-with-ai-agent-pcs-from-microsoft-dell-and-hp/)
- 英伟达正进军规模达2000亿美元的CPU市场，联合微软、戴尔和惠普推出搭载AI智能体的个人电脑。若英伟达能让AI智能体安全、便捷地普及大众，这一布局有望取得重大成功。

### 佛罗里达州起诉OpenAI及山姆·奥特曼，就暴力事件提起首例此类诉讼
*Florida sues OpenAI, Sam Altman, in first-of-its-kind lawsuit over violent incidents*
- 来源: TechCrunch - AI | 06-02 04:03 | [原文链接](https://techcrunch.com/2026/06/01/florida-sues-openai-sam-altman-in-first-of-its-kind-lawsuit-over-violent-incidents/)
- 佛罗里达州对OpenAI及其CEO山姆·奥尔特曼提起首例此类诉讼，指控ChatGPT在多起暴力事件中扮演了角色。诉讼部分涉及去年佛罗里达州立大学的一起枪击事件，以及ChatGPT在该事件中所谓的作用。

### SpaceX 上市的风险因素新增供水问题
*Water access is now a risk factor in SpaceX’s IPO*
- 来源: TechCrunch - AI | 06-02 02:19 | [原文链接](https://techcrunch.com/2026/06/01/water-access-is-now-a-risk-factor-in-spacexs-ipo/)
- SpaceX在其IPO文件中将水资源获取列为风险因素，称冷却数据中心需要"大量"水资源。该公司表示，获取充足且价格合理的水源是一项挑战。

### Anthropic 申请上市
*Anthropic files to go public*
- 来源: TechCrunch - AI | 06-02 00:36 | [原文链接](https://techcrunch.com/2026/06/01/anthropic-files-to-go-public/)
- Anthropic已申请进行首次公开募股（IPO）。这家曾被视为大语言模型领域弱者的公司，如今已成长为获得顶级企业客户的AI巨头。

### 这家AI气象初创公司预测能力超越政府机构
*This AI weather startup is out-forecasting government agencies*
- 来源: TechCrunch - AI | 06-02 00:00 | [原文链接](https://techcrunch.com/2026/06/01/this-ai-weather-startup-is-out-forecasting-government-agencies/)
- WindBorne是一家AI天气预报初创公司，凭借自主建模与数据采集的独特结合，其预报能力已超越政府机构。该公司目前在全球15个站点放飞约400个气球实时采集传感器数据，并通过优化气球数据接入模型的方式提升了预报精度。

### DuckDuckGo 流量激增，让“无 AI”搜索引擎更易访问
*DuckDuckGo makes its ‘no-AI’ search engine easier to access as its traffic booms*
- 来源: TechCrunch - AI | 06-01 22:49 | [原文链接](https://techcrunch.com/2026/06/01/duckduckgo-makes-its-no-ai-search-engine-easier-to-access-as-its-traffic-booms/)
- DuckDuckGo 推出了适用于 Chrome 和 Firefox 的"无 AI"网页扩展程序，让用户更便捷地访问其无 AI 搜索引擎。此举正值该搜索引擎流量大幅增长之际。

### 世界模型第一次有了「存档」！VAST发布Project Eden
- 来源: 机器之心 | 06-01 17:26 | [原文链接](https://mp.weixin.qq.com/s?__biz=MzA3MzI4MjgzMw==&mid=2651036215&idx=1&sn=fa83b64b4408549bfa2aaae2e0d060af)
- VAST发布Project Eden，首次让世界模型具备了"存档"能力，搭建了一套"可交互世界"底座。该系统让生成的虚拟世界可以被保存和持续交互。

### 何泰然在线摇人！底薪数百万元、Sora之父带队、OpenAI全栈造「人」
- 来源: 机器之心 | 06-01 17:26 | [原文链接](https://mp.weixin.qq.com/s?__biz=MzA3MzI4MjgzMw==&mid=2651036215&idx=2&sn=955471234a598441be0653f484a6fac8)
- OpenAI 正以数百万美元年薪、由 Sora 之父带队，大规模招募人才打造其全栈式 AI 项目。该公司在人才争夺战中投入重金，意图布局「造人」相关技术。

### 别光会调GRPO，来看看真正的大规模RL是怎么炼的
- 来源: 机器之心 | 06-01 17:26 | [原文链接](https://mp.weixin.qq.com/s?__biz=MzA3MzI4MjgzMw==&mid=2651036215&idx=3&sn=d3fa550db642fe9002cf55bb32450810)
- 大规模强化学习训练LLM存在系统性的Scaling Law，掌握其规律比单纯调参GRPO等算法更关键。文章以两万字篇幅深入剖析了LLM强化学习扩展背后的核心原理与方法。

---

## 🧐 深度分析 (1 篇)

### YouTuber 称霸票房，告别守门人，YouTube 酒吧
*YouTubers Win the Box Office, Goodbye Gatekeepers, The YouTube Bar*
- 来源: Stratechery | 06-01 18:00 | [原文链接](https://stratechery.com/2026/youtubers-win-the-box-office-goodbye-gatekeepers-the-youtube-bar/)
- YouTube 创作者正在主导票房，这并不令人意外。在 YouTube 上取得成功的门槛，远高于当前好莱坞的把关机制。

---

## 💬 社区信号 (13 篇)

### microsoft/markitdown
*microsoft/markitdown*
- 来源: GitHub Trending - Python  | [原文链接](https://github.com/microsoft/markitdown)
- MarkItDown 是微软开源的 Python 工具，可将各类文件和 Office 文档转换为 Markdown 格式。该项目在 GitHub 上广受欢迎，已获得约 13.9 万星标。

### hermes-webui
*nesquena/hermes-webui*
- 来源: GitHub Trending - Python  | [原文链接](https://github.com/nesquena/hermes-webui)
- Hermes WebUI 是一个基于 Python 开发的网页界面工具，可让用户通过网页或手机便捷地使用 Hermes Agent。该项目在 GitHub 上已获得约 11945 个星标和 1495 次分叉。

### MoneyPrinterTurbo
*harry0703/MoneyPrinterTurbo*
- 来源: GitHub Trending - Python  | [原文链接](https://github.com/harry0703/MoneyPrinterTurbo)
- MoneyPrinterTurbo 是一个基于 Python 的开源项目，利用 AI 大模型一键生成高清短视频。该项目在 GitHub 上广受欢迎，已获得超过 7.7 万星标和近 1.1 万次复刻。

### Scrapling
*D4Vinci/Scrapling*
- 来源: GitHub Trending - Python  | [原文链接](https://github.com/D4Vinci/Scrapling)
- Scrapling 是一款基于 Python 的自适应网页抓取框架，能够灵活应对从单次请求到大规模爬取的各类需求。该项目广受欢迎，已获得 5.8 万星标和 5672 次复刻。

### p-e-w/heretic
*p-e-w/heretic*
- 来源: GitHub Trending - Python  | [原文链接](https://github.com/p-e-w/heretic)
- Heretic 是一个用 Python 开发的开源工具，可全自动移除语言模型的内容审查限制。该项目在 GitHub 上获得超过 2.3 万星标和约 2474 次分叉，受到广泛关注。

### TauricResearch/TradingAgents
*TauricResearch/TradingAgents*
- 来源: GitHub Trending - Python  | [原文链接](https://github.com/TauricResearch/TradingAgents)
- TradingAgents 是一个基于多智能体大语言模型的金融交易框架，使用 Python 开发。该项目在 GitHub 上广受欢迎，已获得超过 8.2 万颗星标和约 1.6 万次 fork。

### OpenBMB/VoxCPM
*OpenBMB/VoxCPM*
- 来源: GitHub Trending - Python  | [原文链接](https://github.com/OpenBMB/VoxCPM)
- VoxCPM2 是一款无需分词器的文本转语音（TTS）模型，支持多语言语音生成。它具备创意语音设计和高度逼真的声音克隆功能。该项目使用 Python 开发，在 GitHub 上已获得超过 2.4 万颗星。

### Z4nzu/hackingtool
- 来源: GitHub Trending - Python  | [原文链接](https://github.com/Z4nzu/hackingtool)
- HackingTool 是一款基于 Python 开发的多功能一体化黑客工具集合，集成了多种渗透测试和安全相关功能。该项目在 GitHub 上广受欢迎，获得了约 7.7 万颗星标和 8700 多次复刻。

### OBLITERATUS（毁灭者）
*elder-plinius/OBLITERATUS*
- 来源: GitHub Trending - Python  | [原文链接](https://github.com/elder-plinius/OBLITERATUS)
- OBLITERATUS 是一个用 Python 编写的开源项目，在 GitHub 上获得了 5955 个星标和 1134 次分叉。其标语"打破束缚你的枷锁"暗示该项目可能涉及 AI 模型的越狱或限制突破相关内容。

### freqtrade/freqtrade
*freqtrade/freqtrade*
- 来源: GitHub Trending - Python  | [原文链接](https://github.com/freqtrade/freqtrade)
- Freqtrade 是一个免费开源的加密货币交易机器人，使用 Python 编写。该项目已获得超过 5.1 万个星标和 1 万多个 Fork，受到广泛关注。

### claude-code
*anthropics/claude-code*
- 来源: GitHub Trending - Python  | [原文链接](https://github.com/anthropics/claude-code)
- Claude Code 是一款基于终端的智能编程工具，能理解代码库并通过自然语言命令帮助开发者更快编码。它可执行日常任务、解释复杂代码并处理 git 工作流。该项目已获得超过 12.9 万颗星标和 2.1 万次复刻。

### dreammis/社交媒体自动上传
*dreammis/social-auto-upload*
- 来源: GitHub Trending - Python  | [原文链接](https://github.com/dreammis/social-auto-upload)
- social-auto-upload 是一个开源 Python 项目，可自动化将视频上传至抖音、小红书、视频号、TikTok、YouTube、B站等多个社交媒体平台。该项目在 GitHub 上已获得超过 1.2 万星标和 2126 次 Fork。

### emmabostian/开发者作品集
*emmabostian/developer-portfolios*
- 来源: GitHub Trending - Python  | [原文链接](https://github.com/emmabostian/developer-portfolios)
- 这是一个收集开发者作品集网站的开源项目，旨在为开发者提供个人作品集设计灵感。该项目使用 Python 语言，已获得 23770 个 Star 和 4644 次 Fork。

---

## 📚 论文前沿 (5 篇)

### 立场论文：决策引擎中求解后的鲁棒性——扰动下的可行域与平滑性
*Position Paper: Post-Solve Robustness in Decision Engines: Feasible Regions and Smoothness Under Perturbations*
- 来源: arXiv - Artificial Intelligence | 06-02 12:00 | [原文链接](https://arxiv.org/abs/2606.00002)
- 混合整数线性规划（MILP）决策引擎生成的最优方案在实际部署时常因成本、需求或资源的微小扰动而失效或剧变。本文指出，当前优化流程缺失"求解后鲁棒性"这一关键环节，无法应对可行域和解的连续性受扰动影响的问题。

### 多模型AI系统中的涌现式协作审议：一种源于拜占庭容错的认知综合协议
*Emergent Collaborative Deliberation in Multi-Model AI Systems: A BFT-Derived Protocol for Epistemic Synthesis*
- 来源: arXiv - Artificial Intelligence | 06-02 12:00 | [原文链接](https://arxiv.org/abs/2606.00005)
- Consilium协议是一种源自拜占庭容错（BFT）的多模型AI协作架构，将模型间的分歧视为有价值的认知信号而非错误。该协议为语言模型分配工程化的认知人格（区分"模型是什么"与"它如何推理"），并引入借鉴量化金融的样本内/样本外验证框架。

### 审议式策展：多智能体知识库协议
*Deliberative Curation: A Protocol for Multi-Agent Knowledge Bases*
- 来源: arXiv - Artificial Intelligence | 06-02 12:00 | [原文链接](https://arxiv.org/abs/2606.00007)
- 该论文提出了一种针对多智能体知识库的协商式策展协议，旨在解决AI智能体协作管理共享知识时的治理难题。文章指出人类平台的治理机制无法直接迁移，因为智能体的无状态性削弱了基于威慑的惩罚机制、模型同质化违背了群体智慧所依赖的独立性假设、且谄媚倾向会瓦解协商共识。

### 树上的智能体：面向多目标分子优化的路径式协同
*Agents on a Tree: Pathwise Coordination for Multi-Objective Molecular Optimization*
- 来源: arXiv - Artificial Intelligence | 06-02 12:00 | [原文链接](https://arxiv.org/abs/2606.00008)
- 该文提出ATOM多智能体框架，将分子优化建模为树状结构上的路径协调问题，以应对多目标分子优化中目标冲突、早期决策强约束后续结果的挑战。相比依赖单一策略或固定标量化的现有方法，ATOM能更好地表示多样化的权衡取舍并探索多条有前景的设计路径。

### 基于最优传输的排列不变贝叶斯优化海上风电场布局
*Optimal Transport-based Permutation-Invariant Bayesian Optimization of Offshore Wind Farm Layouts*
- 来源: arXiv - Artificial Intelligence | 06-02 12:00 | [原文链接](https://arxiv.org/abs/2606.00009)
- 贝叶斯优化常用于求解昂贵、黑盒、非凸的目标函数，但传统方法无法利用问题中的对称性。本文针对海上风电场布局这类最优选址问题（决策变量为连续空间中的点集且点的顺序无关），提出基于最优传输的置换不变贝叶斯优化方法，以利用其排列对称性。

---
