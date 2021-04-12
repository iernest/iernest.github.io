---
layout:		post
title:      Emotion recognition in conversations in COLING 2020
subtitle:	
date:       2021-04-10
author:     xuelin
header-img: img/post-web.jpg
catalog:    true
tags:
    - NLP
    - ERC
    - Multimodal
typora-root-url: ..
---

### Contextual Augmentation of Pretrained Language Models for Emotion Recognition in Conversations

[Contextual Augmentation of Pretrained Language Models for Emotion Recognition in Conversations](https://www.aclweb.org/anthology/2020.peoples-1.7.pdf)



### Knowledge Aware Emotion Recognition in Textual Conversations via Multi-Task Incremental Transformer

[Knowledge Aware Emotion Recognition in Textual Conversations via Multi-Task Incremental Transformer](https://www.aclweb.org/anthology/2020.coling-main.392.pdf)

- Motivation
  - 语境和常识影响情绪
  - 错误大多来自neutral和non-neutral情绪的混淆
- Model
  - 双层图注意力机制引入外部知识，从而加强语义信息
  - Incremental Transformer建模语境
  - 多任务的方法解决neutral和non-neutral情绪的混淆问题

![image-20210410094417014](/modelimg/image-20210410094417014.png)

- 双层图注意力机制
  - Node-level Attention
  - Relation-level Attention 
  ![image-20210410094813829](/modelimg/image-20210410094813829.png)![image-20210410094833522](/modelimg/image-20210410094833522.png)
- 多任务
  - 任务1：原始任务
  - 任务2：non-neutral vs neutral
  - 任务3：non-neutral情绪分类

Result

![image-20210410095712009](/modelimg/image-20210410095712009.png)

[Summarize before Aggregate: A Global-to-local Heterogeneous Graph Inference Network for Conversational Emotion Recognition](https://www.aclweb.org/anthology/2020.coling-main.367.pdf)

### An Iterative Emotion Interaction Network for Emotion Recognition in Conversations

[An Iterative Emotion Interaction Network for Emotion Recognition in Conversations](https://www.aclweb.org/anthology/2020.coling-main.360.pdf)

- Motivation
  - 对话情绪识别不同于一般的句子级情绪识别，该任务需要考虑对话中话语情绪的相互影响，已有工作通常都建模对话上下文内容，以此来隐式地建模话语的情绪交互，但这种做法常被语言中的复杂表达所干扰，导致情绪交互变得不可靠。
  - 显式建模情绪交互存在一个实际困难，即情绪标签仅能在训练阶段获得，在测试阶段是不可能事先得到并作为输入的，为了解决这个问题，就放宽了对情绪标签完全准确的要求，假设存在部分噪声的情绪标签也可以使情绪识别受益，并且情绪标签精度的不断提升也可以使情绪识别的性能不断增强
- Model
  - 迭代情绪交互模型
  - 使用迭代预测的情绪标签代替真实情绪标签，在迭代过程中不断更正预测并反馈输入，实现逐步增强的显式情绪交互

![640](/modelimg/640.png)

- Utterance Encoder
  - 获取所有话语的向量表示
- Emotion Interaction Based Context Encoder
  - 显式建模话语的情绪交互
  - 三部分：情绪嵌入层、双向门控循环单元和情绪分类器
  - 输入是话语表示序列和上下文情绪概率分布，输出是更新后的上下文情绪概率分布
- Iterative Improvement Mechanism
  - 实现迭代增强的多轮情绪预测
  - 三部分：初始情绪预测、迭代情绪反馈和迭代损失函数



[HiTrans: A Transformer-Based Context- and Speaker-Sensitive Model for Emotion Detection in Conversations](https://www.aclweb.org/anthology/2020.coling-main.370.pdf)



### Reference

[基于迭代情绪交互网络的对话情绪识别](https://mp.weixin.qq.com/s?__biz=MzIxMjAzNDY5Mg%3D%3D&mid=2650800448&idx=1&sn=cced17f8ea6e3567442936a16d2763d2)

