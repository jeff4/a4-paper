---
author: Jeff Hwang
pubDatetime: 2023-04-15T18:53:00Z
title: InstructGPT and How LLMs are Trained
postSlug: 2019-04-15-instructgpt-and-how-llms-are-trained
featured: false
draft: false
tags:
  - tech
  - machine-learning
  - tech-history
  - ai
  - prompt-engineering
  - fine-tuning
  - rag
ogImage: ""
description:
  Notes on Ari Seff's January 2023 video on InstructGPT, prompt engineering, and RAG
---

Some quick personal notes on [Ari Seff's](https://www.ariseff.com) excellent and still relevant [January, 2023](https://www.youtube.com/watch?v=VPRSBzXzavo) YouTube on "ChatGPT and how it's trained". In fact, the video is broader than just OpenAI's work; it describes the general process by which most LLMs constructed: (1) First, train a foundation model with unsupervised data; and then (2) fine-tune with instructions and ground-truth supervised label question+answer pairs; and finally (3) improve quality with [RLHF](https://en.wikipedia.org/wiki/Reinforcement_learning_from_human_feedback). 

1. Very early in the video, Seff talks about how InstructGPT was a forerunner to ChatGPT. See this [March 2022 paper](https://arxiv.org/abs/2203.02155) by Ouyang, Wu et al "Training language models to follow instructions with human feedback"
1. What is a language model? (1:49)
	* "A language model is just a special case of an autoregressive sequence model. Aka, given some history of observed variables, where history is specified by variables *x<sub>1</sub>,... x<sub>t</sub>*, what is the value of the next element *x<sub>t+1</sub>*?
	* During training, we adjust the value of the parameters for next element *X<sub>t+1</sub>* such that it more accurately models the 'ground truth' value of *x<sub>t+1</sub>*.
	* This sequence prediction technique has been used in many domains such as audio waveforms, chemical structure prediction (e.g., structures of organic molecules)
	* In the specific example of language models, each of the variables *x<sub>1</sub>,... x<sub>t</sub>* is referred to as a *token*. A token can represent a whole word or just a portion of a word.  
	* Uses the example of the sentence "Alice painted her house `X`". Given history *h*, `X` may taken on any of these values = ['brown', 'beige', 'red', 'because', 'with',...]. Each of these options has its own probability.
	* Language models are agnostic to model architecture. But since the 2017 "Attention is all you need" paper, most language models are huge transformer models with billions of parameters
1. Transformer models since 2017
	* Example models include GPT3 (2020), PaLM (2022) from Google.
	* History that is used to condition the next token prediction only has a limited window, aka context length. For example, the underlying LLM for GPT-3 can attend to a history of about 3000 words. Long enough for short conversations but not long enough for generating a novel.
1. Why is this not enough? Why do we need fine-tuning?
	* Answer: misalignment. Based solely on pre-training, the model is actually trained a mix of many types of tasks. For example, let's say the user asks: 'Explain how the bubble sort algorithm works?'
	* Because there is some large set of examinations in the training corpus, it's likely that the model will reply with something like 'Explain how the merge sort algorithm works?' because that sort of question is one of many that might appear with the bubble question.
	* in order to guide the LLM to the smaller subset of data/training within its model taht is appopriate, we can do a few things to constrain it to a specific subset/task. This can be done by prompt engineering for exampe.
	* One challenge of prompt engineering is that it might be tiresome for the end-user.
1. Thus, part two of building the LLM is supervised fine-tuning 
	* Before the advent of creation of synthetic datasets, people paid pairs of humans to have dialogues. These dialogues have been captured in to a supervised dataset that can be used for fine-tuning.
	* This can be called a typical imitation learning setup, specifically 'behavior cloning' where we try to mimic an expert's `action distribution` conditioned on an `input state`.
	* At (7:15) of the video, good chart showing how the fine-tuned supervised model outperforms prompted GPT which outperforms vanilla GPT with no adjustment at all. Even better b/c it has less need for prompting from an end-user.
		* This chart is from the [March 2022 paper](https://arxiv.org/abs/2203.02155) by Ouyang, Wu et al "Training language models to follow instructions with human feedback"
1. But even fine-tuning still has limitations. 
	* For a variety of reasons, the model may poorly learn the true probability distribution of a human expert. See "Efficient Reductions for Imitation Learning" (2010) by Ross & Bagnell. 
	* As novel states are encountered, the model may compound error after error.
	* It can be shown mathematically that the error rate grows quadratically (x<sup>2</sup>!) if x = length of history.
	* In the case of a LLM, early mistakes during generation can cause it to make overconfident assertions.	
	* In other words, an LLM can't just passively observe an expert during training. It needs to *act* or *interact*
1. RLHF
	* One way to further fine-tune through this interaction is by Reinforcement Learning through Human Feedback
	* Some RL functions already come with a clear reward function. think about traditional Atari arcade games. see ["Playing Atari with Deep Reinforcement Learning" (2013)](https://arxiv.org/abs/1312.5602) by Minh, Kavukcuoglu, et al.
	* Here is the process. 
		* A human has a conversation with the model. the model generates 4-5 responses. then the human ranks those potential responses from most preferred to least. Papers:
			* "Deep reinforcement learning from human preferences" by Christiano et al (2017)
			* "Learning to summarize from human feedback" by Stiennon et al (2020)
		* This preference ranking is summarized into a scalar reard suitable for reinforecment learning like in a video game.
		* Next, a separate 'reward model' is initialized with weights from the supervised model
		* One can turn the ranking of 5 choices into a set of pairs. Aka rather than A > B > C > D, we can have pairs such as: `A > D`, `B > C`, `A > C`, etc.
		* Using a clearer reward function, the reward model and the pre-trained policy model interact with each other in a chat which further optimizes the pre-trained policy model.
		* PPO has become a popular method. See "Proximal policy optimization algorithms" by Schulman et al (2017). see (11:15)
1.  The learned reward model can lead to overoptimazation. Interesting chart at (11:45) from Gao et all 2022 "Scaling Laws for Reward Model Overoptimization". [Goodhart's Law](https://en.wikipedia.org/wiki/Goodhart%27s_law) the version which the video uses: "When a measure [aka metric] becomes the target, it ceases to become a good measure." 
	* The authors of the InstructGPT paper try to get around this by adding an additional term that penalizes the KL divergence between the RL policy and the policy previously learned from supervised fine-tuning.
1. The combination of reward modeling (reward model + policy model interaction) and PPO is repeated several times.
	* At each iteration, the updated policy can be used to gather more reponses for preference ranking and a new reward model is trained. Then the policy model is updated again through another round of PPO.
1. See chart from InstructGPT Ouyang paper at (12:35). Shows how PPO > supervised fine-tuning > prompted GPT > vanilla GPT. 
	* The combo of supervised fine-tuning (SFT) plus RHLF/PPO means that the resulting 1.3 B parameter model provides chat answers that human reviewers *prefer* over the simply prompt-trained GPT-3 model with 175-B parameters. a 100x improvement in efficiency as measured by number of parameters!!
1. Despite all this improvements, Chat-GPT's behavior is still highly dependent on the wording of input / prompts.
