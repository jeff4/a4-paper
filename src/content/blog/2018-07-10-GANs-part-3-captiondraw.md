---
author: Jeff Hwang
pubDatetime: 2018-07-10T01:42:00Z
title: GANs Part 3–CaptionDraw
postSlug: 2018-07-10-gans-part-3-captiondraw
featured: false
draft: false
tags:
  - tech
  - research
  - machine-learning
  - ai
  - generative
ogImage: ""
description:
  Product idea involving generative adversarial networks.
---

My recent [posts](/posts/2018-06-15-generative-adversarial-network) on [generative adversarial networks](/posts/2018-06-20-gans-part-2-counterfeit-money) (aka GANs) still feel a bit abstract. Perhaps a more concrete product idea will help. Let's call it *CaptionDraw*, a personal digital sketch artist.

Kids love to draw, to color, to cut and to paste. Whether they're using colored pencils, construction paper, glue, or touchscreens,  children seek to express themselves visually. 

Let's say 6-year-old Jesse wants to tell a story about a blue unicorn and a pink dragon who live in the forest together. Jesse *could* illustrate this story using crayons. But Jesse is lucky enough to have Uncle Walt who happens to be a professional animator. Uncle Walt might listen to Jesse's verbal descriptions and draw these characters for Jesse in a manner similar to the origin of [Winnie-the-Pooh](https://en.wikipedia.org/wiki/Winnie-the-Pooh#Origin) and [Alice in Wonderland](https://en.wikipedia.org/wiki/Alice%27s_Adventures_in_Wonderland#Background).  Or Uncle Walt might draw Jesse's unicorn and dragon in the manner of  [Dave DeVries](https://goodmenproject.com/arts/the-monster-engine-an-interview-with-dave-devries/) and his [Monster Engine](https://www.themonsterengine.com/about) drawings.<sup><a href="#fn1" id="ref1">1</a></sup>

Most kids don't have an Uncle Walt the way Jesse does–which is great for children's independence, creativity, and self-expression. But imagine if every child *could* have their own personal Uncle Walt. That's what CaptionDraw is–a digital Uncle Walt, partly powered by GAN technology. 

Any child that wanted to conjure characters, monsters, and scenes could simply describe them to CaptionDraw which would then obligingly draw realistic 2D and 3D renderings. Like a police sketch artist, CaptionDraw would reproduce something close to what a kid sees in their mind's eye. 

Looking more broadly, there is a whole universe of adults who have the desire to express themselves visually but don't have the training and experience to do so. Today, communicating in high fidelity 2D and 3D is the province of a small set of people. This group includes the highly trained designers and animators working at film and game studios, architecture and design firms, and various types of engineering companies. It also includes the many professionals and amateurs who have the traditional drawing and painting skills to communicate visually. CaptionDraw could serve as a personal digital sketch artist for everyone. The smartphone revolution has made high-quality, portable, and easy-to-use cameras available to billions more people than before. In a similar way, children and adults with access to CaptionDraw in the future would vastly expand the number of people who can express themselves in a way similar to the way people at Pixar do today. 

Does CaptionDraw sound like science fiction? The core engine for the product can be glimpsed in a series of papers over the last four years. Using image processing, GANs and related neural net techniques, researchers have shown impressive progress in accepting simple text captions as input and generating close to photorealistic images as output.<sup><a href="#fn2" id="ref2">2</a></sup> 

Of course, a lot more work is needed to make CaptionDraw a reality.  But if something like CaptionDraw could be developed, think of all the other uses we could have for a smart, talented Uncle Walt who can draw whatever you ask!


---
<sup id="fn1">1. For an funny and creepy variation of this idea, check out this article about a [Dad bringing his 6-year-old son's drawings to life](https://www.boredpanda.com/kid-drawings-things-i-have-drawn-dom/). Similarly, Gianluca Gimini [makes professional 3-D renders](https://www.dezeen.com/2016/06/19/velocipedia-project-hopeless-bicycle-drawings-life-digital-renders-gianluca-gimini/) of hazily remembered bicycle sketchs to amusing effect in his Velocipedia project.<a href="#ref1" title="Return to text.">↩</a></sup>

<sup id="fn2">2. My favorite paper in the area of caption-to-image GANs is this [2017 paper by Zhang et al.](https://arxiv.org/abs/1612.03242) proposing a StackGAN architecture. StackGAN references the [caption-to-image work by Reed, Akata, et al.](https://arxiv.org/abs/1605.05396), the related [GAWWN architecture](https://arxiv.org/abs/1610.02454), and the very interesting [LAPGAN ](https://arxiv.org/abs/1506.05751)–a Laplacian pyramid-based GAN proposed by Denton, Chintala et al. in 2016. Finally, virtually all the GAN papers since 2015 have referenced conditional GANs introduced by [Mirza](https://arxiv.org/abs/1411.1784) in 2014 and applied to faces by [Gauthier](https://pdfs.semanticscholar.org/42f6/f5454dda99d8989f9814989efd50fe807ee8.pdf) in 2015.<a href="#ref2" title="Return to text.">↩</a></sup>
