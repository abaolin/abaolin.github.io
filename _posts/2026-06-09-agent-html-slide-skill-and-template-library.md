---
title: 从 Frontend Slides 到 Editable：Agent 如何制作可交付、可编辑的网页 PPT
date: 2026-06-09 16:33:08 +0800
categories: [Tech, Frontend]
tags: [Tech, Frontend, HTML, Presentation, AI Agents, Claude Code, Design System, Workflow, Editable]
---

## 核心内容提炼

`frontend-slides`、`beautiful-html-templates` 与 `frontend-slides-editable` 共同展示了一套面向编码 Agent 的网页 PPT 生产体系：先用 skill 固化需求发现、风格预览、PPT/PDF 转换和单 HTML 交付流程，再用模板库提供 34 套可复用视觉系统，最后通过 editable 分支加入浏览器内编辑运行时，让生成结果不只是“能展示”，还能继续拖拽、缩放、改文字、重排页面、保存并导出干净 HTML。

> 由 GPT-5 Codex 模型总结提炼，观点仅供参考。

## 为什么网页 PPT 需要一套 Agent 生产体系

用大模型直接生成一份 HTML 幻灯片并不难，难的是稳定地产出“像作品而不是草稿”的演示文稿。普通提示词往往会遇到几个问题：

- 视觉风格依赖用户描述，用户很难准确说清自己想要的审美。
- 每次从零写 CSS，容易生成重复、普通、同质化的页面。
- 演示文稿有固定比例、切页、键盘控制、导出、适配等工程细节，不只是几页静态 HTML。
- 如果输入是 PowerPoint 或 PDF，还需要提取文字、图片、页面结构，再重新编排。
- 很多演示文稿生成后不会立刻定稿，仍需要客户、团队或作者在浏览器里继续改。

这三个项目分别解决其中不同层次的问题：`frontend-slides` 负责把“做 PPT”变成可执行的 Agent workflow；`beautiful-html-templates` 负责提供高辨识度模板资产；`frontend-slides-editable` 负责把生成物从只读展示推进到可继续编辑的交付件。

## Frontend Slides 的产品化设计

`frontend-slides` 是基础层。它将自己定义为一个用于创建 HTML presentations 的 coding-agent skill，可以从零制作演示文稿，也可以转换 PowerPoint 文件。它的核心特点可以概括为五点：

1. **单文件交付**：生成带内联 CSS/JS 的 HTML，不依赖 npm、构建工具或前端框架。这降低了长期维护成本，也方便用户直接打开、分享和修改。
2. **视觉风格发现**：不是让用户用抽象词描述审美，而是先生成 3 个视觉预览，让用户从实际画面中选择方向。
3. **PPT 转换能力**：可以从现有 `.pptx` 中提取文本、图片和备注，再转换为网页幻灯片。
4. **反模板化审美**：通过预置风格和 bold template pack，避免大模型常见的泛化视觉套路。
5. **生产级细节**：要求固定 16:9、可访问、代码有注释，并提供部署到 Vercel 和导出 PDF 的脚本。

这套设计本质上把 Agent 的职责拆成了两层：一层是内容与结构生成，另一层是视觉系统选择与落地。只让模型“写漂亮一点”是不可靠的，而让模型在明确的候选风格和工程约束内生成，结果会稳定得多。

## beautiful-html-templates 的角色

`beautiful-html-templates` 是素材层。它是一套可复用 HTML slide templates 模板库，目标是让任何 coding agent 都能根据用户 brief 选择合适模板，并自动生成漂亮的 deck。

它不是单个主题，而是一个模板系统集合。README 中列出了 34 套模板，每套模板都通过封面、中段、后段三张示例图展示视觉系统在不同版式下的表现。模板风格覆盖很广，例如：

- `Soft Editorial`：偏编辑感、纸张质感和柔和配色。
- `Neo-Grid Bold`：新粗野主义网格、强对比、单一高亮色。
- `Creative Mode`：多色块、强标题、适合创意表达。
- `Signal`：深色画布、克制金色强调，适合机构化表达。
- `Retro Windows`：Windows 95 风格，适合复古技术叙事。

这个模板库的关键不是“多”，而是它把审美资产结构化了：每个模板都有目录、HTML、元数据以及相关资产，Agent 可以读取索引、匹配需求、克隆模板、替换内容，而不是每次重新发明一套视觉语言。

## Frontend Slides Editable 补上“生成后编辑”

`frontend-slides-editable` 是交互层。它是 `frontend-slides` 的可编辑分支，保留父 skill 的风格探索、视口规则、PPT/PDF 转换能力，并加入完整的浏览器内编辑运行时。

这一步解决的是演示文稿最真实的使用场景：第一版生成后，往往还要继续改。它内置的编辑能力包括：

- 在幻灯片上拖拽对象、缩放文本框和媒体框。
- 支持 `Ctrl+点击` 多选、撤销、重做、对象删除。
- 通过 Pages 侧栏重排或删除页面。
- 在编辑模式中添加文本、图片、视频对象。
- 图片可选择本地文件，也可通过剪贴板粘贴，并以 data URL 方式保持单文件自包含。
- 富文本工具栏支持粗体、斜体、字体、字号和自定义像素字号。
- `Ctrl+S` 将完整 deck 结构保存到 `localStorage`。
- 导出时剥离临时编辑状态、上传控件和文件输入，得到干净的独立 HTML。

它还明确区分 `frontend-slides` 与 `frontend-slides-editable` 的适用边界：前者更轻、更适合接近定稿的只读交付；后者更重，但适合评审后仍会继续改布局、内容和媒体的场景。

## 三者如何协同

这三个项目可以理解为一条从“生成”到“可编辑交付”的流水线：

- `frontend-slides` 定义 Agent 怎样发现需求、选择风格、生成 HTML、转换 PPT、部署和导出。
- `beautiful-html-templates` 提供可选择、可移植、可审美复用的模板系统。
- `frontend-slides-editable` 在最终 deck 中注入编辑运行时，让用户可以在浏览器里继续改。

在 `frontend-slides` 中，风格发现阶段会混合三类候选：

1. 一个来自安全预设的基础风格。
2. 至少一个来自 `beautiful-html-templates` 的 bold template。
3. 一个 wildcard 方向，可能是另一个 bold template，也可能是 Agent 自生成的定制风格。

这种组合很实用。安全预设保证默认结果不崩，bold template 提供强审美上限，wildcard 给特殊需求留出空间。用户不用读完整模板库，只需要看三个预览并选择，这正是面向非设计用户的合理交互。

而在 editable 分支中，模板移植进一步变成“双构建层”：19 套 legacy preset 用于 runtime smoke 和风格预览；34 套 ported preset 从 `beautiful-html-templates` 的真实上游模板移植，保留原始 CSS、字体、slide classes、装饰语言，再统一注入编辑运行时和 locked slot adapter。

## 渐进式加载：为 Agent 设计上下文预算

这套体系里最值得借鉴的工程思想，是“progressive disclosure”。也就是不要让 Agent 一开始读完所有素材，而是按阶段加载必要信息：

- 初始阶段读取 `SKILL.md`，理解完整工作流。
- 风格选择阶段读取 `STYLE_PRESETS.md` 和模板索引。
- 只对入围模板读取小型 `preview.md`。
- 用户选定某个 bold template 后，再读取该模板完整的 `design.md`。
- 最终生成阶段才使用固定舞台 CSS、HTML 结构、动画模式和脚本。

这解决了 Agent 应用里一个常见问题：资料越多不一定越好。把所有模板、规则、示例一次性塞进上下文，会增加噪声，也会浪费 token。用索引先筛选，用预览再确认，最后只展开一个模板，才是适合 Agent 的资料组织方式。

在 `frontend-slides-editable` 中，这个策略继续延伸：`SKILL.md` 承载工作流，`editor-runtime.md` 描述运行时 DOM 契约，`examples/editable-deck-reference.html` 作为唯一参考实现，验证脚本和截图脚本则用于维护 preset 与 runtime 的稳定性。

## 可编辑运行时的关键设计：slot 与 object 分层

`frontend-slides-editable` 最关键的设计，是把“模板原生内容”和“用户新增对象”分开。

真实模板里的标题、正文、指标、图片等内容，通过 `data-edit-slot` 在原位编辑。这样可以保留模板原始布局、网格、纹理、轴线、装饰图形和视觉节奏，不会因为可编辑而把设计骨架拖散。

用户通过 Add element 新增的内容，则进入 `.slide-edit-layer`，成为带 `data-slide-object` 和 `data-oid` 的可拖拽对象。它们可以移动、缩放、删除、多选，也可以进入撤销栈。

这个分层很重要。很多“可编辑模板”会把所有元素都变成自由拖拽对象，结果是第一轮编辑后版式就失控。editable 分支默认使用 slot 模式，把设计系统锁住，只开放该开放的内容；当用户确实需要自由移动原生内容时，再通过 Unlock layout 把当前页可编辑槽位复制成可拖拽对象。

## 单 HTML 文件的技术取舍

三个项目都坚持零依赖、单 HTML 文件交付。这是一个偏保守但非常实用的技术取舍。

它牺牲了一部分现代前端工程的模块化体验，但换来了几个直接收益：

- 用户不需要安装依赖。
- 文件可以长期打开，不受框架版本影响。
- 分享、归档、邮件传递都更简单。
- Agent 生成、检查和修改的边界更清晰。
- 可编辑分支也能把图片、视频和 deck 状态收敛到自包含文件与本地存储里。

对于演示文稿这种“交付物重于持续开发”的场景，单文件往往比复杂工程更合适。真正需要模块化的部分，不在最终产物里，而在 skill 的支持文件、模板库和脚本中。

## 从 PPT/PDF 转网页：不只是格式转换

PPT 或 PDF 转 HTML 的难点不只是解析文件。更重要的是如何在保留原始内容的同时，重新组织为适合网页展示和后续编辑的版式。

`frontend-slides` 的流程里，Agent 会先提取原始文本、图片和备注，给用户确认，再进入风格选择，最后生成带原始资产的新 HTML deck。`frontend-slides-editable` 则进一步支持将 `.pptx` 或 `.pdf` 抽成相同形态的中间 JSON 和 `assets/`，再生成可编辑网页幻灯片。

这避免了“机器直接转码”常见的问题：内容是全的，但视觉和叙事都很生硬。它把 PPT/PDF 转换看作一次再设计，而不是一次文件格式迁移。尤其是 PDF，editable 分支也明确强调这是“抽取后重设计”，不是像素级还原。

## 验证脚本让 Skill 更像工程项目

`frontend-slides-editable` 的 README 还透露出一个值得注意的方向：Agent skill 不只是文档和模板，也需要验证脚本维护质量。

它包含多类脚本，例如：

- 构建 legacy preset 和 template port deck。
- 用无头 Chrome 截取预览图。
- 静态验证 editable runtime 的 DOM 契约。
- 用负向 fixture 确认 validator 能抓到坏例子。
- 抽样验证 Pages、保存、导出和移动端横向溢出。

这说明一套可复用 skill 如果要长期演进，不能只依赖人工观察生成结果。它需要把“能编辑”“能保存”“能导出”“移动端不溢出”“模板移植没有破坏契约”这些要求变成自动化检查。

## 对 Agent Skill 设计的启发

这三个项目给 Agent 工具设计提供了几个可复用经验：

1. **把自由生成变成分阶段决策**：需求、预览、选择、生成、验证、分享，每一步都有清晰边界。
2. **把审美变成可比较对象**：用户不需要说懂设计术语，只需要在预览中做选择。
3. **把模板库做成 Agent 可读结构**：索引、预览、完整设计文件分层组织，便于模型按需读取。
4. **区分只读交付与可编辑交付**：接近定稿时选轻量只读，仍需协作改稿时选 editable。
5. **用 slot/object 分层保护设计系统**：允许用户编辑内容，但不轻易破坏模板骨架。
6. **把最终交付保持简单**：复杂度留在工具链中，用户拿到的是能直接使用的 HTML。
7. **把默认路径和高级路径分开**：安全预设兜底，bold template 提升上限，自定义 wildcard 处理特殊场景。
8. **把质量要求变成验证脚本**：尤其是涉及运行时、保存、导出和视口适配时，skill 需要像软件项目一样测试。

## 总结

`frontend-slides`、`beautiful-html-templates` 和 `frontend-slides-editable` 展示了一种更成熟的 Agent 应用形态：不是让模型凭空“生成一个网页 PPT”，而是给它一套工作流、一组可选择的视觉系统、一个渐进式加载机制、一个可编辑运行时，以及清晰的交付边界。

这类设计的核心价值，是把不稳定的生成能力放进稳定的产品流程里。Agent 仍然负责理解需求和生成内容，但关键审美资产、工程约束、编辑运行时和验证路径都被结构化了。对于任何想把 AI 编码助手变成可复用生产工具的人来说，这比单次提示词更值得参考。

## 原文链接

- [Frontend Slides README](https://github.com/zarazhangrui/frontend-slides/blob/main/README.md)
- [beautiful-html-templates README](https://github.com/zarazhangrui/beautiful-html-templates/blob/main/README.md)
- [Frontend Slides Editable README](https://github.com/archlizheng/frontend-slides-editable/blob/main/README.md)
