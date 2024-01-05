---
layout: ../layouts/timeLayout.astro
title: "AI Timeline"
---
## 1940's
* **1943** - [McCulloh](https://en.wikipedia.org/wiki/Warren_Sturgis_McCulloch) and [Pitts](https://en.wikipedia.org/wiki/Walter_Pitts) introduce the Perceptron in their paper 'A logical calculus of ideas immanent in nervous activity'.
* **1946** - First [Macy Cybernetics Conference](https://en.wikipedia.org/wiki/Macy_conferences#Cybernetics_Conferences) held in New York. They would continue through 1953.
* **1947** - In response to a challenge by Gestalt theorists at the Macy conferences, McCulloh and Pitts publish 'How We Know Universals: The Perception of Auditory and Visual Forms'.
* **1948**
	* Norbert Weiner publishes first edition of [*Cybernetics*](https://en.wikipedia.org/wiki/Cybernetics:_Or_Control_and_Communication_in_the_Animal_and_the_Machine).
	* September: [Hixon Symposium](https://www.lancaster.ac.uk/fas/psych/glossary/hixon_symposium/) at Caltech in September, 1948.
* **1949** - [Donald Hebb](https://en.wikipedia.org/wiki/Donald_O._Hebb) proposes Hebbian Learning in *The Organization of Behavior*.  

## 1950's
* **1956** - Dartmouth Conference with John McCarthy.
* **1957** - [Frank Rosenblatt](https://en.wikipedia.org/wiki/Frank_Rosenblatt) builds the first mechanical [implementation of the perceptron](https://en.wikipedia.org/wiki/Perceptron#Mark_I_Perceptron_machine) at the Cornell.


## 1960's
* **1969** - MIT mathematicians Minsky and Papert publish *Perceptrons*, their famous critique of single-layer perceptrons leading to the first AI winter. In other words, perceptrons can only classify data that is linearly separable; they cannot implement the XOR function.

## 1970's
* **1974** - As part of his PhD work, Paul Werbos develops an early version of the backpropagation algorithm. Although this will be a critical step in training multi-layer perceptrons, Werbos does not include it in his dissertation because of the skepticism about perceptrons during this AI winter.


## 1980's
* **1982** - J.J. Hopfield publishes 'Neural networks and physical systems with emergent collective computational abilities' about Hopfield networks.
* **1986** - Hinton (along with co-authors Rumelhart and Williams) popularized [the backpropagation algorithm](https://en.wikipedia.org/wiki/Backpropagation#History) and published empirical results of its usefulness in [this landmark paper.](https://www.iro.umontreal.ca/~vincentp/ift3395/lectures/backprop_old.pdf)
* **1988** - Bourland and Kamp 'Auto-association by multilayer perceptrons and singular value decomposition'.
* **1989** 
	* Baldi and Hornik 'Neural networks and PCA: learning from examples without local minima'. PCA = Principal Components Analysis.
	* Hornik, Stinchcombe, and White publish 'Multilayer feedforward networks are universal approximators', proving that with enough layers, MLPs can theoretically implement any function including XOR.
	* LeCun [applied the backprop algorithm to convolutional neural networks (CNNs)](https://en.wikipedia.org/wiki/Convolutional_neural_network#Image_recognition_with_CNNs_trained_by_gradient_descent) and showed how it was successful at computer vision tasks like [recognizing handwritten numerals](http://yann.lecun.com/exdb/publis/pdf/lecun-89e.pdf).


## 1990's
* **1993** 
	* Hinton and Zemel 'Autoencoders, Minimum Description Length and Helmholtz Free Energy' introduce autoencoders as a method for unsupervised learning where ANNs can learn approximate probability distributions.
	* Problems with Recurrent Neural Networks described in Bengio 'A Connectionst Approach to Speech Recognition'.
* **1998** - Lecun, Bottou, Bengio, and Haffner publish 'Gradient-based learning applied to document recognition', indicating that 5th version of LeNet is good enough at handwriting recognition that it is processing ~10% of all handwritten checks in the US.

## 2000's
* **2003** - Bengio et al 'A Neural Probablisitic Language Model'.
* **2004** - Hinton secured a small but important amount of funding from the Canadian Institute for Adavanced Research (CIFAR) to [convene a continuing group of people to work on neural networks](https://www.wired.com/2014/01/geoffrey-hinton-deep-learning/). The two co-directors for this [CIFAR program](https://www.cifar.ca/cifarnews/2019/03/27/turing-award-honours-cifar-s-pioneers-of-ai) were Bengio and LeCun. This working group was critical to advancing what eventually became deep learning.
* **2006** - Hinton and Osindero published a [seminal paper on Deep Belief Networks](https://www.cs.toronto.edu/~hinton/absps/fastnc.pdf) which showed that ANNs with multiple hidden layers could actually perform reasonably well -- despite the poor reputation of ANNs at the time. 

## 2010's
* **2012** - Two of Hinton's students, Alex Krizhevsky and Ilya Sutskever built a deep CNN called [AlexNet](https://en.wikipedia.org/wiki/AlexNet) that used an algorithm they dubbed SuperVision [to win the annual ImageNet competition](https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf) by a resounding margin. 
* **2014** 
	* Bengio and his student [Ian Goodfellow](https://www.theverge.com/2019/4/5/18296473/apple-google-ai-research-poached-ian-goodfellow) published the [first paper](https://arxiv.org/abs/1406.2661) on [Generative Adversarial Networks (GANs)](https://en.wikipedia.org/wiki/Generative_adversarial_network).
	* Cho, Bahdanau, Bengio et al. publish two papers 'Learning Phrase Representations using RNN Encoder–Decoder for Statistical Machine Translation' and 'On the Properties of Neural Machine Translation: Encoder-Decoder Approaches'. Together, they bring the encode-decode architecture to deep NNs. Forerunner to Transformer paper.
* **2015** - Sohl-Dickstein et al. publish 'Deep Unsupervised Learning using Nonequilibrium Thermodynamics' which introduces diffusion models from physics into deep learning. These models are the foundation of image generation networks like DALL-E, Midjourney, and Stable Diffusion.
* **2017** - Transformer architecture introduced in Google paper 'Attention is All You Need'.
* **2023** - ChatGPT launches in late November, 2023.
