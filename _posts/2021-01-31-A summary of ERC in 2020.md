---
layout:		post
title:      Emotion Recognition in Conversation2020模型总结
subtitle:	
date:       2020-10-16
author:     xuelin
header-img: img/post-web.jpg
catalog:    true
tags:
    - ERC
---

# Emotion Recognition in Conversation2020模型总结

#### 模型概述

|                            Title                             | 模型        | 会议       | 问题                                                 | 模型要点                                                     | 方法                 |
| :----------------------------------------------------------: | ----------- | ---------- | ---------------------------------------------------- | ------------------------------------------------------------ | -------------------- |
| Summarize before Aggregate: A Global-to-local Heterogeneous Graph Inference Network for Conversational Emotion Recognition | SumAggGIN   | COLING2020 | 短语级别的语义单元可以提供话题信息，但是之前没有考虑 | 两阶段图推理网络捕获全局和局部信息；用异构图将短语级别的信息和句子级别的信息融合 | GNN                  |
| Relation-aware Graph Attention Networks with Relational Position Encodings for Emotion Recognition in Conversations | RGAT        | EMNLP2020  | 没有考虑序列信息                                     | 位置编码引入序列信息；关系位置编码同时考虑序列信息和说话人依赖 | GAT                  |
| DialogueGCN: A Graph Convolutional Neural Network for Emotion Recognition in Conversation | DialogueGCN | EMNLP2019  | RNN模型上下文传播效果不好                            | GRU建模序列上下文；GCN建模说话者级别上下文                   | GCN                  |
| Knowledge Aware Emotion Recognition in Textual Conversations via Multi-Task Incremental Transformer | KAITML      | COLING2020 | 中性情绪和非中性情绪的交织                           | 两级图注意力引入知识库；多任务学习解决情绪交织问题           | 图注意力&多任务&常识 |
| Knowledge-Enriched Transformer for Emotion Detection in Textual Conversations | KET         | EMNLP2019  | 人会根据常识判断，但是机器没有                       | 动态图引入外部知识；分层自注意力和交叉注意力建模上下文信息   | 动态图网络&分层&常识 |
| COSMIC: COmmonSense knowledge for eMotion Identification in Conversations | COSMIC      | EMNLP2020  | 情绪转换和相似情绪区分很难                           | 使用常识生成模型引入常识；多种GRU对引入的常识进行建模        | 常识                 |
| HiGRU: Hierarchical Gated Recurrent Units for Utterance-Level Emotion Recognition | HiGRU       | NAACL2019  | 远距离信息难以被捕捉                                 | 两层GRU学习词级别和句子级别信息；Attention和Fusion融合信息   | 分层                 |
| Real-Time Emotion Recognition via Attention Gated Hierarchical Memory Network | AGHMN       | AAAI2020   | 没有考虑序列信息                                     | 两层双向GRU进行特征融合；Attention GRU保留位置信息和顺序信息 | 分层                 |
| DialogXL: All-in-One XLNet for Multi-Party Conversation Emotion Recognition | DialogXL    | AAAI2021   | 之前的层次模型不适合预训练语言模型                   | XLNet在ERC的应用；Memory Bank中由段变为句子；自注意力考虑了说话人之间的关系 | 预训练语言模型       |
| An Iterative Emotion Interaction Network for Emotion Recognition in Conversations | IERC        | COLING2020 | Gold Label可以提高预测效果，但是不能引入             | 迭代的方式变相引入“假”的Gold Label                           | 迭代                 |
| DialogueRNN: An Attentive RNN for Emotion Detection in Conversations | DialogueRNN | AAAI2019   | 没有考虑说话人的差异                                 | 全局GRU建模上下文；Party GRU建模说话人；情绪GRU建模情绪      | RNN                  |

#### 模型要点

|                            Title                             | 模型        | 方法                 | 说话人的差异               | 听众的反应                 | 多方对话                 | 动态上下文              | 情感转换 |
| :----------------------------------------------------------: | ----------- | -------------------- | -------------------------- | -------------------------- | ------------------------ | ----------------------- | -------- |
| Summarize before Aggregate: A Global-to-local Heterogeneous Graph Inference Network for Conversational Emotion Recognition | SumAggGIN   | GNN                  |                            |                            | 支持，没有考虑说话人     | 不支持                  |          |
| Relation-aware Graph Attention Networks with Relational Position Encodings for Emotion Recognition in Conversations | RGAT        | GAT                  | 关系位置编码               | 关系位置编码               | 支持，只考虑的自己和非己 | 不支持                  |          |
| DialogueGCN: A Graph Convolutional Neural Network for Emotion Recognition in Conversation | DialogueGCN | GCN                  | 不同说话者为不同类型的节点 | 不同说话者为不同类型的节点 | 支持，但图复杂度很高     | 不支持                  |          |
| Knowledge Aware Emotion Recognition in Textual Conversations via Multi-Task Incremental Transformer | KAITML      | 图注意力&多任务      |                            |                            | 支持，没有考虑说话人     | Incremental Transformer |          |
| Knowledge-Enriched Transformer for Emotion Detection in Textual Conversations | KET         | 动态图网络&分层&常识 |                            |                            | 支持，没有考虑说话人     | 动态图网络              |          |
| COSMIC: COmmonSense knowledge for eMotion Identification in Conversations | COSMIC      | 常识                 | 单独GRU                    | 单独GRU                    | 支持                     | 多种GRU                 | 引入常识 |
| HiGRU: Hierarchical Gated Recurrent Units for Utterance-Level Emotion Recognition | HiGRU       | 分层                 |                            |                            | 支持，没有考虑说话人     | 不支持                  |          |
| Real-Time Emotion Recognition via Attention Gated Hierarchical Memory Network | AGHMN       | 分层                 |                            |                            | 支持，没有考虑说话人     | Memory Bank             |          |
| DialogXL: All-in-One XLNet for Multi-Party Conversation Emotion Recognition | DialogXL    | 预训练语言模型       | Mask的方式                 | Mask的方式                 | 支持                     | Memory Bank             |          |
| An Iterative Emotion Interaction Network for Emotion Recognition in Conversations | IERC        | 迭代                 |                            |                            | 支持，没有考虑说话人     | 不支持                  |          |
| DialogueRNN: An Attentive RNN for Emotion Detection in Conversations | DialogueRNN | RNN                  | 单独GRU                    |                            | 支持                     | 多种GRU                 |          |



