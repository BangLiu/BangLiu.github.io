---
layout:     post
title:      Paper reading - A Hierarchical Multi-task Approach for Learning Embeddings from Semantic Tasks
date:       2019-06-27 00:00:00
summary:    Summarize XLNet model and ideas.
categories: jekyll pixyll
---

## 问题

训练层级多任务。

## 关键想法

根据任务关系组合不同的任务，简单任务在下，复杂在上，下层任务对上层进行辅助。这里选择NER，EMD，CR，RE四个任务，分三层。NER-〉EMD-〉CR和RE

## 模型



![model]({{"/images/model.png"|prepend: site.baseurl}}){:height="500px"}

1. 结构

   - Embedding： character emb + Glove + ELMo
   - Encoder: Multi-layer BiLSTM for each task
   - Decoder: CRF for NER and EMD, Scorer for CR and RE

2. 数据

   利用标注好的不同训练数据

3. 训练
   随机选择任务，选择batch

## 技巧

利用BILOU tagging，不是以前的BIO。

## 效果

NER，EMD，RE三个任务达到SOTA

## 评论

1. 建设任务层级有效果
2. 多任务能加速训练
3. 不同层embedding联合能提高效果

## 其他

论文地址: <https://arxiv.org/pdf/1811.06031.pdf>

***

## Problem

Perform multi-tasks in a hierarchical manner.

## Key Ideas

Construct task hierarchy according to their relation. Here choose NER, EMD (Entity Mention Detection), Coreference Resolution and Relation Extraction. NER-〉EMD-〉CR and RE

## Model

1. Structure

   - Embedding： character emb + Glove + ELMo
   - Encoder: Multi-layer BiLSTM for each task
   - Decoder: CRF for NER and EMD, Scorer for CR and RE

2. Data

   Use different existing labeled training data

3. Training

   Randomly select task and data batch.

## Tricks

Use BILOU (Beginning, Inside, Last, Outside, Unit) tagging scheme.

## Performance

Get new SOTA performance for NER, EMD, RE.

## Comments

1. Construct task hierarchichy is useful.
2. Multi-task can accelerate training.
3. Combine different layer's embedding can help.

## Others

Paper link: <https://arxiv.org/pdf/1811.06031.pdf>



