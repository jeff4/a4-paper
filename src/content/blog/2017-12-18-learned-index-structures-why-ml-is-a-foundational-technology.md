---
author: Jeff Hwang
pubDatetime: 2017-12-18T02:29:00Z
title: Learned Index Structures–Why ML is a Foundational Technology
postSlug: 2017-12-18-learned-index-structures-why-ml-is-a-foundational-technology
featured: false
draft: false
tags:
  - tech
  - machine-learning
  - google
  - microsoft
  - tech-history
  - research
  - ai
ogImage: ""
description: Really exciting paper on how AI is a stacking technology that improves other technologies--in this case improving efficiency of data structures.
---

A [recent paper published by Google Research](https://www.arxiv-vanity.com/papers/1712.01208v1/) provides more evidence that machine learning is a foundational technology that is as significant as [electrical power](http://www.slate.com/articles/arts/the_undercover_economist/2007/06/the_shock_of_the_new.html), [relational databases](/posts/2017-05-15-relational-database-systems-and-ai), or [the internet](https://stratechery.com/2017/defining-aggregators/).

[The Case for Learned Index Structures](https://www.arxiv-vanity.com/papers/1712.01208v1/) by Kraska, Beutel, et al. examines what happens if one uses bottom-up ML techniques to optimize classic data structures such as [B-trees](https://en.wikipedia.org/wiki/B-tree), [hash maps](https://en.wikipedia.org/wiki/Hash_table), and [Bloom filters](https://en.wikipedia.org/wiki/Bloom_filter). The Google team propose using *learned indexes*, which rebuild the fundamental data structures used bottom-based on the specific characteristics of particular datasets. Historically, this was impractical because one would not re-implement a new index for each new application or dataset. However, machine learning allow us to optimize indexes that are specifically tuned to each and every application. 

The tech industy has had decades to optimize hardware memory, cache, and CPU to make classical indexes efficient. As such, it will take several years of R&D to bring learned indexes into production. However, this is already a promising research direction that suggests something new. Much faster, more efficient, and customized data indexes mean new data stores, new applications, and eventually, new businesses.

This aspect of machine learning specifically (and AI more generally) that excites me most. I get the impression that a lot of popular press about AI has been focused: (a) fears of an AI Singularity / take over by artificial general intelligence or (b) consumer-facing voice assistants (such as Alexa, Siri, Cortana) and their related smart speakers or (c) industry pushes like bots by Facebook. In contrast, papers like this show how AI has the potential to transform technology behind the scenes, which eventually makes new technologies, products, and companies available. Walmart could never have become the giant it did without foundational building blocks like the internal combustion engine, trucks, the interstate highway system, and relational databases. In the 2030's, what will be the new Walmarts enabled by far more efficient data structure indexes?

(h/t to former [Microsoft exec Steven Sinofsky](https://en.wikipedia.org/wiki/Steven_Sinofsky) for [highlighting](https://twitter.com/stevesi/status/940120951940825088) this paper.)