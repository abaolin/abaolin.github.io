---
title: 华为提出「τ定律」，计划无EUV路线实现等效1.4nm 等 9 条要闻
date: 2026-05-27 09:17:57 +0800
categories: [AI]
tags: [AI, Huawei, 芯片, HBM, AMD, 量子]
---

> 本文由钉钉知识库每日要闻同步生成，共 9 条要闻。

> 26年5月27日18时56分，遍历过去24小时的113篇文章，总结出9个热点话题。由claude-opus提炼，💡部分为模型观点，仅作参考。   

# 📌 今日要闻

**1\. 华为提出「τ定律」，计划无EUV路线实现等效1.4nm**

华为提出「τ定律」（又称「赫定律」）作为摩尔定律替代方案，核心策略是在无法获取EUV光刻设备的条件下，通过时间压缩和多维度工艺优化，计划到2031年实现等效14A（1.4nm）节点的芯片性能。该路线被EE Times等外媒详细报道，被视为中国应对美国芯片制裁的具体技术策略。
> 💡 **深度解读** 这是我看到的第一个被国际半导体媒体认真对待的中国「绕过EUV」路线图。华为不再回避制裁造成的技术断层，而是公开提出替代范式并给出时间表，这本身就是一种产业信心信号。对国内芯片产业链而言，关键问题不是口号是否响亮，而是2031年这个时间窗口内，封装、材料、设计工具等配套环节能否同步跟上。如果τ定律的早期节点能兑现，将实质性改变全球对中国半导体「天花板在哪」的判断。   
> 📰 [EE Times1](https://www.eetimes.com/necessity-is-the-mother-of-invention-huawei-replaces-moores-law-with-hers-law/) · [EE Times2](https://www.eetimes.com/from-shrinking-transistors-to-compressing-time-deciphering-huaweis-%cf%84-law/)   

---

**2\. SK海力士iHBM将冷却层嵌入HBM封装，热阻降30%**

SK海力士发布「iHBM」热封装架构，将冷却元件直接嵌入HBM接口层，热阻降低30%。该技术面向下一代HBM5加速器和高密度AI数据中心，目标是从封装源头解决AI芯片因过热导致的性能降频问题。
> 💡 **深度解读** HBM的散热瓶颈正在成为AI算力扩展的硬约束，iHBM是我看到的第一个在封装层面而非系统层面给出解决方案的量产级技术。这意味着HBM竞争已从单纯的带宽和容量比拼，进入热管理这个新维度。对三星HBM追赶战略而言，这又多了一个需要跨越的工程门槛。对国内存储厂商来说，先进封装的差距可能比制程差距更难弥合。   
> 📰 [Tom's Hardware](https://www.tomshardware.com/tech-industry/semiconductors/sk-hynix-unveils-ihbm-thermal-architecture-that-cools-ai-memory-at-the-source-integrated-cooling-elements-inside-hbm-interface-cut-thermal-resistance-by-30-percent-target-next-gen-hbm5-accelerators-and-dense-ai-data-centers)   

---

**3\. AMD发现FP4训练不稳定根因非随机性不足，实现原生FP4端到端加速9-10%**

AMD研究团队发现FP4精度训练不稳定的根本原因是有限精度导致的梯度表示误差累积，而非此前学界普遍认为的随机舍入缺失。基于这一发现，团队在原生FP4硬件上实现了端到端9-10%的训练加速，同时保持模型精度。
> 💡 **深度解读** 这篇论文的价值不在于加速幅度本身，而在于它纠正了超低精度训练领域一个被广泛接受的错误假设。如果FP4训练路线被打通，意味着下一代GPU/加速器的算力密度可以再翻一倍。AMD在这个方向上抢先发论文，也是在为自家MI系列芯片的FP4支持铺路——这是一个用学术成果绑定硬件路线图的典型动作。   
> 📰 [机器之心](https://mp.weixin.qq.com/s?__biz=MzA3MzI4MjgzMw==&mid=2651035341&idx=2&sn=60922570204a163ed48f2515c8e3ef97)   

---

**4\. IBM拆分量子芯片制造为独立代工厂Anderon，获20亿美元资金**

IBM将量子芯片制造业务拆分为独立公司「Anderon」，总部位于纽约州奥尔巴尼，获得20亿美元联邦及私人资金支持。Anderon运营300mm量子晶圆制造工厂，将向其他竞争性量子硬件厂商开放代工服务，成为美国首家量子芯片代工厂。
> 💡 **深度解读** IBM把量子芯片制造从自用转为开放代工，本质上是承认量子计算的商业化需要更大的产业基座，单一公司无法独撑。20亿美元的联邦资金介入，说明美国政府正在把量子计算视为需要产业政策扶持的战略方向，而非纯市场行为。这个模式如果跑通，量子计算的硬件供给瓶颈会比预期更早松动。   
> 📰 [Tom's Hardware](https://www.tomshardware.com/tech-industry/quantum-computing/ibm-spins-off-americas-first-quantum-chip-foundry-with-2-billion-in-federal-and-private-funding)   

---

**5\. 中国将AI人才出境管控从政府扩展至民营企业**

中国政府已将AI专家出境审批要求从政府机构扩展至民营企业，关键AI人才出国前须事先获得审批。这一政策变化的背景是中美AI竞争加剧。
> 💡 **深度解读** 这条政策的信号强度极高。它意味着北京已将顶尖AI人才明确定义为「战略资源」而非「市场要素」。对国内AI公司而言，这既是人才流失的防火墙，也可能成为国际合作和人才吸引的障碍——顶尖研究者如果预期出境自由受限，加入中国民企的意愿会打折扣。对在华外企和跨国研究合作的影响需要密切跟踪。   
> 📰 [Tom's Hardware](https://www.tomshardware.com/tech-industry/artificial-intelligence/chinese-ai-experts-in-private-firms-now-required-to-secure-approval-before-international-travel-beijing-enforces-policy-to-secure-top-tier-talent-expands-measures-beyond-government)   

---

**6\. OpenRouter估值一年翻倍至13亿美元，多模型并行使用趋势确立**

OpenRouter完成由CapitalG领投的1.13亿美元B轮融资，估值达13亿美元，一年内翻倍。平台过去六个月使用量增长5倍。OpenRouter提供统一API接入多家大模型服务。
> 💡 **深度解读** OpenRouter的增长数据实质性验证了一个判断：企业和开发者不会押注单一模型，而是倾向于多模型并行调用和动态切换。这对任何试图建立模型锁定效应的厂商都是坏消息，对API聚合层和模型路由层则是结构性利好。国内类似的中间层产品（如各类API网关）应该关注这个信号——模型层的商品化速度可能比预期更快。   
> 📰 [TechCrunch - AI](https://techcrunch.com/2026/05/26/openrouter-more-than-doubles-valuation-to-1-3b-in-a-year/)   

---

**7\. Google搜索全面AI化引发用户反弹，DuckDuckGo安装量涨30%**

Google在I/O 2026大会上用AI代理取代传统蓝色链接搜索结果，引发用户强烈反弹。隐私搜索引擎DuckDuckGo应用安装量因此激增30%。
> 💡 **深度解读** Google搜索的激进AI化正在制造一个罕见的用户迁移窗口。30%的安装量增长虽然基数不大，但它证明了一件事：在搜索这个最成熟的互联网产品上，强制改变用户习惯的代价是真实的。这对百度等同样在推进AI搜索改造的公司是直接警示——用户要的是更好的答案，不是被剥夺选择权。   
> 📰 [TechCrunch - AI](https://techcrunch.com/2026/05/26/duckduckgo-installs-are-up-30-as-users-reject-being-force-fed-googles-ai-search/)   

---

**8\. 台积电考虑削减15%员工分红引发罢工讨论**

据报道，台积电在AI热潮推动营收创历史新高的情况下，考虑削减15%的员工分红以资助资本支出。部分员工正考虑罢工和组建工会。台积电回应称预计2026年员工利润分享奖金增速将快于2025年。
> 💡 **深度解读** 台积电的资本支出压力已经大到需要从员工分红中挤出资金，这说明先进制程扩产的资金需求远超利润增长能力。如果罢工或工会化真的发生，将是台积电历史上前所未有的事件，可能影响其产能爬坡节奏。对依赖台积电的全球AI芯片供应链而言，这是一个需要纳入风险评估的新变量。   
> 📰 [Tom's Hardware](https://www.tomshardware.com/tech-industry/tsmc-employees-threaten-samsung-style-strike-over-rumored-15-percent-bonus-cuts-despite-record-profits)   

---

**9\. 小米大模型降价99%，国内模型价格战进入极端阶段**

小米宣布旗下大模型永久降价99%，以极低价格策略正面挑战DeepSeek等竞争对手。这延续了小米在硬件领域的高性价比打法。
> 💡 **深度解读** 99%的降价幅度意味着小米基本放弃了在模型API层面盈利的可能，其真实意图是把大模型能力作为硬件和服务的获客工具。这进一步印证国内大模型API正在快速商品化，独立模型公司如果没有差异化的技术壁垒或场景绑定，纯靠卖Token的商业模式已经不成立。   
> 📰 [钛媒体](https://www.tmtpost.com/8004327.html) · [爱范儿](https://www.ifanr.com/1666975?utm_source=rss&utm_medium=rss&utm_campaign=)
