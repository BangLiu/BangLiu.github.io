---
layout:     post
title:      Curriculum Learning 
date:       2019-07-04 12:00:00
summary:    Summarize a few works for curriculum learning.
categories: survey
---

## Introduction

Curriculum learning accelerates the convergence of a model, and helps to find a better local minimum for non-convex problems. Here we summarize a few works.

---

## Curriculum Learning

### Problem

Introduce curriculum learning. Formalize such training strategy, perform experiments on some problems, and propose potential explanations for why curriculum learning has both an effect on the speed of convergence of the training process to a minimum and, in the case of non-convex criteria, on the quality of the local minima obtained.

### Key Ideas

1. Order training examples by difficulty: first easy examples, then introducing more difficult examples, and finally the full training dataset.
2. A curriculum can be seen as a sequence of training criteria. Each criterion in the sequence is associated with a different set of weights on the training examples, or more generally, on a reweighting of the training distribution.
3. In a curriculum, the entropy of training distribution at different steps increases, and the weight of training sample increases. 
4. We need a method to estimate the difficulty of examples for different tasks.
5. Faster training is maybe because the learner wastes less time with noisy or harder to predict examples when it is not ready to incorporate them.
6. Better local minimum is because a curriculum can be seen as a particular continuation method: first optimize a smoothed objective and gradually consider less smoothing, with the intuition that a smooth version of the problem reveals the global picture.

### Comments

How to order the training examples; how to change the data distribution in different training steps. These are important for curriculum learning.

We can manually set above criterias, or we can learn by RL.

---

## References

Curriculum Learning:<https://ronan.collobert.com/pub/matos/2009_curriculum_icml.pdf>


