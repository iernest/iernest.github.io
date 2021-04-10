---
layout:		post
title:      Emotion recognition in conversations in ACM MM 2020
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

[Modeling both Intra- and Inter-modal Influence for Real-Time Emotion Detection in Conversations](https://dl.acm.org/doi/pdf/10.1145/3394171.3413949?casa_token=CgDjp2hokAEAAAAA:W-GCXBkMztp74bOyjSDQQM0dmeNOU-XKhN336SmJBT_rbhX0PAv5JGSVq_0yD8LU3DNb7uyqPoQk)

- Motivation

  - 单模态信息量不够
  - 信息流单方向对信息使用不充分

  

  ![image-20210410095428895](/modelimg/image-20210410095428895.png)

- Model

  - 多模态
  - 信息双向传播

  ![image-20210410095516187](/modelimg/image-20210410095516187.png)

### Semi-supervised Multi-modal Emotion Recognition with Cross-Modal Distribution Matching

[Semi-supervised Multi-modal Emotion Recognition with Cross-Modal Distribution Matching](https://dl.acm.org/doi/10.1145/3394171.3413579)

- Motivation
  - High manual annotation **cost** and inevitable label **ambiguity**
  - Weakness of existing approaches includes such as **training instability(**data augmentation and semi-supervised learning through generative adversarial network) or **marginal improvement**(transfer learning)
- Model
  - Assume that different modalities are expected to express **similar emotion information** at the coarse-grained level
  - **Deep Auto-encoder (DAE)** structure to extract utterance-level representation
  - **Maximum Mean Discrepancy**(MMD) to restrict their distribution difference

Multi-modal Network Architecture

![image-20210410100414178](/modelimg/image-20210410100414178.png)



DAE for Representation Learning![image-20210410100459901](/modelimg/image-20210410100459901.png)



![image-20210410100447505](/modelimg/image-20210410100447505.png)

Loss Function Design

![image-20210410100608178](/modelimg/image-20210410100608178.png)

![image-20210410100730787](/modelimg/image-20210410100730787.png)