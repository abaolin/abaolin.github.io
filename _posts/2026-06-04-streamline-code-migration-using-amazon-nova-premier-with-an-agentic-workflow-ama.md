---
title: 用 Amazon Nova Premier 和 Agentic Workflow 加速遗留 C 代码迁移
date: 2026-06-04 09:46:59 +0800
categories: [Tech, DevOps]
tags: [Tech, AWS, Amazon Bedrock, Amazon Nova, Code Migration, Agent, Java, Spring]
image:
  path: /assets/img/posts/2026-06-04-streamline-code-migration-using-amazon-nova-premier-with-an-agentic-workflow-ama/cover.png
  alt: 用 Amazon Nova Premier 和 Agentic Workflow 加速遗留 C 代码迁移
---

## 核心内容提炼

AWS 这篇文章展示了一个面向遗留系统现代化的 Agentic Workflow：使用 Amazon Bedrock Converse API 调用 Amazon Nova Premier，把大型 C 代码库迁移到 Java/Spring 应用。它不是把整份代码一次性丢给模型，而是将迁移拆成代码分析、单文件转换、安全评估、转换验证、迭代修正和最终集成等多个专业 Agent，通过反馈循环逐步提高完整性和质量。

这套方案的价值在于把 AI 代码迁移从“单轮翻译”提升为“工程流程”：LLM 负责重复性转换、模式识别和初步审查，人类工程师负责迁移顺序、复杂业务逻辑确认、测试策略和最终验收。对于有大量 C/C++、COBOL 或其他遗留代码的企业，这种模式比直接生成代码更接近可落地的现代化路径。

> 由 claude-opus-4-8 模型总结提炼，观点仅供参考。

## 遗留代码迁移为什么难

文章从 C 到 Java/Spring 的迁移场景切入。很多企业的核心系统仍运行在老技术栈上，这些系统往往稳定但难以维护，新增功能、接入云服务、做安全治理和招聘维护人员都会越来越困难。

直接使用大模型做代码翻译会遇到几类典型问题：

- **语言范式差异**：C 依赖过程式结构、指针、手动内存管理和错误码；Java/Spring 更强调对象模型、异常、依赖注入和框架约束。
- **架构依赖复杂**：遗留代码之间可能存在大量 include、全局变量、共享结构体和跨模块调用。文章提到有些 TP(Transaction Programs) 会连接多达 12 个其他模块。
- **业务逻辑不能丢**：简单、结构清晰的文件比较容易自动迁移，但超过 700 行、包含复杂业务分支的文件需要人工审核和多轮修正。
- **命名和结构不一致**：老代码里常见不统一的函数名、结构体、错误码和数据库访问模式，迁移时需要建立新的命名和分层规则。
- **集成阶段容易碎裂**：单文件转换看起来正确，不代表多个转换后的 Java 文件能组合成一致的 Spring 应用。
- **质量验证成本高**：迁移后的代码必须在功能等价、安全性、异常处理、数据库访问和日志等方面做系统验证。

因此，AWS 的重点不是证明“模型可以写代码”，而是说明需要把模型嵌入一个可验证、可回滚、可迭代的工程流程里。

## 方案概览

这套方案使用 Amazon Bedrock Converse API 调用 Amazon Nova Premier，并结合 Strands Agents 框架做 Agent 生命周期、会话和上下文管理。整体迁移流程被拆成多个角色清晰的 Agent：

- **Code analysis agent**：分析 C 代码结构、文件依赖、函数调用、共享数据结构和复杂度。
- **Conversion agent**：把单个 C 文件转换为 Java/Spring 代码。
- **Security assessment agent**：对原始 C 代码和迁移后的 Java 代码做安全风险评估。
- **Validation agent**：检查转换是否完整、逻辑是否保留、Spring 实现是否合理。
- **Refine agent**：根据验证和安全反馈修正代码。
- **Integration agent**：把单文件转换结果合并为一致的 Java/Spring 应用结构。

底层实现还包含几个工程化组件：

- **Strands Agents v1.1.0+**：负责 Agent 会话、生命周期和结构化通信。
- **Amazon Bedrock Converse API**：负责模型推理。
- **Amazon Nova Premier**：承担复杂代码分析和转换任务。
- **自定义 BedrockInference 类**：通过 text prefilling 和 response continuation 处理大文件或长输出的 token 限制。
- **asyncio 编排**：支持并发处理和非阻塞 Agent 执行。

## 迁移流程

### 1. 代码分析

第一步不是转换，而是理解代码库。Code analysis agent 会扫描 C 代码目录，识别文件之间的 include、函数调用、共享结构体、全局变量和数据库 I/O 关系。

它还会给文件打复杂度标签：

- Simple：0-300 行
- Medium：300-700 行
- Complex：700 行以上

这个分类很关键。简单文件可以优先自动转换，复杂文件则需要更谨慎的迁移计划、人工检查和多轮验证。

### 2. 文件元数据和迁移顺序

迁移顺序不能随意。对于存在大量依赖关系的 C 系统，通常应从依赖较少的叶子节点开始，再逐步迁移上层模块。

文章中的实现会为每个文件创建 metadata，记录文件类型、复杂度、依赖关系和迁移建议。文件类型包括普通 C 文件、头文件和数据库 I/O(DBIO) 文件。

### 3. 单文件转换

Conversion agent 负责具体代码转换。它会把 C 代码映射到 Java/Spring 结构，例如：

- C 函数转换为 Service 方法
- C struct 转换为 DTO
- 全局变量改为依赖注入或上下文对象
- 错误码改为异常处理
- 日志宏改为 SLF4J
- 数据库调用改为 Mapper 或持久层方法
- 手动内存管理移除，改为 Java 对象和集合

对于超过模型输出限制的文件，系统通过 `stitch_output()` 一类的续写机制拼接长输出，避免大文件迁移被 token 上限截断。

### 4. 安全评估

安全评估是这套流程里很实用的一环。Security assessment agent 同时检查遗留 C 代码和迁移后的 Java 代码，避免把旧风险原样带进新系统，也避免在 Spring 化过程中引入新问题。

它关注的风险包括：

- C 代码中的缓冲区溢出、内存泄漏、整数溢出、格式化字符串问题
- SQL 注入、输入校验不足、硬编码凭据
- Java 代码中的异常信息泄露、反序列化风险、日志敏感数据
- Spring Security 配置缺失或权限边界过宽
- REST 接口暴露过多内部数据

输出不是泛泛而谈，而是按 Critical、High、Medium、Low 分级，并给出修复建议。

### 5. 验证与反馈循环

Validation agent 会对转换结果做完整性检查，包括：

- 原 C 文件中的函数是否都被实现
- 变量和数据结构是否正确映射
- 分支、循环、错误处理路径是否保留
- 指针、字符串、字节处理是否转换合理
- Spring 注解、依赖注入、持久层接口是否符合预期

如果发现缺失或错误，Refine agent 会把验证反馈和安全反馈一起纳入下一轮修正。文章中的流程最多执行 5 轮反馈，也支持在结果已经足够好时提前结束。

这比单次转换更接近真实开发流程：先生成，再 review，再修复，再验证。

### 6. 集成与最终成型

单文件迁移完成后，还需要 Integration agent 处理跨文件集成问题：

- 统一 DTO 字段和方法命名
- 修正 Service 之间的依赖注入
- 组织 package 结构
- 补齐 import 和配置类
- 抽取公共工具逻辑
- 标准化异常处理和日志风格

这一步解决的是“每个文件看起来都对，但系统跑不起来”的问题。对遗留系统迁移来说，集成质量往往比单点转换更决定成败。

## DBIO 到 MyBatis 的专项转换

文章还提到 DBIO C 源码的特殊处理：将 SQL DBIO 代码转换为 MyBatis XML mapper。

这说明迁移不只是语言层面的 C 到 Java，还涉及持久层范式迁移。直接把 SQL 字符串塞进 Java 代码并不是现代化，真正的目标是把数据库访问纳入 Spring 应用的分层结构、Mapper 接口和配置体系中。

## 落地前提

要复现这套方案，需要准备：

- 已开通 Amazon Bedrock，并具备 Amazon Nova Premier 模型访问权限
- AWS CLI、Boto3、Python 3.10+
- Strands Agents
- 一台本地开发环境或 EC2 实例，文章建议至少 t3.medium
- Git 管理的 C 源码目录
- Java 11+、Maven 或 Gradle
- Spring Framework 5.x 或 Spring Boot 2.x+

这些前提说明它更适合作为企业内部迁移流水线或 PoC，而不是一次性脚本。

## 工程启示

这篇文章最值得借鉴的点不是某个 prompt 模板，而是流程设计：

- **迁移前先分析依赖**：没有 dependency map，AI 转换会缺少全局视角。
- **按复杂度分层处理**：简单文件自动化，复杂文件保留人工审查。
- **安全和功能验证要内置**：不要等到迁移后才做安全扫描和测试。
- **Agent 应该有明确职责**：分析、转换、验证、修正和集成分开，输出更容易审计。
- **把 token 限制当工程问题处理**：长文件和长输出需要续写、拼接和状态管理。
- **人仍然在关键路径上**：迁移顺序、业务等价性、测试覆盖和最终上线决策不能完全交给模型。

如果团队正在评估 AI 辅助遗留系统现代化，这套架构可以作为参考模板：先围绕一个小型模块建立分析、转换、验证、修正的闭环，再逐步扩展到更大的代码库。

## 原文链接

- [Streamline code migration using Amazon Nova Premier with an agentic workflow](https://aws.amazon.com/cn/blogs/machine-learning/streamline-code-migration-using-amazon-nova-premier-with-an-agentic-workflow/?utm_source=chatgpt.com)
