---
showonlyimage: true
title:      "Topological photonics 综述 （待续）"
subtitle:   "拓扑光子学"
excerpt: " "
description: "这是一个非常有意思的平台，我们能从中发现很多有意思的现象。"
date:  2023-08-12
author:  陈诗曰
image: "/img/contact-bg.jpg"
published: true 
tags:
    - Physics
categories: [ Physics ]
math: true

---

## Introduction

从实验手段上来讲，topological lattice可以在electric、photonics和acoustic上实现。Electric即传统的topological insulator赛道， 2d topological insulator主要是在2005年左右由C.L.Kane和张首晟等人预测，开始了一系列以Z-2 拓扑不变量和time reversal symmetry来讲故事的topological insulator时代。而把这套概念迁移到photoncis领域就是yidong所的topological photonics领域了。Haldane等人预测了在光学领域存在类似topological insulator的现象，而在08年yidong和wang zheng发表的论文 (Wang, Zheng, et al. "Reflection-free one-way edge modes in a gyromagnetic photonic crystal."  Physical review letters 100.1 (2008): 013905.) 提供了用gyromagnetic photonic crystal 来模拟electronic insulator的实验方法， 而在gyromagnetic photonic crystal中的TM modes可以map到周期电磁场中的电子波。

拓扑物理本质上还是经典物理，但是能够用一套新的数学语言来描述。

从光学到声学，再到力学和电子学（电路），不仅是实验介质、工作波段的区别。

有些很有意思的现象，比如high-oder topological insulator，目前可能只有在topological photonics的平台上实现。而在经典的电子体系中难度却很大。

如何把 Classical wave 和 machine learning联系起来呢？经典波其实已经完全可以用Maxwell equation解释了，那还需要ml干什么？

龙洋在这方面做了一些拓扑分类的工作，我觉得很有意思。


## topological invariant

Z2 topological invariant

## Time reversal symmetry


为什么time reversal symmetry这个关键呢？

1. time reversal 算符以及为什么会是这样？

The anti-unitary time T operator is given by: 
$$
\left(
\begin{matrix}
1&0\\ 0&-1
\end{matrix}
\right)K
$$
which square to unity, where K is complex conjugation. 

2. Time reversal symmetry bettween electrons and photons

A photon is a neutral non-conserved non-interacting spin-1 Boson that satisfies Maxwells equations.

An electron is a charged conserved interacting spin-1 fermion that satisfies Schrodinger equation.

Ref: https://www.nature.com.remotexs.ntu.edu.sg/articles/nphoton.2014.248


## 实现topological photonics的平台


### gyromagnetic photonic crystal

Yidong的最初nature的工作就是在这个体系上做的，最近几年guigeng也在这个领域做了不少的工作。


### coupled resonators


### Bi-anisotropic metamaterials （双各向异性超构材料）

### quasicrystals

## 3d topological photonics

weyl points


## others

Degrees of freedom in photonic system:
Frequency
wavevector
polarization
phase

现在topological invariant也是一个新的自由度了。

