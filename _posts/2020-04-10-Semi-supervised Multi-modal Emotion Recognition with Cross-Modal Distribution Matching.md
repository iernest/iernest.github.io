---
layout:		post
title:      Semi-supervised Multi-modal Emotion Recognition with Cross-Modal Distribution Matching
subtitle:	
date:       2021-04-10
author:     xuelin
header-img: img/post-web.jpg
catalog:    true
tags:
    - NLP
    - ERC
    - Multimodal
    - ACM MM 2020
typora-root-url: ..
---

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
