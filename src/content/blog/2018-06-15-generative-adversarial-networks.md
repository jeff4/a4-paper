---
author: Jeff Hwang
pubDatetime: 2018-06-15T06:43:00Z
title: Generative Adversarial Networks
postSlug: 2018-06-15-generative-adversarial-network
featured: false
draft: false
tags:
  - tech
  - research
  - ai
  - generative
ogImage: ""
description:
  Intro to GANs and why this architecture has been so interesting.
---

I've been reading about [Generative Adversarial Networks](https://en.wikipedia.org/wiki/Generative_adversarial_network) (GANs) which were first introduced in this [2014 paper](https://arxiv.org/abs/1406.2661) by Ian Goodfellow et al. At the time, deep neural nets had already shown impressive advances in object identification, visual discrimination, NLP, and other tasks–especially in the context of supervised learning. However, GANs addressed a distinct shortcoming in neural networks–they were less capable of *generating*believable images (or other types of media such as audio).

Building on previous work in [game theory](https://en.wikipedia.org/wiki/Minimax), [restricted Boltzmann machines](https://en.wikipedia.org/wiki/Restricted_Boltzmann_machine) (RBM's), [deep belief networks](https://en.wikipedia.org/wiki/Deep_belief_network) (DBN's), and [deep Boltzmann machines](https://en.wikipedia.org/wiki/Boltzmann_machine#Deep_Boltzmann_machine) (DBM's), Goodfellow and his coauthors proposed using pairing two neural networks to make each other better at their respective tasks. One network was called G, the generator, while the second network was called D, the discriminator. In addition there was a library L of real images that were similar to the types of images created by G. The job of D was to tell if an image was drawn from G or L. Since both G and D are [multilayer perceptrons](https://en.wikipedia.org/wiki/Multilayer_perceptron), they can jointly be trained using the [backpropagation](https://en.wikipedia.org/wiki/Backpropagation), [stochastic gradient descent](https://en.wikipedia.org/wiki/Stochastic_gradient_descent), and [dropout](http://jmlr.org/papers/volume15/srivastava14a/srivastava14a.pdf) algorithms.

The initial 2014 paper showed promising results and has generated a wave of papers since then. I've found this [three](https://www.kdnuggets.com/2017/11/overview-gans-generative-adversarial-networks-part1.html)-[part](https://www.kdnuggets.com/2017/11/generative-adversarial-networks-part2.html) [series](https://www.kdnuggets.com/2017/11/infogan-generative-adversarial-networks-part3.html) on GANs by Zak Jost to be a helpful introduction to post-2014 developments. GANs have proven so popular that there are now hundreds of related GANs tracked at places like [GANzoo](https://github.com/hindupuravinash/the-gan-zoo).

There are several more GAN papers on my reading list. First, the [2015 LAPGAN paper](https://arxiv.org/abs/1506.05751) by Denton et al which is a GAN that starts by generating a low-resolution image and uses a Laplacian pyramid to generate additional images with greater detail and increasing resolution. Second, the [2016 DCGAN paper](https://arxiv.org/abs/1511.06434) on Deep Convolutional GANs by Radford, Metz, and Chintala. Finally, the [InfoGAN paper](https://arxiv.org/abs/1606.03657) by Chen, Duan, et al. which provides a more structured understanding of the how to precisely manipulate images building on the accuracy introduced by LAPGANs.