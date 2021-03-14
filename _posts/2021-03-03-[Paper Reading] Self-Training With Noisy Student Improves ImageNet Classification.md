---
title: '[Paper Reading] Self-Training With Noisy Student Improves ImageNet Classification'
date: 2021-03-03
permalink: /posts/2021/03/[Paper Reading] Self-Training With Noisy Student Improves ImageNet Classification/
tags:
  - cool posts
---

> Xie et al. Self-training with Noisy Student improves ImageNet classification. CVPR 2020

============
## Problem Definition
Use as little annotated data as possible to learn to distinguish images.
1. A helpful scheme for using as little annotated data as possible to learn to distinguish images should have properties as following:
	+ It requires a small corpus of labeled images to work well.
	+ It needs to have similar or better performance than a model trained with a large amount of annotated data.
	+ Robustness. 
2. Goal
	+ The authors limit themselves from making use of unlabeled images available in much larger quantities to improve the accuracy and robustness of SOTA models.
3. Problem formulation
	+ To minimize the average cross-entropy when labeled and unlabeled datasets are concatenated.


## Contribution and Discussion

**Contribution:**
1. Noisy Student boosts robustness in computer vision models.
2. The experiments showed that Noisy student significantly improves performances on ImageNet-A, C and P.

**Limitation:**
1. Computing Resources: The Largest model, EfficientNet-L2, needs to be trained for 3.5 days on a Cloud TPU v3 Pod, which has 2048 cores. Many people won't be able to replicate and tweak it for further experimentation.

## Method

### Classic Self-training
1. train a teacher model on labeled images
2. use the teacher to generate pseudo labels on unlabeled images
3. train a student model on the combination of labeled images and pseudo labeled images.
We iterate this algorithm a few times by treating the student as a teacher to relabel the unlabeled data and training a new student.

### Proposed algorithm
The method is similar to classical self-training with some minor differences.

![image.png](https://i.loli.net/2021/03/03/Jo4zgGEflRyIX7p.png)

The main difference is the addition of noise to the student using RandAugment data augmentation, dropout and stochastic depth.

Different kind of noise has a different kind of effects. For example, when augmentation is used, the model is forced to learn to categorize a normal and the corresponding augmented image in the same category. Similarly, when dropout is used, a model acts as an ensemble of models. Hence a student with noise is a more powerful model 
