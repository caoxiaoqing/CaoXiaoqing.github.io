---
layout: post
title:  "curveball优化算法推导"
date:   2018-08-08 00:00:00
author: caoxiaoqing
categories: 算法
tags: 算法 优化 
---

* content
{:toc}
前段时间，VGG 的一拨人搞了个叫 curveball 的优化算法，能够将二阶信息用起来，同时避免了之前的传统方法要么去近似 Hessian 矩阵的逆，要么通过 conjugate-gradient 的方法去得到 Hessian 矩阵的逆，这些传统方法既耗时又对噪声敏感。而 curveball 算法并不需要直接算 Hessian 矩阵和它的逆，每次只是去估计梯度与 Hessian 矩阵的乘积即可，所付出的代价仅仅是额外的两次正向传播。 由于这篇文章写的极为简略，很多过程都直接略掉了，今天我们就来推导这个算法，将作者略去的部分补上。

文章链接：[点我](https://arxiv.org/abs/1805.08095)

文章代码 github 链接：[点我](https://github.com/jotaf98/curveball)

本文推导内容的 pdf 链接：[点我](/media/docs/curveball algorithm/curveball algorithm推导.pdf)



### 推导细节

![1](/media/docs/curveball algorithm/images/img10.jpg)

![2](/media/docs/curveball algorithm/images/img12.jpg)

![3](/media/docs/curveball algorithm/images/img14.jpg)

![4](/media/docs/curveball algorithm/images/img16.jpg)

![5](/media/docs/curveball algorithm/images/img18.jpg)