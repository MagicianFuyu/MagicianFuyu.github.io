---
layout: post
title: Math Exercises 1
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
date: 2024-07-02 00:00 +0000
---
## 题目描述
对于数列 $1，11，111，1111， \cdots $ 

除了第一项 $ 1 = 1^5 $，是否存在其他数列项是五次方数？

## 解题思路
该数列的通项公式可以表示为：

$$
    a_{n} = \frac {10^{n} - 1}{9}
$$

考虑反证法，假设从第二项往后存在数列项是五次方数，即：

$$
    \frac {10^{n} - 1}{9} = a^5, n \ge 2, a \in \mathbb{N}
$$

即等式 $ 10^n - 1 = 9a^5 $。

考虑 $ 10^n - 1 \pmod{5} $：

$$
    \begin{aligned}
        &\because 10 \equiv 0 &&\pmod{5} &\\
        &\therefore 10^n \equiv 0^n \equiv 0 &&\pmod{5} &\\
        &\therefore 10^n - 1 \equiv 0 - 1 \equiv -1 &&\pmod{5} &
    \end{aligned}
$$

考虑 $ 9a^5 \pmod{5} $：

$$
    \begin{aligned}
        &\because 9 \equiv 4 &\pmod{5} \\
        &\therefore 9a^5 \equiv 4a^5 &\pmod{5}
    \end{aligned}
$$

结合上面的结果：

$$
    \begin{aligned}
        &\because 10^n - 1 = 9a^5 \\
        &\therefore -1 \equiv 4a^5 \pmod{5}
    \end{aligned}
$$

利用 $ 4 \equiv -1 \pmod{5} $：

$$
    \begin{aligned}
        &\because 4 \equiv -1 &\pmod{5} \\
        &\therefore 4a^5 \equiv (-1)a^5 &\pmod{5} \\
        &\therefore -1 \equiv -a^5 &\pmod{5}
    \end{aligned}
$$

也就是：

$$
\boxed{a^5 \equiv 1 \pmod{5}}
$$

由于 $5$ 是质数，根据费马小定理，得到 $ a \equiv 1 \pmod{5} $。

不妨令 $ a = 5k + 1 $, $k$ 为非负整数，则

$$
    10^n - 1 = 9(5k + 1)^5, k \ge 0
$$

将上式右侧展开，得到

$$
    10^n - 1 = 9({\color{red} 5^{5}} k^{5} + {\color{red} 5 \cdot 5^{4}} k^{4} + {\color{red} 10 \cdot 5^{3}} k^{3} + {\color{red} 10 \cdot 5^{2}} k^{2} + {\color{red} 5 \cdot 5} k + 1)
$$

可以看到，右侧前几项均能被 $25$ 整除，于是有

$$
    \begin{aligned}
        10^n - 1  \equiv 9 \pmod{25} \\
        -1 \equiv 9 \pmod{25} \\
    \end{aligned}
$$

最后得到 $ 10 \equiv 0 \pmod{25} $ ，显然矛盾，故原假设有误，该数列第二项以后不存在五次方数。

## 拓展思考
对于第二项以后的数列项，是否能证明其中任意一个项都不是一个大于 $1$ 的正整数的n次方？

根据通项公式，容易得到

$$
    \begin{aligned}
        a_k \equiv 0 \pmod{3} \\
        a_k \equiv 0 \pmod{9} \\
    \end{aligned}
$$

但到此思路中断，下一步也许应该从数位分析入手？