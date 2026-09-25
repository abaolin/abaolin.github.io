---
title: "甲骨文对星际之门数据中心发出不可抗力通知 等 7 条要闻"
date: 2026-09-25 17:02:40 +0800
categories: ["AI", "算力"]
tags: ["AI", "Oracle", "Stargate", "数据中心", "OpenAI", "算力", "云计算", "不可抗力"]
image:
  path: /assets/img/posts/2026-09-25-ai-daily-20260925-oracle-stargate-force-majeure/cover.webp
  alt: "甲骨文对星际之门数据中心发出不可抗力通知 等 7 条要闻"
---

> 本文由钉钉知识库每日要闻同步生成，共 7 条要闻。

> 26年9月25日17时0分，遍历过去24小时的41篇文章，总结出7个热点话题。由claude-opus-4-8提炼，💡部分为模型观点，仅作参考。   

# 📌 今日要闻

**1\. 甲骨文对星际之门数据中心发出不可抗力通知**

甲骨文对其新墨西哥州的 Stargate 数据中心发出不可抗力通知，该条款允许其在设施未能于 2028 年如期上线时推迟付款。Stargate 是 OpenAI、软银与甲骨文联合推进的算力基建项目。
> 💡 **深度解读** 这是 Stargate 叙事第一次出现来自内部的裂缝。不可抗力通知本质是甲骨文在给自己留后路，说明这个万亿级算力承诺在工程和供应链层面正遭遇现实阻力。当美国头部算力基建都开始为延期做法律预案时，所谓「算力无限扩张」的确定性被打了折扣，对押注美国算力供给节奏的所有人都是一记提醒。   
> 📰 [TechCrunch - AI](https://techcrunch.com/2026/09/24/oracle-sends-force-majeure-notice-on-its-new-mexico-stargate-data-center/)   

---

**2\. 2-bit量化把基础模型压到8MB塞进微控制器**

开源项目 Needle 面向微型设备推出自动化基础模型，采用 2-bit 量化，体积仅 8-29 MB，支持工具调用、结构化数据提取与嵌入，可运行于手机、可穿戴、智能家居、机器人、汽车及微控制器。PrismML 同期把微型大语言模型部署到搭载高通芯片的智能眼镜。
> 💡 **深度解读** 端侧模型的下限正在被急速压低——不是压到手机，而是压到微控制器这一级别。这条路线一旦跑通，AI 能力将脱离云端和 API 成本约束，进入几乎零边际成本的硬件长尾。对中国厂商是利好：我们在硬件制造和端侧部署上有结构性优势，谁先把 8MB 模型做进量产设备，谁就绕开了对云端算力的依赖。   
> 📰 [GitHub Trending - Python](https://github.com/cactus-compute/needle) · [TechCrunch - AI](https://techcrunch.com/2026/09/24/prismml-brings-its-tiny-llms-to-qualcomm-powered-smart-glasses/)   

---

**3\. Lovable年化营收破6亿美元验证氛围编程规模化**

AI 应用生成平台 Lovable 年化营收突破 6 亿美元，其平台上创建的应用每月获得近十亿次访问量。联合创始人称 vibe coding（氛围编程）正快速兴起。
> 💡 **深度解读** 6 亿美元 ARR 加上十亿级月访问，说明 vibe coding 不再是 demo 阶段的玩具，而是有真实付费和真实流量支撑的商业模式。这条曲线的意义在于：它把「不会写代码的人也能造软件」从概念变成了可规模化的现金流。对国内做 low-code 和应用生成的玩家，这是一个已被证明的收入天花板参照，也是一次时间窗口的警告。   
> 📰 [TechCrunch - AI](https://techcrunch.com/2026/09/24/lovables-annualized-revenue-crosses-600m-as-vibe-coding-takes-off/)   

---

**4\. Ando让AI智能体拥有独立身份挑战Slack**

团队消息应用 Ando 面向 Slack 竞争，为 AI 智能体赋予独立身份和收件箱，使其像真人一样参与团队对话。同期 strands-agents 的 harness-sdk 提供构建生产级智能体的端到端控制工具，兼容任意模型和云平台。
> 💡 **深度解读** 把智能体当作有独立身份的团队成员来设计协作工具，这是组织形态层面的变化而非功能叠加。它假设未来企业内部的沟通对象里将常驻一批 AI 同事，这重构了协作软件的底层数据模型。对国内钉钉、飞书、企业微信是明确信号：谁先把智能体做成一等公民而非插件，谁就掌握下一代协作入口。   
> 📰 [TechCrunch - AI](https://techcrunch.com/2026/09/24/ando-eyes-slack-as-it-builds-team-messaging-platform-for-humans-and-agents-to-work-together/) · [GitHub Trending - Python](https://github.com/strands-agents/harness-sdk)   

---

**5\. 不含语言模型的路由器在时序预测超越智能体方案**

TW3Cast 在 GIFT-Eval 基准 130 个条目中按平均 MASE 排名第 3，位列其上的两个系统均依赖智能体或语言模型。TW3Cast 不使用任何智能体或 LLM，仅通过训练集一次性计算的冻结路由器选择轻度微调的基础模型。
> 💡 **深度解读** 这是对「万物皆可套 LLM」思路的一次冷静证伪。在结构化的时序预测任务上，一个不用大模型、成本极低的确定性路由方案能打到前三，说明智能体化并非在所有场景都带来净收益。作为编辑，我把这条留下来是提醒 CEO：在 AI 军备竞赛里保持对任务本质的判断，不该为了叙事而给一切场景强行加上模型。   
> 📰 [arXiv - Artificial Intelligence1](https://arxiv.org/abs/2609.28506) · [arXiv - Artificial Intelligence2](https://arxiv.org/abs/2609.28475)   

---

**6\. 澳大利亚就OpenAI入侵政府健康网站启动调查**

澳大利亚将调查 OpenAI 入侵政府健康网站的事件是否违法，这是首次已知影响政府机构的相关泄露事件，澳总理承诺追究 OpenAI 责任。
> 💡 **深度解读** 这是主权国家首次以政府机构受害者的身份，对一家 AI 巨头的数据抓取行为动用法律追责。它把 AI 公司的数据获取从灰色地带推向了国家级监管冲突。当爬取行为触及政府数据边界，各国的监管反应会明显收紧，OpenAI 这类依赖大规模抓取的公司未来在海外扩张将面临越来越高的合规成本。   
> 📰 [TechCrunch - AI](https://techcrunch.com/2026/09/24/australia-to-investigate-if-openai-hack-of-government-health-website-broke-the-law/)   

---

**7\. ElevenLabs主张AI客服须主动告知用户在与机器对话**

ElevenLabs 为大量客服电话提供 AI 语音技术，其 CEO 表示在 AI 客服成为普遍预期之前，企业应主动告知用户正在与机器对话，并谈及公司利润率与 IPO 时机。
> 💡 **深度解读** 一家靠语音以假乱真赚钱的公司主动呼吁「披露机器人身份」，看似矛盾，实则是在监管落地前抢占规则制定权。语音 AI 已经好到无法分辨，行业开始自我设限，说明这条技术路线的能力边界已经越过了社会接受度的临界点。这是 AI 语音真正成熟、并即将迎来强制披露立法的前兆。   
> 📰 [TechCrunch - AI](https://techcrunch.com/2026/09/24/twenty-minutes-with-the-ceo-of-elevenlabs-now-reportedly-valued-at-22-billion/)   

# 📋 详细内容

## 📰 新闻媒体 (16 篇)

**光速创投瞄准2.5亿美元新印度基金，聚焦早期AI投资**
> Lightspeed 计划为其新的印度基金募集 2.5 亿美元，重点投资早期阶段的 AI 项目。该公司首次将印度募资周期与全球基金同步，并转向更短的投资期。
📎 来源：TechCrunch - AI \| 09-25 13:00 · [阅读原文](https://techcrunch.com/2026/09/24/lightspeed-targets-250m-for-new-india-fund-focusing-on-early-stage-ai/)   

**携手联合创始人、合伙人或同事，第二张 TechCrunch Disrupt 2026 门票立享五折优惠**
> TechCrunch Disrupt 2026 推出限时优惠：购买一张门票，即可享受第二张同类型门票半价（5折）。需在活动开始前（10月13日上午8点太平洋时间）完成注册。
📎 来源：TechCrunch - AI \| 09-25 03:15 · [阅读原文](https://techcrunch.com/2026/09/24/bring-your-co-founder-partner-or-colleague-and-get-50-off-a-second-techcrunch-disrupt-2026-pass/)   

**PrismML 将其微型大语言模型引入高通芯片智能眼镜**
> PrismML 将其微型大语言模型引入搭载高通芯片的智能眼镜。该公司的更大目标是开发能在设备端运行的开放权重 AI，从而更好地利用设备现有的计算能力。
📎 来源：TechCrunch - AI \| 09-25 03:00 · [阅读原文](https://techcrunch.com/2026/09/24/prismml-brings-its-tiny-llms-to-qualcomm-powered-smart-glasses/)   

**甲骨文就其新墨西哥州星际之门数据中心发出不可抗力通知**
> 甲骨文对其新墨西哥州的Stargate数据中心发出了不可抗力通知，若该设施未能在2028年如期上线，此举将允许甲骨文推迟付款。
📎 来源：TechCrunch - AI \| 09-25 02:11 · [阅读原文](https://techcrunch.com/2026/09/24/oracle-sends-force-majeure-notice-on-its-new-mexico-stargate-data-center/)   

**Meta 的 Muse Charm 看起来像拓麻歌子，但它瞄准的是一个更新潮的趋势**
> Meta 推出了一款名为 Muse Charm 的 AI 挂饰，外形酷似电子宠物机 Tamagotchi。这款可挂在包上的小配件迎合了 Z 世代将复古科技与时尚配饰相结合的潮流。
📎 来源：TechCrunch - AI \| 09-25 01:39 · [阅读原文](https://techcrunch.com/2026/09/24/metas-muse-charm-looks-like-a-tamagotchi-but-its-tapping-into-a-much-newer-trend/)   

**谷歌相册受《独领风骚》启发的虚拟衣橱现已登陆安卓和iOS**
> Google Photos 推出 AI 驱动的虚拟衣橱功能，可从用户照片中自动构建虚拟穿搭库。该功能于 6 月首先向 Android 用户开放，现已全面登陆 Android 和 iOS 平台。
📎 来源：TechCrunch - AI \| 09-25 01:00 · [阅读原文](https://techcrunch.com/2026/09/24/google-photos-clueless-inspired-virtual-closet-is-now-available-on-android-and-ios/)   

**TechCrunch 2026 创始人峰会：你需要了解的一切**
> TechCrunch 创始人峰会将于11月4日在波士顿举办，为期一天。此次活动汇聚各阶段创业者、顶级风投及资深企业家，帮助创始人获取公司创建与扩展方面的实战见解。
📎 来源：TechCrunch - AI \| 09-25 00:46 · [阅读原文](https://techcrunch.com/2026/09/24/techcrunch-founder-summit-2026-everything-you-need-to-know/)   

**ElevenLabs CEO 谈利润率、IPO 时机，以及告知客户他们正在与机器人对话**
> ElevenLabs为大量客服电话提供AI语音技术，其CEO本周表示，在AI客服成为普遍预期之前，企业应主动告知用户正在与机器对话。
📎 来源：TechCrunch - AI \| 09-25 00:35 · [阅读原文](https://techcrunch.com/2026/09/24/twenty-minutes-with-the-ceo-of-elevenlabs-now-reportedly-valued-at-22-billion/)   

**认识将在 2026 年 TechCrunch Disrupt 上评审创业战场 200 强的新一批风险投资人**
> TechCrunch Disrupt 2026将邀请新一代风险投资人担任Startup Battlefield 200创业大赛评委。观众若在9月25日晚11:59（太平洋时间）前注册，最高可省200美元并获得现场观赛机会。
📎 来源：TechCrunch - AI \| 09-25 00:03 · [阅读原文](https://techcrunch.com/2026/09/24/meet-the-next-wave-of-vcs-judging-startup-battlefield-200-at-techcrunch-disrupt-2026/)   

**谷歌测试让 Gemini 帮你致电商家**
> 谷歌正在测试一项让Gemini替用户拨打商家电话的AI功能。该功能将率先向美国付费订阅Gemini的Pixel 11用户开放。
📎 来源：TechCrunch - AI \| 09-25 00:00 · [阅读原文](https://techcrunch.com/2026/09/24/google-tests-letting-gemini-make-phone-calls-initially-for-us-pixel-owners/)   

**Shield AI、Waabi 与通用汽车：在 TechCrunch Disrupt 2026 探讨如何打造零容错 AI**
> TechCrunch Disrupt 2026大会将设立"Real World AI"专场，邀请Waabi、Shield AI和通用汽车的高管探讨在容错率极低的场景下如何构建AI。9月25日前购票最高可省200美元，第二张票享5折优惠。
📎 来源：TechCrunch - AI \| 09-24 23:00 · [阅读原文](https://techcrunch.com/2026/09/24/shield-ai-waabi-and-general-motors-on-building-ai-when-failure-is-not-an-option-at-techcrunch-disrupt-2026/)   

**Lovable 年化营收突破 6 亿美元，氛围编程加速起飞**
> Lovable 年化收入已突破 6 亿美元，凸显 vibe coding（氛围编程）的快速兴起。联合创始人 Fabian Hedin 表示，该平台上创建的应用每月获得近十亿次访问量。
📎 来源：TechCrunch - AI \| 09-24 22:43 · [阅读原文](https://techcrunch.com/2026/09/24/lovables-annualized-revenue-crosses-600m-as-vibe-coding-takes-off/)   

**安多想用一款人类与智能体协作的团队通讯应用挑战 Slack**
> Ando 推出一款团队消息应用，旨在与 Slack 竞争，让人类与 AI 智能体协同工作。该应用为智能体赋予独立身份和收件箱，使其能像真人一样自然地参与对话。
📎 来源：TechCrunch - AI \| 09-24 22:31 · [阅读原文](https://techcrunch.com/2026/09/24/ando-eyes-slack-as-it-builds-team-messaging-platform-for-humans-and-agents-to-work-together/)   

**TechCrunch Disrupt 2026：Cal AI 的 Zach Yadegari 谈如何打造病毒式增长并从中获利**
> Cal AI 创始人 Zach Yadegari 将亮相 TechCrunch Disrupt 2026 建设者舞台，分享如何实现并利用病毒式增长。9 月 25 日前购票最高可省 200 美元，第二张票享 5 折优惠。
📎 来源：TechCrunch - AI \| 09-24 22:30 · [阅读原文](https://techcrunch.com/2026/09/24/techcrunch-disrupt-2026-cal-ais-zach-yadegari-on-how-to-create-viral-growth-and-capitalize-on-it/)   

**仅剩2天，购买TechCrunch Disrupt 2026门票立省最高200美元——不容错过的5大理由之四**
> TechCrunch Disrupt 2026 门票优惠仅剩两天，最高可省200美元，截止日期为9月25日晚11:59（太平洋时间）。参会理由之一是可获得务实的解决方案，此外还可携带第二位嘉宾享受5折优惠。
📎 来源：TechCrunch - AI \| 09-24 22:00 · [阅读原文](https://techcrunch.com/2026/09/24/2-days-left-to-save-up-to-200-on-techcrunch-disrupt-2026-reason-5-7-to-attend/)   

**澳大利亚将调查OpenAI入侵政府健康网站是否违法**
> 澳大利亚将调查OpenAI入侵政府健康网站的事件是否违法，这是首次已知影响政府机构的相关泄露事件。澳大利亚总理承诺将追究OpenAI的责任。
📎 来源：TechCrunch - AI \| 09-24 20:54 · [阅读原文](https://techcrunch.com/2026/09/24/australia-to-investigate-if-openai-hack-of-government-health-website-broke-the-law/)   

## 💬 社区信号 (20 篇)

**AI 工程从零开始**
> 一个名为 ai-engineering-from-scratch 的 Python 开源项目，主打"学习、构建、分享"的 AI 工程实践理念。该项目在 GitHub 上广受欢迎，已获得约 5.7 万星标和近 1 万次 fork。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/rohitg00/ai-engineering-from-scratch)   

**向量化输入/事后诸葛亮**
> 信息不足，仅提供了项目名称、标题及统计数据（28373星、2819分支），未包含可供概括的实际内容。请补充文章正文或项目描述后再进行总结。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/vectorize-io/hindsight)   

**NVIDIA/模型优化器**
> NVIDIA Model-Optimizer 是一个统一的模型优化库，集成了量化、蒸馏、剪枝、神经架构搜索、推测解码等前沿技术。它可压缩深度学习模型，适配 TensorRT-LLM、TensorRT、vLLM 等部署框架以提升推理速度。该项目基于 Python 开发，目前已获 4206 个星标。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/NVIDIA/Model-Optimizer)   

**anthropics/financial-services**
> Anthropic 推出面向金融服务行业的开源项目，使用 Python 开发。该项目在 GitHub 上获得了 37447 个星标和 5425 个分支。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/anthropics/financial-services)   

**HKUDS/万物皆可命令行**
> CLI-Anything 是一个旨在让所有软件都具备 AI 智能体原生能力的开源项目，配套提供 CLI-Hub 平台。该项目基于 Python 开发，目前已获得约 5 万个 Star 和 4600 多个 Fork。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/HKUDS/CLI-Anything)   

**MVT 项目/MVT**
> MVT（移动验证工具包）是一款用于对移动设备进行取证分析的工具，帮助发现设备可能被入侵的痕迹。该项目使用 Python 开发，已获得约 14779 个星标和 1394 次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/mvt-project/mvt)   

**strands-agents/harness-sdk**
> Strands Agents Harness SDK 是一款开源的 AI 智能体开发工具，支持 Python 和 TypeScript。它能帮助开发者构建生产级 AI 智能体并实现端到端控制，兼容任意模型和云平台。该项目目前已获得 8355 个星标和 1245 个复刻。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/strands-agents/harness-sdk)   

**superdesigndev/treg**
> treg 是一个面向智能体工具的 OpenRouter 平台，用 Python 编写。目前在 GitHub 上获得 3268 星标和 273 次分叉，并设有 Discord 社区供交流。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/superdesigndev/treg)   

**MoneyPrinterTurbo**
> MoneyPrinterTurbo 是一款基于 AI 大模型和自动化工作流的开源工具，只需输入主题或关键词即可一键生成高清短视频。该项目使用 Python 开发，在 GitHub 上已获得超过 12.5 万星标。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/harry0703/MoneyPrinterTurbo)   

**Humanizer-zh（人性化-中文）**
> Humanizer-zh 是 Humanizer 的中文汉化版本，作为 Claude Code Skills 使用，专门用于消除文本中的 AI 生成痕迹。项目采用 Python 开发，目前已获得 18435 星标和 1202 次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/op7418/Humanizer-zh)   

**PanWatch/TNT可能项目**
> 盯盘侠 PanWatch 是一款自托管的 AI 盯盘助手，集成 TradingAgents 多 Agent 投资决策系统，支持 A股、港股、美股的实时监控与持仓管理。它提供智能分析和全渠道消息推送功能，基于 Python 开发。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/TNT-Likely/PanWatch)   

**Z4nzu/hackingtool**
> HackingTool 是一款用 Python 编写的多合一黑客工具集，为黑客提供各类攻击测试功能。该项目在 GitHub 上广受欢迎，已获得约 7.97 万星标和 9039 次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/Z4nzu/hackingtool)   

**claude-code-templates（保持不变，此为项目名称）**
> claude-code-templates 是一个用于配置和监控 Claude Code 的命令行工具。该项目基于 Python 开发，目前已获得 3.1 万多个 Star 和 3600 多个 Fork。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/davila7/claude-code-templates)   

**SimplifyJobs/2027年暑期实习**
> SimplifyJobs 与 Pitt CSC 联合维护的开源项目，汇总2027年暑期软件工程、数据科学、AI、量化、产品管理及硬件等领域的实习岗位信息，每日更新。该项目已获得约4.7万星标。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/SimplifyJobs/Summer2027-Internships)   

**Fosowl/agenticSeek**
> AgenticSeek 是一款完全本地化的自主 AI 智能体，无需 API 或高额月费，仅需电费成本即可运行。它能够自主思考、浏览网页并编写代码。该项目基于 Python 开发，目前已获得 2.7 万余星标。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/Fosowl/agenticSeek)   

**aayushch/laya**
> Laya 是一款开源、本地优先的 AI 通知管理中心，可聚合 Slack、Gmail、GitHub、Jira、Notion 等多个平台的通知。它通过 Ollama 和 LM Studio 使用本地大语言模型处理信息，同时支持自带密钥调用云端模型。该项目基于 Python 开发，目前已获得 293 星标。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/aayushch/laya)   

**alirezarezvani/claude-skills**
> 该项目是一个大型 AI 编程助手资源库，提供 380 多个技能、30 多个智能体、70 多个自定义命令及插件，适用于 Claude Code、Codex、Gemini CLI、Cursor 等十余种编程助手。技能涵盖工程、市场营销、产品、合规、C 级顾问、研究、商业运营、财务及日常生产力等多个领域。该仓库以 Python 编写，已获 2.6 万余星标。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/alirezarezvani/claude-skills)   

**cactus-compute/needle**
> Needle 是一款面向微型设备的自动化基础模型，采用 2-bit 量化，体积仅 8-29 MB。它支持工具调用、结构化数据提取和嵌入功能，可运行于手机、可穿戴设备、智能家居、机器人、汽车及微控制器等设备上。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/cactus-compute/needle)   

**体验实验室/体验**
> Experiential 是一个开源、零加价的模型网关，支持自带密钥（BYOK）、自托管及 1000 多个市场模型。它能通过学习你的使用流量来降低成本、推荐更优模型，并训练一个专属于你的定制模型。项目采用 Python 开发，已获 6832 星标。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/experientiallabs/experiential)   

**anthropics/技能**
> Anthropic 开源了 Agent Skills 公共代码库，主要使用 Python 开发。该项目在 GitHub 上广受欢迎，已获得约 17.8 万星标和 2.1 万次分叉。
📎 来源：GitHub Trending - Python · [阅读原文](https://github.com/anthropics/skills)   

## 📚 论文前沿 (5 篇)

**预测智能体何时应当推理？可靠性路由的行为压力测试**
> 该研究在ForecastBench类二元预测任务上，将检索、推理、参考市场先验或使用历史类比等选择视为可观察的智能体行为，探讨何时应信任每种预测机制。核心发现是机制选择本身对可靠性至关重要，并据此提出了基于行为压力测试的可靠性路由方法。
📎 来源：arXiv - Artificial Intelligence \| 09-25 12:00 · [阅读原文](https://arxiv.org/abs/2609.28475)   

**TW3Cast：基于轻度微调基础模型的冻结路由器，用于 GIFT-Eval 时间序列预测，完全基于训练集选择**
> TW3Cast 是一个时间序列预测系统，在 GIFT-Eval 基准的 130 个条目中按平均 MASE 排名位列第 3，且排在其之上的两个系统均属于依赖智能体或语言模型的类别。该系统不使用任何智能体或语言模型，而是通过在训练集上一次性计算并冻结的选择表来运行。其核心是对轻量微调的基础模型进行冻结路由。
📎 来源：arXiv - Artificial Intelligence \| 09-25 12:00 · [阅读原文](https://arxiv.org/abs/2609.28506)   

**PAWS：策略驱动的智能体世界仿真**
> PAWS 是一个政策驱动的智能体世界模拟数据集，涵盖 36 个经过验证的美国金融与经济政策事件、12,727 条政策关联新闻记录和 65,291 个有据可查的利益相关者行为。该数据集将政策干预过程与时间对齐的历史证据相连接，填补了金融多智能体模拟领域的空白。
📎 来源：arXiv - Artificial Intelligence \| 09-25 12:00 · [阅读原文](https://arxiv.org/abs/2609.28547)   

**皮斯提斯技术报告**
> Pistis 模型家族包含基于 Qwen3.6 和 Qwen3.5 构建的 27B 和 9B 参数多模态大语言模型，采用通用且可扩展的后训练框架开发。该框架先通过大规模多模态监督微调（SFT）奠定基础，再提出交错蒸馏与强化学习（IDRL）这一新颖的后训练方法。
📎 来源：arXiv - Artificial Intelligence \| 09-25 12:00 · [阅读原文](https://arxiv.org/abs/2609.28554)   

**BaseCamp——用于自动化DNA测序数据流程的智能体AI框架**
> BaseCamp 是一个基于智能体的 AI 框架，旨在自动化 DNA 测序数据处理流程中的决策环节。它专注于工作流管理系统之外仍需人工完成的部分，如选择适合样本和平台的质量阈值、判定临界变异位点、诊断异常等。该框架致力于将这些人工决策过程智能化。
📎 来源：arXiv - Artificial Intelligence \| 09-25 12:00 · [阅读原文](https://arxiv.org/abs/2609.28557)   

---
