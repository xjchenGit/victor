---
title: '[Paper Reading] A survey on Image Data Augmentation for Deep Learning'
date: 2021-03-03
permalink: /posts/2021/03/[Paper Reading] A survey on Image Data Augmentation for Deep Learning/
tags:
  - cool posts
---
>Shorten, C., Khoshgoftaar, T.M. A survey on Image Data Augmentation for Deep Learning. J Big Data 2019
============
## Problem Definition

Data Augmentation approaches overfitting from the root of the problem, the training dataset. This is done under the assumption that more information can be extracted from the original dataset through augmentations

1. How data augmentation properties as following:
	+ Produce enough data
	+ class balance
	
2. Goal
	+ Try to investigate existing data augmentation solutions to solve the problem of overfitting of deep learning models due to limited data.

3. Problem formulation
	+ The image recognition software must overcome issues of viewpoint, lighting, occlusion, background, scale, and more. The task of Data Augmentation is to bake these translational invariances into the dataset such that the resulting models will perform well despite these challenges



## Contribution and Discussion

### Contribution

1. Many of these techniques and concepts can be expanded to other data domains, although this survey focuses on applications for image data.
2. Many augmentations have been proposed which can generally be classified as either a data warping or over-sampling technique.

### Limitation

1. Data Augmentation cannot overcome all biases present in a small dataset. (e.g., in a dog breed classification task, if there are only bulldogs and no instances of golden retrievers, no augmentation method discussed, from SamplePairing to AutoAugment to GANs, will create a golden retriever. However, several forms of biases such as lighting, occlusion, scale, background, and many more are preventable or at least dramatically lessened with Data Augmentation.)

### Future work

1. The layered architecture of deep neural networks presents many opportunities for Data Augmentation. Most of the augmentations surveyed operate the input layer. However, some are derived from the hidden layer representations, and one method **DisturbLabel** is even manifested in the output layer.
2. The space of intermediate representations and the label space are under-explored areas of Data Augmentation with interesting results.

## Method
![image.png](https://i.loli.net/2021/03/03/ehAn3Nr9jvg4sXi.png)

Data Augmentation has three major types: basic image manipulations, deep learning approaches, and meta-learning.

**Basic image Manipulation**
The earliest demonstrations showing the effectiveness of Data Augmentations come from transformations such as horizontal flipping, color space augmentations, and random cropping.

**Deep Learning approaches**
Adversarial Training, neural style transfer, GAN Data Augmentation

**Meta-Learning**
Neural Augmentation, AutoAugment, Smart Augmentation
