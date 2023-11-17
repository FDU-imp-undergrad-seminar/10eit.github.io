---
layout: post
title: "滤子、超滤子"
date: 2023-08-14
author: 可爱猪仔
tags: [数理逻辑,非标准分析]
---

<head>
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
    <script type="text/x-mathjax-config">
        MathJax.Hub.Config({
            tex2jax: {
            skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
            inlineMath: [['$','$']]
            }
        });
    </script>
</head>

**原型**

对于一个指标集 $I$，在该指标集上定义的超滤子可以认为是一个 $\{0,1\}$ 测度，也即：

$$
\mu :\mathcal{P}( I)\rightarrow \{0,1\} .
$$

然鹅上面的原型需要大家学点实分析，但显然俺不会实分析，我只会爬。我们看一些等价，但是看不出什么motivation的定义：

**定义 - 良滤子（proper filter）**

我们考虑一个定义在集合 $I$ 上的良滤子 $\mathcal{F}$，它其实是满足以下条件的 $I$ 的子集的集合 $\mathcal{F} \subseteq \mathcal{P}( I)$：

1. 若 $X\in \mathcal{F}$ 且 $X\subseteq Y\subseteq I$，则我们有 $Y\subseteq \mathcal{F}$；

2. 若 $X,Y\in \mathcal{F}$，则 $X\cap Y\in \mathcal{F}$；

3. $I\in \mathcal{F}$ 但是 $\emptyset \notin \mathcal{F}$；

4. 对于每一个 $X\subseteq I$，在 $X$ 和 $I\backslash X$ 中有且只有一个属于 $\mathcal{F}$。

满足前两个条件，我们就说 $\mathcal{F}$ 是一个滤子（filter），如果满足前三个条件则是良滤子。良滤子 $\mathcal{F}$ 的子集 $\mathcal{F}_{1} \subseteq \mathcal{F}$ 也是一个滤子，被称为是 $\mathcal{F}$ 的子滤子（subfilter）。

对于四个条件都满足的 $\mathcal{F}$，我们称之为一个超滤子（ultrafilter），通常记为 $U$。

在试图得到一点直观理解之前，我们先看一下 Tarski 的一个结果：

**定理 - Tarski (1930)**

在集合 $I$ 上任意的良滤子都可以被扩张为一个超滤子。

证明咱就不仔细展开了，毕竟我们这课主要目的是给 Newton 招魂的。现在我们来点直觉的例子：

**例子 - 尾滤子基**

我们考虑这样的集合：

$$
\mathcal{F} =\{\{n,n+1,n+2,\dotsc \} :n\in \mathbb{N}\}
$$

它是 $\mathbb{N}$ 上的一个滤子，我们随便写一些元素出来 $\{0,1,\dotsc \} ,\{1,2,\dotsc \}$，如果我们按照 $n$ 给 $\mathcal{F}$ 中的元素排序，我们会发现第 $n+1$ 个集合是并不包含第 $n$ 个自然数的。

这种滤子被称为是自然数序列 $( 1,2,3,\dotsc )$ 的尾滤子基。

**例子 - Hasse 图**

我们考虑集合 $X=\{1,2,3,4\}$ 生成的 Hasse 图：

<img src="C:\Users\PC\AppData\Roaming\Typora\typora-user-images\image-20230814225513803.png" alt="image-20230814225513803" style="zoom:50%;" />

我们知道（依定义）深绿色这一块其实构成了集合 $X$ 的一个滤子，但它不是超滤子，如果我们需要一个超滤子则需要扩张浅绿色这部分子集。

事实上，$X$ 上的滤子 $\mathcal{F}$ 是用来表示一个集合它足够大（large enough）的工具，大到能包含我们需要的子集和需要的所有点。在前面的例子中我们看到，浅绿色部分的子集集合包含了全部含有元素 $1\in X$ 的子集，因此它是一个超滤子。

我们再看一个稍微抽象一点的例子：

**例子 - Frechet 滤子**

对于无限集 $I$，在其上定义的良滤子被称为是 Frechet 滤子，它是 $I$ 中所有余有限（cofinite）子集的集合。包含 Frechet 滤子的超滤子被称为是自由超滤子（free ultrafilter）。

由于 Tarski 定理，我们知道 $I$ 上的自由超滤子总是存在的，因为我们总能将一个 Frechet 滤子扩张成一个超滤子。

但并不是所有的超滤子都会是自由的，下面我们再回到前面的例子，我们要引入一个概念：

**定义 - 主滤子（principal ultrafilters）**

我们定义下面的滤子：

$$
U=\{X\subseteq I:i_{0} \in X\}
$$

对于 $i_{0} \in I$，我们称 $U$ 是定义在 $I$ 上关于 $i_{0}$ 的主滤子，这种主滤子不是自由的超滤子。

我们再来看就不难发现，其实浅绿色的部分为 $\{1\} \in X$ 的主滤子。对于有限基数的集合 $I$，他有且仅有 $n=Card( I)$ 个主滤子