---
author: Jeff Hwang
pubDatetime: 2019-04-04T14:47:00Z
title: Turing Award Recognizes Bengio, Hinton, and LeCun 
postSlug: 2019-04-04-turing-award-recognizes-bengio-hinton-lecun
featured: true
draft: false
tags:
  - tech
  - machine-learning
  - tech-history
  - ai
  - gpu
ogImage: ""
description:
  An brief history of neural networks from 1986-2014.
---

Last week the "Nobel Prize of Computing" was awarded to three pioneers of deep learning and I decided to revisit the history of neural networks from 1986-2014.

On March 27th, the [Association for Computing Machinery](https://en.wikipedia.org/wiki/Association_for_Computing_Machinery) awarded the [2018 Turing Award](https://awards.acm.org/about/2018-turing) to [Geoff Hinton](https://en.wikipedia.org/wiki/Geoffrey_Hinton), [Yann LeCun](https://en.wikipedia.org/wiki/Yann_LeCun), [Yoshua Bengio](https://en.wikipedia.org/wiki/Yoshua_Bengio) for their contributions to deep learning. The three "godfathers of deep learning" have worked together on and off for decades; they and their collaborators stubbornly kept working on artificial neural networks through multiple [AI winters](https://a16z.com/2016/06/10/ai-deep-learning-machines/) and periods when the usefulness of ANNs were dismissed by the rest of the computer science community. Just a few of the critical moments in their shared history:

* **1986** Hinton (along with co-authors Rumelhart and Williams) popularized [the backpropagation algorithm](https://en.wikipedia.org/wiki/Backpropagation#History) and published empirical results of its usefulness in [this landmark paper.](https://www.iro.umontreal.ca/~vincentp/ift3395/lectures/backprop_old.pdf)
* **1989** LeCun [applied the backprop algorithm to convolutional neural networks (CNNs)](https://en.wikipedia.org/wiki/Convolutional_neural_network#Image_recognition_with_CNNs_trained_by_gradient_descent) and showed how it was successful at computer vision tasks like [recognizing handwritten numerals](http://yann.lecun.com/exdb/publis/pdf/lecun-89e.pdf)
* **2004** Hinton secured a small but important amount of funding from the Canadian Institute for Adavanced Research (CIFAR) to [convene a continuing group of people to work on neural networks](https://www.wired.com/2014/01/geoffrey-hinton-deep-learning/). The two co-directors for this [CIFAR program](https://www.cifar.ca/cifarnews/2019/03/27/turing-award-honours-cifar-s-pioneers-of-ai) were Bengio and LeCun. This working group was critical to advancing what eventually became deep learning.
* **2006** Hinton and Osindero published a [seminal paper on Deep Belief Networks](https://www.cs.toronto.edu/~hinton/absps/fastnc.pdf) which showed that ANNs with multiple hidden layers could actually perform reasonably well (despite the poor reputation of ANNs at the time). This laid the foundation for adding more and more better initialized hidden layers to eventually turn the study of shallow artificial neural networks (ANNs) into the study of deep neural networks (DNNs). For more, see this [very useful history by Andrey Kurenkov](http://www.andreykurenkov.com/writing/ai/a-brief-history-of-neural-nets-and-deep-learning-part-4/).
* **2012** Two of Hinton's students, Alex Krizhevsky and Ilya Sutskever built a deep CNN called [AlexNet](https://en.wikipedia.org/wiki/AlexNet) that used an algorithm they dubbed SuperVision [to win the annual ImageNet competition](https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf) by a resounding margin. The MIT Tech Review published [good general overview of this achievement as of 2014](https://www.technologyreview.com/s/530561/the-revolutionary-technique-that-quietly-changed-machine-vision-forever/). 
	* Andrey Kurenkov's [history of neural networks](http://www.andreykurenkov.com/writing/ai/a-brief-history-of-neural-nets-and-deep-learning-part-4/) gives an excellent perspective on the impact of AlexNet winning in 2012: *Still, having all these research discoveries since 2006 is not what made the computer vision or other research communities again respect neural nets. What did do it was something somewhat less noble: completely destroying non-deep learning methods on a modern competitive benchmark [in the 2012 ImageNet competition]...It is very striking to now understand that [their work](https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf)...is the combination of very old concepts (a CNN with pooling and convolution layers, variations on the input data) with several new key insight (very efficient GPU implementation, ReLU neurons, dropout), and that this, precisely this, is what modern deep learning is...This, the first and only CNN entry in that [2012] competition, was an undisputed sign that CNNs, and deep learning in general, had to be taken seriously for computer vision. Now, almost all entries to the competition are CNNs - a neural net model Yann LeCun was working with since 1989.*
* **2014** Bengio and his student [Ian Goodfellow](https://www.theverge.com/2019/4/5/18296473/apple-google-ai-research-poached-ian-goodfellow) published the [seminal paper](https://arxiv.org/abs/1406.2661) introducing [Generative Adversarial Networks (GANs)](https://en.wikipedia.org/wiki/Generative_adversarial_network) which quickly inspired a [Cambrian Explosion of GANs](https://github.com/hindupuravinash/the-gan-zoo/blob/master/README.md) used for synethic image generation, translation of text to image, [realtime conversion of sketch to photorealistic outputs](/blog/2019/03/21/top-of-mind-04), deep fakes, audio synthesis, and many other applications.  
* The current fascination with deep learning can be traced back to 2012 because AlexNet won first place by such a margin and *especially* because it showed how bottom-up training through ANNs could be much more effective than hand-tuned top-down AI techniques. People began seeing how with sufficient computation (through GPUs) and data, one could scale up computer vision performance without applying additional human knowledge-based expertise. 
* In all likelihood, we would not be living in the era of deep learning if not for the persistence and contributions of Hinton, LeCun,  Bengio, and their students and collaborators during the fallow periods of ANNs.

See also this [older post](/posts/2017-10-23-histories-of-deep-learning) with more perspectives on the history of artificial neural networks.
