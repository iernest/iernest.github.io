---
layout:		post
title:      Multimodal End-to-End Sparse Model for Emotion Recognition
subtitle:	
date:       2021-04-10
author:     xuelin
header-img: img/post-web.jpg
catalog:    true
tags:
    - NLP
    - ERC
    - Multimodal
    - NAACL2021
typora-root-url: ..
---

### Multimodal End-to-End Sparse Model for Emotion Recognition

[Paper](https://arxiv.org/abs/2103.09666)

[Code](https://github.com/wenliangdai/Multimodal-End2end-Sparse)

> 现有的多模态情感计算任务，如情感识别，一般采用两阶段流程，首先用手工算法提取单个模态的特征表示，然后利用提取的特征进行端到端的学习。然而，所提取的特征是固定的，不能在不同的目标任务上进一步微调，而手工寻找特征提取算法不能很好地适用于不同的任务，可能导致性能欠佳。在本文中，作者开发了一个完整的端到端模型来连接这两个阶段并共同优化它们。此外，文章重构了当前的数据集，以实现完全的端到端训练。为了减少端到端模型带来的计算开销，作者也引入了一种稀疏的跨模态注意机制来进行特征提取。实验结果表明，文章提出的全端到端模型明显超过了目前基于两阶段管道的最先进模型。此外，通过添加稀疏的跨模态注意，文章提出的模型可以在特征提取部分的一半左右的计算量下保持性能。

- Motivation
  - Extracted features are **fixed** and cannot be further fine-tuned on **different target tasks** in a two-phase pipeline
  - Manually finding feature extraction algorithms does not **generalize** or **scale** well to different tasks
- Model
  - **Fully** end-to-end model
  - **Sparse cross-modal attention** mechanism and **sparse CNN** for the feature extraction

Fully End-to-End Multimodal Modeling

![image-20210410101308172](/modelimg/image-20210410101308172.png)

Multimodal End-to-end Sparse Model

![image-20210410101406171](/modelimg/image-20210410101406171.png)

Result

![image-20210410101449940](/modelimg/image-20210410101449940.png)

### Reference

[面向情感识别的多模态端到端稀疏模型](https://hub.baai.ac.cn/view/7044)
