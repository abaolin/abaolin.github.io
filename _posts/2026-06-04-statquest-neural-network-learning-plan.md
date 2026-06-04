---
title: 从 StatQuest 开始的神经网络学习计划：一条可执行路线
date: 2026-06-04 16:46:15 +0800
categories: [Tech, Data]
tags: [Tech, AI, Deep Learning, Neural Network, StatQuest, Transformer, LLM, 学习计划]
image:
  path: /assets/img/posts/2026-06-04-statquest-neural-network-learning-plan/cover.png
  alt: 从 StatQuest 开始的神经网络学习计划：一条可执行路线
---

## 核心内容提炼

学习神经网络不应一开始就陷入复杂公式和框架 API，而应先用 StatQuest 这类直观材料建立神经网络的心智模型，再逐步补上数学、反向传播、Transformer、LLM 和工程实践。

学习路线分为四个阶段：先理解神经网络如何从输入到输出，再掌握训练过程和反向传播，然后过渡到词向量、注意力和 Transformer，最后用 Hugging Face、Karpathy、Dive into Deep Learning 等资源把概念落到代码和项目上。目标不是“刷完资料”，而是在每个阶段都形成可验证的输出：笔记、手推、复现代码和小项目。

> 由 claude-opus-4-8 模型总结提炼，观点仅供参考。

## 为什么从 StatQuest 开始

神经网络入门最常见的问题，不是资料太少，而是资料太多。很多路线一上来就给出线性代数、概率论、优化算法、PyTorch 和 Transformer，学习者很容易在第一周就失去主线。

StatQuest 的优势在于把复杂概念拆成可视化、可口语化的解释。它适合用来建立第一层直觉：

- 神经元不是神秘结构，本质是加权求和、加偏置、过激活函数。
- 神经网络不是魔法，而是一层层函数组合。
- 训练不是“让模型变聪明”，而是反复调整参数，让预测误差变小。
- 反向传播不是凭空出现的算法，而是链式法则在多层函数上的系统应用。

用 StatQuest 开局，可以先把“模型到底在干什么”讲清楚，再进入更严肃的数学和代码实现。

## 学习路线总览

建议把这条路线拆成 8 周，每周保持一个明确目标。节奏可以按个人时间压缩或拉长，但不要跳过每个阶段的输出物。

| 阶段 | 时间 | 目标 | 输出物 |
|------|------|------|--------|
| 直觉建立 | 第 1-2 周 | 理解神经网络、损失函数、梯度下降 | 概念笔记 + 手绘流程图 |
| 训练机制 | 第 3-4 周 | 掌握反向传播、过拟合、正则化 | 手推一层网络 + NumPy 实现 |
| 表征学习 | 第 5 周 | 理解词向量、Word2Vec、序列建模 | 词向量笔记 + 小实验 |
| Transformer | 第 6 周 | 理解 Attention、Transformer、GPT | 图解笔记 + 最小实现 |
| 工程实践 | 第 7 周 | 使用 PyTorch / Hugging Face 训练和推理 | 一个可运行 notebook |
| 项目整合 | 第 8 周 | 做一个端到端小项目 | 项目 README + 复盘 |

这条路线的重点是从“看懂”走向“能解释、能复现、能改造”。

## 第 1-2 周：建立神经网络直觉

第一阶段只追求两件事：看懂前向传播，理解为什么要训练。

推荐先看 StatQuest 关于神经网络、梯度下降、损失函数和激活函数的视频。看完后不要急着写 PyTorch，先用纸笔画出最简单的网络：两个输入、一个隐藏层、一个输出。

你需要能解释：

- 输入如何乘以权重并传到下一层
- bias 为什么存在
- ReLU、Sigmoid 这类激活函数解决了什么问题
- loss 如何衡量预测错误
- gradient descent 为什么能让 loss 下降

这一阶段的输出物应该是一份自己的“神经网络一页纸”：用图和文字说明一次预测如何发生。

## 第 3-4 周：理解训练和反向传播

第二阶段进入真正的训练机制。反向传播是很多人卡住的地方，但不要把它想成单独的黑盒算法。它本质上是在问：每个参数对最终误差有多大责任？

建议做三件事：

1. 用一个极小网络手算一次前向传播。
2. 用链式法则手算一次梯度。
3. 用 NumPy 写一个只有一层隐藏层的小网络。

这里不需要追求工业级代码。目标是让你知道框架里的 `loss.backward()` 到底替你做了什么。

这个阶段还要补上几个训练常识：

- 训练集、验证集、测试集的区别
- 过拟合和欠拟合
- 正则化、Dropout、Early Stopping
- 学习率过大或过小会发生什么
- batch size 为什么影响训练稳定性

如果这些概念没有建立，后面看 Transformer 和 LLM 时会只剩 API 调用，缺少判断力。

## 第 5 周：从神经网络过渡到词向量

理解语言模型之前，先理解“词如何变成向量”。推荐阅读 Jay Alammar 的 Word2Vec 图解文章，再结合简单 notebook 观察相似词的向量关系。

这一周要掌握的不是所有 NLP 历史，而是几个关键问题：

- 为什么 one-hot 表示不够用
- embedding 如何让词拥有连续空间中的位置
- Word2Vec 如何通过上下文学习词义
- 向量相似度为什么能表达语义相近

学到这里，神经网络就不只是处理数字表格或图片，而是开始处理语言。

## 第 6 周：进入 Attention 和 Transformer

Transformer 是现代 LLM 的核心结构。建议从 Jay Alammar 的 Illustrated Transformer 开始，再看 Illustrated GPT-2，最后配合 Karpathy 的 Zero to Hero 系列补代码直觉。

这一阶段要抓住三件事：

- **Self-Attention**：每个 token 如何根据上下文重新理解自己。
- **位置编码**：没有循环结构时，模型如何知道词序。
- **堆叠结构**：多层 attention 和 MLP 如何组合成深层模型。

不要一开始就陷入全部矩阵细节。先能讲清楚一句话如何被拆成 token，如何进入 embedding，如何通过 attention 汇聚上下文，再如何预测下一个 token。

## 第 7 周：用工具链把概念落地

当概念打通后，再进入工程工具。推荐顺序是：

1. 用 PyTorch 写一个最小 MLP 或分类模型。
2. 用 Dive into Deep Learning 跑通训练循环。
3. 用 Hugging Face Learn 跑通 tokenizer、model、pipeline。
4. 尝试微调一个小模型或做一个 embedding 检索 demo。

这一周的目标是熟悉真实工作流：数据加载、模型定义、训练、评估、保存、推理。不要只停留在 Colab 运行成功，要能解释每段代码的作用。

## 第 8 周：做一个小项目收束

最后一周需要做项目，不然前面的知识会散掉。项目不必大，但要端到端。

可以选择以下方向：

- 用一个小型文本分类数据集训练分类器。
- 做一个基于 embedding 的相似文本检索 demo。
- 复现一个极简 Transformer block。
- 用 Hugging Face pipeline 做一个可交互的小工具。
- 写一篇学习复盘，解释从神经网络到 Transformer 的主线。

项目的标准不是复杂，而是完整：有 README、有输入输出、有复现实验步骤、有失败记录和改进方向。

## 推荐资源清单

以下资源来自会话中出现的学习材料和同一学习路线的延伸整理。

### 入门直觉

- [StatQuest / Neural Network 系列视频 1](https://www.youtube.com/watch?v=IHZwWFHWa-w)
- [StatQuest / Neural Network 系列视频 2](https://www.youtube.com/watch?v=IN2XmBhILt4)
- [StatQuest / Neural Network 系列视频 3](https://www.youtube.com/watch?v=AsNTP8Kwu80)
- [StatQuest / Neural Network 系列视频 4](https://www.youtube.com/watch?v=CqOfi41LfDw)
- [StatQuest / Neural Network 系列视频 5](https://www.youtube.com/watch?v=KXD7o5IS1C8)

### 系统教材

- [Dive into Deep Learning 中文版](https://zh.d2l.ai/)
- [Dive into Deep Learning 英文版](https://d2l.ai/)

### 图解 NLP 与 Transformer

- [Jay Alammar](https://jalammar.github.io/)
- [The Illustrated Word2Vec](https://jalammar.github.io/illustrated-word2vec/)
- [The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/)
- [The Illustrated GPT-2](https://jalammar.github.io/illustrated-gpt2/)

### 工程实践

- [Hugging Face Learn](https://huggingface.co/learn)
- [Karpathy: Neural Networks Zero to Hero](https://karpathy.ai/zero-to-hero.html)
- [Hands-On Large Language Models](https://www.oreilly.com/library/view/hands-on-large-language/9781098150952/)

## 学习方法建议

这条路线最容易失败的地方，是把“收藏资源”误认为“完成学习”。建议用以下规则控制节奏：

- 每看一个视频，写 5 句话总结，不写就不算学完。
- 每学一个公式，写一个极小数值例子。
- 每跑一个 notebook，改一个参数并记录变化。
- 每周只保留一个主资源，其他资源只用于查漏补缺。
- 每两周做一次复盘，删掉不再需要的资料。

神经网络学习不怕慢，怕的是没有反馈。只要每周都有可见输出，路线就能持续推进。

## 原文链接

- [The StatQuest Illustrated Guide to Neural Networks and AI (PDF)](https://statquest.gumroad.com/l/kihdi)
