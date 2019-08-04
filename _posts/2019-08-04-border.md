---
layout: post
title: 图像边缘检测
categories: blog
tags: [好玩的]
description: 没有。
---

初始图像
<img src="/img2019/miyuki0.png" width = "300" height = "424" alt="miyuki"/>

首先将RGB图像转成灰度值（下图左）
```
grayScale = ( (0.3 * R) + (0.59 * G) + (0.11 * B) )
```
尝试直接用每个点的灰度值减去其左侧点的灰度值，效果并不理想（下图中）
对灰度图像施加高斯模糊（下图右）

![1](/img2019/miyuki1.png)





