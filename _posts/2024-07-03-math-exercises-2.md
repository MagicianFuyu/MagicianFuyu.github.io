---
layout: post
title: Math Exercises 2
categories:
- Math
- Exercises
tags:
- math
math: true
mermaid: true
toc: true
comments: true
description: 每日一道数学散题
date: 2024-07-03 00:00 +0000
---
## 题目描述
原题：[2012 AMC 10A, Problem 24](https://artofproblemsolving.com/wiki/index.php/2012_AMC_10A_Problems/Problem_24)

设正整数 $a, b, c$ 满足 $a \ge b \ge c$ ，且 $a^2-b^2-c^2+ab=2011$ ，$a^2+3b^2+3c^2-3ab-2ac-2bc=-1997$。求 $a$ 的值。

## 解题思路
将两个等式相加，我们得到

$$
    2a^2+2b^2+2c^2-2ab-2ac-2bc=14
$$

将式子变形，即：

$$
    (a-b)^2 + (a-c)^2 + (b-c)^2 = 14
$$

依题意，满足上式的解仅有 $14=1+4+9$。由于 $a \ge b \ge c$ ，可得 $a-c=3$ ，且

$$
    \begin{cases}
        b-c = 1 \\
        a-b = 2
    \end{cases}
    \text{或}
    \begin{cases}
        b-c = 2 \\
        a-b = 1
    \end{cases}
$$

即 $(a,b,c) = (a, a-1, a-3)$ 或 $(a, a-2, a-3)$。

考虑第一个解，代入原等式化简得 $7a=2021$ ，显然矛盾。代入第二个解化简得 $8a=2024$ ，解得 $a=253$ ，故原题解为：

$$
    \boxed{a=253}
$$
