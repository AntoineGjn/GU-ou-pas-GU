# GU-ou-pas-GU


> It might seems very hard at first to 'train' a network with a dataset so small but in pratice very few people actually train ConvNets from scratch.
Instead, it is common to pretrain a ConvNet on a very large dataset (e.g. ImageNet, which contains 1.2 million images with 1000 categories), and then use the ConvNet either as an initialization or a fixed feature extractor for the task of interest.

## Table of contents
  * [Description](#description)
  * [References](#references)

## Description

I made a ConvNet learn the polytechnique GU using only 50 pictures, most of them from the 14th July parade.

Some of the pictures are provided below as examples :

<p align="center"><img src="/img/arton2270.jpg"/></p>

<p align="center"><img src="/img/defile.jpg"/></p>

What is interesting here is that :

* we are trying to generalize from a very small dataset (~50 training examples)
* these examples often represent the same situation i.e. multiple 'GU' in a military parade

So the issue here is to be able to learn the individual concept of 'GU' without other miscellaneous elements from the situations

We will be using the classic ResNet-18 architecture and do (hopefully intelligently !) some transfert learning on top of it.

<p align="center"><img src="/img/resnet.jpg"/></p>

In order to test if the concept was indeed learned, we will be using a technique introduced by by Matthew Zeiler in [Visualizing and Understanding Convolutional Networks](https://arxiv.org/abs/1311.2901)

To do this, we will be plotting the probability of the class of interest (e.g. GU class) as a function of the position of an occluder object. That is, we iterate over regions of the image, set a patch of the image to be all zero, and look at the probability of the class. We can visualize the probability as a 2-dimensional heat map.

<p align="center"><img src="/img/img_gu.png"/></p>

<p align="center"><img src="/img/gu_detection.png"/></p>

 
The dataset is available here : https://drive.google.com/open?id=1gcrlqG8yRip4qhy92J6p0RwnMn0tJ4BP

## References

* [Standford Course on ConvNets](http://cs231n.github.io/convolutional-networks/) 
* [Visualizing and Understanding Convolutional Networks](https://arxiv.org/abs/1311.2901)
* [Deep Residual Learning for Image Recognition](https://arxiv.org/pdf/1512.03385.pdf)

