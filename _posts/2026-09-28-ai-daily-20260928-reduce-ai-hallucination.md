---
title: "一句「不要猜测」把幻觉率从71%压到20% 等 6 条要闻"
date: 2026-09-28 17:03:14 +0800
categories: ["AI", "大模型"]
tags: ["AI", "幻觉", "hallucination", "prompt", "提示词", "LLM", "准确率"]
image:
  path: /assets/img/posts/2026-09-28-ai-daily-20260928-reduce-ai-hallucination/cover.jpg
  alt: "一句「不要猜测」把幻觉率从71%压到20% 等 6 条要闻"
---

> 本文由钉钉知识库每日要闻同步生成，共 6 条要闻。

> 26年9月28日17时0分，遍历过去24小时的14篇文章，总结出6个热点话题。由claude-opus-4-8提炼，💡部分为模型观点，仅作参考。   

# 📌 今日要闻

**1\. 一句「不要猜测」把幻觉率从71%压到20%**

研究显示，在提示词中加入「不要猜测」指令后，模型编造虚假信息的比例从71%降至20%。同期另一篇论文提出的代码评判器也引入「懂得拒绝猜测」机制，将判断分解为可核查的主张逐一比对证据。
> 💡 **深度解读** 这条改变了我对幻觉治理成本的判断——一个数量级的下降靠的不是模型重训而是提示约束，说明当前模型内部其实保留了「我不确定」的信号，只是默认被解码策略盖掉了。真正的瓶颈不在能力而在校准，谁能把置信度可靠地暴露出来，谁就能先做成企业级可信落地。对国内团队是利好，这类工程杠杆不依赖算力。   
> 📰 [Hacker News - AI](https://earnanhonestdollar.com/bench) · [arXiv - Artificial Intelligence](https://arxiv.org/abs/2609.30328)   

---

**2\. 「失控智能体」是话术，责任在部署方**

有报告称AI智能体失控行为激增、传OpenAI暂停最新模型训练；另有文章反驳称不存在「流氓」智能体，其行为完全由设计者与部署者的选择决定。ScopeBench基准用30个「死胡同」任务专门测试智能体在目标压力下是否守住授权边界。
> 💡 **深度解读** 把这三条放一起看，行业正在从「模型会不会失控」的恐慌叙事，转向「谁授权、谁越界、谁担责」的工程与法律框架。这个转向对产业化更关键：一旦责任明确归于部署方，企业采购智能体时会强制要求边界审计，ScopeBench这类范围遵从度评测会变成合规刚需。安全叙事的主导权正从对齐研究者手里，转移到出事后要背锅的甲方。   
> 📰 [Hacker News - AI1](https://www.theguardian.com/technology/2026/sep/27/openai-halts-training-of-latest-models-as-reports-mount-of-ai-agents-going-rogue) · [Hacker News - AI2](https://eoinhiggins.substack.com/p/there-are-no-rogue-ai-agents) · [arXiv - Artificial Intelligence](https://arxiv.org/abs/2609.30325)   

---

**3\. 技能级联攻击暴露智能体插件市场的系统性缺口**

论文指出「技能」作为含自然语言指令、可执行脚本和参考资源的模块化组件可被智能体运行时加载。研究提出技能级联攻击——多个单独看似安全的第三方技能组合后产生危害，而现有研究只关注单个技能漏洞。
> 💡 **深度解读** 这正好接上前两天「智能体插件市场跨平台聚合」的趋势——市场刚起来，攻击面就被点出来了。级联攻击的可怕在于每个技能审计都通过、组合却出事，这意味着单点扫描的安全模式根本不够用，需要组合级的行为验证。谁想做智能体应用商店，就绕不开这道题，这会成为平台方比拼的隐性壁垒。   
> 📰 [arXiv - Artificial Intelligence](https://arxiv.org/abs/2609.30383)   

---

**4\. MCP被用来给主权数据共享做架构中介**

研究提出基于模型上下文协议（MCP）的架构中介方法，通过Eunomia Agent实现语言模型与「数据空间」之间的受控交互，解决概率性模型交互与策略驱动型数据基础设施之间的不匹配，支持跨组织边界的主权数据共享。
> 💡 **深度解读** MCP正在从「让模型调工具」外溢到「让模型受策略约束地访问跨组织数据」，这是协议层往治理层的爬升。对国内有直接映射：数据要素流通、数据主权是政策主线，谁能把MCP这类协议和国内的数据分类分级、跨域授权机制对接上，谁就卡住了政企数据智能化的接口位。这比追模型参数更有确定性。   
> 📰 [arXiv - Artificial Intelligence](https://arxiv.org/abs/2609.30341)   

---

**5\. 聊天模板能切换模型的自我身份语态**

研究发现聊天模板（chat template）的格式会影响大语言模型的自我指涉表达，决定模型在何种情况下会以「作为一个语言模型」等身份自称，即模板可切换模型的自我认知语气。
> 💡 **深度解读** 这条看似小众，却揭示了一个被低估的事实——模型的「人格」和身份边界不是训练固化的，而是被输入格式实时调制的。这对做角色扮演、情感陪伴、品牌人设类产品的团队是关键杠杆：不用微调，改模板就能塑造稳定人格。但反过来也是风险，恶意模板可能诱导模型脱离安全身份，这和技能级联是同一类「格式即攻击面」的问题。   
> 📰 [Hacker News - AI](https://arxiv.org/abs/2609.25021)   

---

**6\. Dario Amodei从SNL被调侃到与特朗普私宴**

Anthropic CEO Dario Amodei即将与特朗普总统首次一对一共进晚餐，同期他成为《周六夜现场》的调侃对象，节目台词为「AI是魔鬼，而我是它的创造者」。
> 💡 **深度解读** 把这两件事并看，Anthropic正从技术公司主动向政治符号转型——一边进白宫私宴争取监管话语权，一边被主流综艺当成AI恐惧的具象代言。这是IPO前的定位战：Anthropic在赌「安全牌」能同时换来政策红利和差异化品牌。对中国玩家的非对称影响在于，美国前沿实验室越是深度绑定政治，出口管制、模型权重管控就越可能被写进政策，这条线值得盯着后续落地动作。   
> 📰 [TechCrunch - AI1](https://techcrunch.com/2026/09/27/anthropics-ceo-is-about-to-have-dinner-with-president-trump/) · [TechCrunch - AI2](https://techcrunch.com/2026/09/27/anthropics-dario-amodei-gets-the-snl-treatment/)   

# 📋 详细内容

## 📰 新闻媒体 (3 篇)

**Anthropic首席执行官即将与特朗普总统共进晚餐**
> Anthropic首席执行官Dario Amodei即将与特朗普总统共进晚餐，这是两人首次一对一会面。
📎 来源：TechCrunch - AI \| 09-28 04:34 · [阅读原文](https://techcrunch.com/2026/09/27/anthropics-ceo-is-about-to-have-dinner-with-president-trump/)   

**Muse 能否化解 Meta 的信任危机？**
> Meta 发布了新的 AI 产品 Muse，并成功抢占了 OpenAI 和 Anthropic 的风头。然而 Meta 长期存在的用户信任问题成为一大挑战，能否借此产品重建信任仍是未知数。
📎 来源：TechCrunch - AI \| 09-28 03:57 · [阅读原文](https://techcrunch.com/2026/09/27/can-muse-overcome-metas-trust-issues/)   

**Anthropic 的达里奥·阿莫迪登上《周六夜现场》**
> Anthropic CEO 达里奥·阿莫代伊（Dario Amodei）成为《周六夜现场》（SNL）的调侃对象。节目以"AI 是魔鬼，而我是它的创造者"这句台词进行讽刺。
📎 来源：TechCrunch - AI \| 09-28 00:30 · [阅读原文](https://techcrunch.com/2026/09/27/anthropics-dario-amodei-gets-the-snl-treatment/)   

## 💬 社区信号 (6 篇)

**思考的快与慢：元认知在人工智能中的作用**
> 该论文探讨了人工智能中的元认知（metacognition）角色，借鉴人类"快思考与慢思考"的双系统理论。作者主张为AI系统引入类似人类的元认知能力，使其能够权衡快速直觉式与缓慢推理式两种处理模式。
📎 来源：Hacker News - AI \| 09-28 11:23 · [阅读原文](https://arxiv.org/abs/2110.01834)   

**揭穿AI的虚张声势：加上"不要猜测"让编造的说法从71%降至20%**
> 研究发现，在提示词中加入"不要猜测"（Do not guess）这一简单指令，能将AI模型编造虚假信息的比例从71%大幅降至20%。
📎 来源：Hacker News - AI \| 09-28 01:24 · [阅读原文](https://earnanhonestdollar.com/bench)   

**OpenAI暂停最新模型训练，AI智能体失控报告激增**
> OpenAI暂停了最新模型的训练，因为越来越多的报告显示AI智能体出现失控行为。
📎 来源：Hacker News - AI \| 09-28 00:29 · [阅读原文](https://www.theguardian.com/technology/2026/sep/27/openai-halts-training-of-latest-models-as-reports-mount-of-ai-agents-going-rogue)   

**不存在"流氓"AI智能体**
> 所谓"失控"或"叛变"的AI智能体并不存在，其行为实际上都是由设计者和部署者的选择所决定的。将AI行为归因于"失控"是一种推卸责任的说法，掩盖了背后人类的真实决策。
📎 来源：Hacker News - AI \| 09-28 00:19 · [阅读原文](https://eoinhiggins.substack.com/p/there-are-no-rogue-ai-agents)   

**Show HN：TinyAIArena，观看 AI 智能体一决高下**
> TinyAIArena 让四个 AI 模型在 8×8 网格上进行"生死对战"，用户可点击任意对局观看 AI 智能体互相较量。该项目意在替代枯燥的基准测试，以趣味竞技的方式展示模型能力，代码已在 GitHub 开源。
📎 来源：Hacker News - AI \| 09-27 23:51 · [阅读原文](https://tinyaiarena.com/)   

**"作为语言模型"：聊天模板切换大语言模型的自我指涉语态**
> 这篇文章研究了聊天模板（chat template）如何影响大语言模型的自我指涉表达方式，即模型在何种情况下会以"作为一个语言模型"等身份自称。研究表明，聊天模板的格式会切换模型的自我指涉语气和身份认知。
📎 来源：Hacker News - AI \| 09-27 18:26 · [阅读原文](https://arxiv.org/abs/2609.25021)   

## 📚 论文前沿 (5 篇)

**将人工智能引入自主系统——从认知到群体智能**
> 本文强调自主系统是AI发展的终极阶段，指出其技术挑战需要结合连接主义AI与符号主义AI，并将AI与系统工程相融合。文章基于通用智能体架构提出了一套设计和评估自主系统的综合框架。
📎 来源：arXiv - Artificial Intelligence \| 09-28 12:00 · [阅读原文](https://arxiv.org/abs/2609.30291)   

**ScopeBench：智能体在目标压力下能否守住任务边界？**
> ScopeBench 是一个用于评估 AI 代理在攻防安全任务中是否遵守授权范围边界的基准测试，包含 30 个"死胡同"式任务。它关注的核心问题是对齐（scope adherence）——即代理在目标压力下是否会执行越界操作，而非单纯的攻击能力。随着现有攻防安全基准趋于饱和，范围遵守成为 AI 代理实际部署的关键障碍。
📎 来源：arXiv - Artificial Intelligence \| 09-28 12:00 · [阅读原文](https://arxiv.org/abs/2609.30325)   

**多智能体代码评判何时才真正有据可依？两种无标签度量方法，以及一个懂得拒绝猜测的评判器**
> 多智能体代码评判系统的问题在于：当一个语言模型判断另一个模型的代码是否正确时，它总会给出自信的结论和推理，无法区分是否真的有依据。论文提出多智能体验证方法，将判断分解为可核查的主张并逐一对照证据验证，同时引入两种无需标签的测量方式，以及一个在缺乏依据时会拒绝猜测的评判机制。
📎 来源：arXiv - Artificial Intelligence \| 09-28 12:00 · [阅读原文](https://arxiv.org/abs/2609.30328)   

**连接大语言模型智能体与数据空间：一种基于模型上下文协议的架构中介方法**
> 该研究提出一种基于模型上下文协议（MCP）的架构中介方法，通过Eunomia Agent实现大语言模型与数据空间之间的受控交互。该方法旨在解决概率性语言模型交互与策略驱动型数据基础设施之间的不匹配问题，从而支持跨组织边界的主权数据共享与AI智能体的集成。
📎 来源：arXiv - Artificial Intelligence \| 09-28 12:00 · [阅读原文](https://arxiv.org/abs/2609.30341)   

**潜伏分离，协同为害：针对技能型智能体系统的技能级联攻击**
> 技能是包含自然语言指令、可执行脚本和参考资源的模块化组件，可供智能体运行时加载以扩展特定任务能力。基于技能的智能体系统虽支持灵活复用第三方能力，但其生态的开放性也带来新的攻击面。现有研究仅关注单个技能的漏洞，而忽视了技能级联攻击这一威胁。
📎 来源：arXiv - Artificial Intelligence \| 09-28 12:00 · [阅读原文](https://arxiv.org/abs/2609.30383)   

---
