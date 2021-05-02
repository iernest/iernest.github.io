---
layout:		post
title:      Knowledge Aware Emotion Recognition in Textual Conversations via Multi-Task Incremental Transformer
subtitle:	
date:       2021-04-11
author:     xuelin
header-img: img/post-web.jpg
catalog:    true
tags:
    - NLP
    - ERC
    - Multimodal
    - COLING 2020
typora-root-url: ..
---

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



