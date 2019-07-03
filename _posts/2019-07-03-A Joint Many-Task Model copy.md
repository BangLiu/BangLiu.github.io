---
layout:     post
title:      Paper reading - A Joint Many-Task Model, Growing a Neural Network for Multiple NLP Tasks
date:       2019-07-03 00:00:00
summary:    It trains a 5 layers BiLSTM for 5 tasks, frow low-level to high-level.
categories: paper reading
---

## Problem

Perform multi-tasks in a hierarchical manner. Train a multi-layer model for multitasks. Different layers handle different tasks, from morphology, syntax to semantics.

## Key Ideas

1. Different layers handle different tasks.
2. Low-level layer handle easy task, high-level layer handle difficult task.
3. Tasks are stacked: POS - CHUNK - DEP - Relatedness - Entailment.
4. Train tasks sequentially, from easy to hard; add regularization term to prevent significant catastrophic forgetting.

## Model

![Joint Many-Task Model]({{"/images/2019-07-03-Joint-model.png"|prepend: site.baseurl}}){:width="350px"}

1. Structure

   - Each task utilizes one layer BiLSTM
   - n + 1 layer dependends on n-th layer output.

2. Data

   Use different existing labeled training data

3. Training

   Train tasks in sequence: POS, CHUNK, DEP, Relatedness, Entailment (from low-level to high level). Add successive regularization: make the previous layer output not change too much after training current layer.

## Performance

1. Joint model performs better than single task models.
2. Joint performance are comparable with existing single models.
3. Sequential training is better than shuffle.
4. Regularization is useful for tasks with small amount of data.

## Comments

1. Multi-task, task hierarchy are useful.
2. Train from bottom to top.
3. We can learn task dependency structure.
4. We can utilize better techniques for catastrophic forgetting. Besides, maybe sampling to improve tasks with limited data can help.

## Reference

Paper link: <https://aclweb.org/anthology/D17-1206>



