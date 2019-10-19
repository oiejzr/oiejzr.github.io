---
layout: post
title: 'CCF2019 CSP-S/J 游记'
subtitle: '到湖大的综合楼门口，发现旁边全是雅礼一中师大附中的，瑟瑟发抖
湖大教室似是确乎有趣，趁着他在那里畅谈所谓「CCF NOIP考场纪律」，不知的为何便努力地玩起了椅子，~~差点卡在椅子里~~'
date: 2019-10-19
categories: 游记
cover: 'https://s2.ax1x.com/2019/10/19/KnjAr6.md.png'
tags: travelNotes
---

## 绪言·参考资料

~~其实不想写初赛游记，但是我太蒟，原地爆炸可能就没有复赛然后直接退役了~~

- [CCF2019 CSP-J1 C++版 A卷试题](assets\files\入门组C++（CSP2019-junior-C++-A）.pdf)

- [CCF2019 CSP-J1 C++版 A卷参考答案](assets\files\CSP2019-junior-参考答案-A.docx)

- [CCF2019 CSP-S1 C++版 A卷试题](assets\files\提高组C++（CSP2019-senior-C++-A）.pdf)

- [CCF2019 CSP-S1 C++版 A卷参考答案](assets\files\CSP2019-senior-参考答案-A.docx)

## 目录

- Day 0
- Day 1
    - 「上午」CSP-S 退役初赛
    - 「下午」CSP-J 日常劝退
    - 浅谈题目
    - 「晚间」**长郡双语十周年校庆 ×「放耳朵去流浪」特别演唱会**

## Day 0

~~整天复习也没有背下来那些硬件基础知识~~

~~还是不知道TCP/IP到底有什么用~~

~~准备退役弃考~~

听说J组的全是小学生

我这一老爷爷是该退役了Orz.

## Day 1

### 「上午」CSP-S 退役初赛

到湖大的综合楼门口，发现旁边全是雅礼一中师大附中的，~~瑟瑟发抖~~

湖大教室似是确乎有趣，趁着他在那里畅谈所谓「CCF NOIP考场纪律」，不知的为何便努力地玩起了椅子，~~差点卡在椅子里~~

![椅子](https://s2.ax1x.com/2019/10/19/Kno7dA.png)

> 图中红色的部分可以转动，大概和电影院里座位一个样子

然后就发卷子了。

看到答题卡的时候也没有什么意外，毕竟CSP改40道选择题都知道了，但是试卷发下来有点慌，这个读程突然感觉变成选择性阅读理解了，这个完善程序可能就真的成完形了orz

中途我考场有俩上厕所的一进一出，门口一撞，似乎也没有其他考场有趣。

> 我们考场有个人没摘电话手表
>
> 考到一半他妈来电话了
>
> 禁赛三年，全国通报orz
>
>   ——Hello, Luogu

于是题太难，考完直接退役。

外面4号线阜埠河地铁站，罐子岭方向，我去就看到前边站台全是烟，还有焦味

至今不明情况

### 「下午」CSP-J 日常劝退

上午就考的很慌，昨晚上守恒的rp现在没剩多少了

换了一个考场，进去一看果真全是小学生，Orz.

根据优先队列与滑动窗口，窝必将退役。

![KnHTZ4.png](https://s2.ax1x.com/2019/10/19/KnHTZ4.png)

### 浅谈题目

这次的pj和tg可做性总体还可以 ~~（难道是因为选择题可以蒙~~

下面以CSP-S/tg试题为标准

#### 1.题型的变化

- 【共15题单选，每题2分】多选消失，且硬件知识大幅减少，取而代之的是**小学奥数**
- 【共3篇读程，共40分】原来的读程不管用了（CCF或正向选择性阅读理解靠近），题目分成了判断题和选择题，主要考察对算法特点的熟练掌握（*eg.时间复杂度的计算*）与对过程的清晰理解。
- 【共2篇完形，每题3分，共30分】*这 真 的 是 完 形*<br>除了改成选择题外，基本没有变化。

#### 2.考察的知识点

- 作为一个算法竞赛，CSP初赛中的语言知识正在增加。包括运算顺序，浮点数的运算等。

- 读程考察到拓扑排序，（不带路径压缩的）并查集，子序列。

- 完形似乎是一个大模拟和一个状压dp（这个状压dp完全不可做！~~（我太蒟了）~~）

#### 3.试题小议

![KnLXzq.png](https://s2.ax1x.com/2019/10/19/KnLXzq.png)

*我太蒟了，记得做过这题，然而不记得答案。*

*后续补这题解析*

---

![KnOVQx.png](https://s2.ax1x.com/2019/10/19/KnOVQx.png)

我们可以看到，多源最短路Floyd是基于dp的。

---

![KnO0Yj.png](https://s2.ax1x.com/2019/10/19/KnO0Yj.png)

一道简单的dp求状态转移方程。

显然，在除根结点外的每一个点$a_(i,j)$中，都存在到这个点上来的至少两者之一的状态

$$a_(i-1,j-1), a_(i-1,j)$$

因此，点$a_(i,j)$即状态数，为

$$max(a_(i-1,j-1), a_(i-1,j))$$

### 「晚间」**长郡双语十周年校庆 ×「放耳朵去流浪」特别演唱会**

# 双语生日快乐！！！

（多图预警 夜店警告

[![KnjAr6.md.png](https://s2.ax1x.com/2019/10/19/KnjAr6.md.png)](https://imgchr.com/i/KnjAr6)

[![KnjuPH.md.png](https://s2.ax1x.com/2019/10/19/KnjuPH.md.png)](https://imgchr.com/i/KnjuPH)

[![KnXfDf.md.png](https://s2.ax1x.com/2019/10/19/KnXfDf.md.png)](https://imgchr.com/i/KnXfDf)

[![KnXIUg.md.png](https://s2.ax1x.com/2019/10/19/KnXIUg.md.png)](https://imgchr.com/i/KnXIUg)

[![KnX7Cj.md.png](https://s2.ax1x.com/2019/10/19/KnX7Cj.md.png)](https://imgchr.com/i/KnX7Cj)

[![KnXqvq.md.png](https://s2.ax1x.com/2019/10/19/KnXqvq.md.png)](https://imgchr.com/i/KnXqvq)

[回放网址](https://vzan.com/live/tvchat-194633513?ver=637070375151473825&shareuid=115571226&vprid=0&from=groupmessage&isappinstalled=0#/)

---

相当开心，于是回来对了csp答案

...

## 记 OIejzr の「退役祭」