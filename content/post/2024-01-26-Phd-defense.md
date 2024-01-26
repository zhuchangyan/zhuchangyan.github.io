---
showonlyimage: true
title:     "Phd oral defense"
subtitle:   "Application of machine learning methods in photonics and non-Hermitian physics"
excerpt: " "
description: "Here is the draft version of my oral defense."
date:    2024-01-26
author: 陈诗曰
# image: "/img/einstein.png"
published: true 
tags:
    - Physics
categories: [ Physics ]
math: true
---

Date: 2024.02.08


# introduction

Hello everyone!

My phd thesis is about the use of machine learning methods in physics research. As everybody knows, artificial intelligence is a hot topic nowadays, not only in fictions, products such as Alphago and chatgpt has shocked peoples eyes and made many of us believe that one day the machine is going to develop new intelligence.

![Alt text](Figs/image0_AI_differences.png)

However, I felt that there is a need to distinguish the following three concepts. 

AI, as a general method for human intelligence simulation, includes a broad range of topics from logical-based reasoning to expert systems. 
As a part of AI, machine learning focuses on learning systems that learn from past experience, e.g.., models that are trained on datasets. 
Deep learning, as a subfield of machine learning, focuses on the use of artificial neural networks with representation learning.



The essence of machine learning is to **pepresent the data in an undefined way**.
* In supervised learning, we train the neural newtork to approximate the relationship between input and output training data.
* In unsupervise learning, we map the training data into a certain kind of data structure to make inferences on datasets.


We will focus our attention on supervised learning at first. The most popular way is to use neural network.


## What is neural network

There are two types of neural network.

![Alt text](Figs/neural_network_structure.png)

First we have dense neural networks, or we can say fully connected layers because every nodes are fully connected to next layers by weights. It's the most elementary version of neural networks, inspired by neuron connections in human brain. Another type is convolution neural networks inspired by human vision process, therefore are widely used in image related tasks.


### why do we use neural networks in physics?


In physics, relationships between different quantities are often represented as formulas, for example in quantum mechanics we have schrodinger euqation $x = vt$, with the explicity known formula, you can explain the moving distance 

$$i\hbar \frac{\partial | \Psi \rangle}{\partial t} = H |\Psi \rangle$$

[fig: schrodinger equation]

In my Phd study I have explored 4 different areas which machine learning methods could bring new insights 


For complex systems, it's hard to write down the formulas explicily.


**The function of neural network** : Approximate the relationships between different quantities using a predifined mathematical structure.

# What kind of physical systems is suited

supervised learning 

In order to maximize the potential of ML in physics problems, the physics system should 
* include large enough parameters
* the input and output are easy to obtain 
* No analytical solution/ Analytical solutions are hard to obtain.

unsupervised learning

* metrics 
* 



# Multimode fiber imaging

The first system we found interesting is the multimode fiber.

![Alt text](image.png)

Different modes inside MMF will propagate along different optical paths, therefore create a phase difference, this is called mode dispersion. Together with mode mixing and  mode-dependent loss, the output end of a MMF are usually seemingly random speckled patterns which are far from the original input.

$$E_{output} = T_{N \times N} E_{input} \quad   (1)$$

A MMF usually holds thousand of modes, therefore the relation between input and output patterns are usually connected by a transmission matrix with size $N \times N$ with $N > 1000$. What's important is in actual MMF applications only intensity information is recorded, therefore it's actually impossible to retrieve the input without phase information given. 

Hence, here is the chance when neural network show its power.
The neural network only need to know the input and output images, of course, to improve the reconstruction accuracy, we need a large enough dataset. Therefore, we collected 10k pair of image and try to build the connection between input and output channels.


# real time terahertz beamforming

Another interesting phenomena that we are interested in is the real time terahertz beamforming.
As a milestone for 6G terahertz communication, the antenna doesn't always go to the direction that we want it to. For example


# random spectrometry


# non-Hermitian physics


# Conclusion and future work




