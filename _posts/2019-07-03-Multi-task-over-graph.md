---
layout:     post
title:      Paper Reading - Multi-task Learning over Graph Structures
date:       2019-07-03 00:00:00
summary:    It learn complete graph or star graph relatedness over different tasks.
categories: paper reading
---

## Problem

How to learn complex relationships between different tasks.

## Key Ideas

![Multi-Task Graph Structures]({{"/images/2019-07-03-task-graphs.png"|prepend: site.baseurl}}){:width="400px"}

1. Instead of use flat structure or pre-defined hierarchical structure, learn a complete graph or star graph between tasks. It is weighted directed graph.
2. Tasks are nodes in a task graph. Interactions between words are modeled by LSTM, and interactions between tasks are modeled by GCN.
3. Relationship between tasks depend on the specific sample and context, not static scores.
4. In Star-graph, utilize gating mechanism to aggregate different information from different tasks. Use an extra LSTM as virtual node to aggregate all task information.

## Model

![Multi-Task over Graph]({{"/images/2019-07-03-multi-task-learning-over-graph.png"|prepend: site.baseurl}}){:width="600px"}

1. For complete-graph, learn weights from other tasks to target task. The weights are depending on the current inputs. The weights are used to get an aggregated vector from other tasks. It will be used in the updating of target task's LSTM.

2. For star-graph, use an extra LSTM as virtual node. It acts like a mailbox. Different tasks share the same LSTM and input their specific input. Therefore, it produces different outputs for each task. The weights are learned in a similar way. Star-graph has smaller calculation complexity.

3. Training

   Jointly train multi-tasks with weighted loss function.

## Performance

The joint model shows significant benefits over single models.

## Comments

1. Whether it is too complicated to learn different weights for each different input?
2. Can we just learn a relationship matrix between different tasks?
3. The gating mechanism in Star-Graph is reasonable.

## Reference

Paper link: <https://arxiv.org/pdf/1811.10211.pdf>

## Related Reading

<https://ieeexplore.ieee.org/document/8658407>



