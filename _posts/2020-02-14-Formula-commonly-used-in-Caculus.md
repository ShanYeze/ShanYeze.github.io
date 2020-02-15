---
layout: post
title: "Common calculus formula"
data: 2020-02-11 01:01:01 +0800
categories: Default
tags: test
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


## 极限   
---
### 基本极限
$\lim\limits_{x\rightarrow0}\dfrac{\sin x}{x}=1$
$\lim\limits_{x\rightarrow0}\left(1+x\right)^{\frac{1}{x}}=e$
$\lim\limits_{x\rightarrow\infty}\left(1+\dfrac{1}{x}\right)^x=e$
$\lim\limits_{x\rightarrow0}\dfrac{a^x-1}{x}=\ln a$,  $\lim\limits_{n\rightarrow\infty}\sqrt[n]{n}=1$
$\lim\limits_{n\rightarrow\infty}\sqrt[n]{a}=1(a>0)$
$\lim\limits_{x\rightarrow\infty}\dfrac{a_nx^n+a_{n-1}x^{n-1}+\cdots+a_1x+a_0}{b_mx^m+b_{m-1}x^{m-1}+\cdots+b_1x+b_0}=\begin{cases} \dfrac{a_n}{b_m},&n=m\\ 0,&n<m \\ \infty,&n>m\end{cases}$
$\lim\limits_{n\rightarrow\infty}=\begin{cases}0,&|x|<1 \\ \infty,&|x|>1 \\ 1,&x=1 \\ \text{不存在},&x=-1\end{cases}$
$\lim\limits_{n\rightarrow\infty}e^{nx}=\begin{cases}0,&x<0 \\ +\infty,&x>0 \\ 1,&x=0\end{cases}$

### 常用等价无穷小
当$x\rightarrow0$时，以下等价关系成立：
$x\sim\sin x\sim\tan x\sim\arcsin x\sim\arctan x\sim\ln (1+x)\sim e^x\sim 1$,
$(1+x)^\alpha-1\sim\alpha x$, $1-\cos x\sim \dfrac{1}{2}x^2$, $a^x-1\sim x\ln a$,
$x-\sin x\sim\dfrac{1}{6}x^2$, $\tan x-x\sim\dfrac{1}{3}x^3$, $x-\ln(1+x)\sim\dfrac{1}{2}x^2$,
$\arcsin x-x\sim\dfrac{1}{6}x^3$, $x-\arctan x\sim\dfrac{1}{3}x^3$


## 导数
---
### 基本初等函数导数公式
|基本初等|函数|一阶导数|
|--|--|--|
|$(C)^\prime=0$||$(x^\alpha)^\prime=\alpha x^{\alpha-1}$|
|$(a^x)^\prime=a^x\ln a$, $(e)$||$(e^x)^\prime=e^x$|
|$(\log_ax)^\prime=\dfrac{1}{x\ln a}$||$\left( \ln\vert x\vert\right)^\prime=\dfrac{1}{x}$|
|$(\sin x)^\prime=\cos x$||$(\cos x)^\prime=-\sin x$|
|$(\tan x)^\prime=\sec^2x$||$(\cot x)^\prime=-\csc^2x$|
|$(\sec x)^\prime=\sec x\tan x$||$(\csc x)^\prime=-\csc x\cot x$|
|$(\arcsin x)^\prime=\dfrac{1}{\sqrt{1-x^2}}$||$(\arccos x)^\prime=-\dfrac{1}{\sqrt{1-x^2}}$|
|$(\arctan x)^\prime=\dfrac{1}{1+x^2}$||$(\arcctg x)^\prime=-\dfrac{1}{1+x^2}$|

### 高阶导数公式
$(\sin x)^{(n)}=\sin\left(x+n\cdot\dfrac{\pi}{2}\right)$
$(\cos x)^{(n)}=\cos\left(x+n\cdot\dfrac{\pi}{2}\right)$
$(u\pm v)^{(n)}=u^{(n)}\pm v^{(n)}$
$(uv)^{(n)}=\sum\limits_{k=0}^nC_n^ku^{k}v^{n-k}$


## 泰勒公式
### 泰勒公式
$f(x)=f(x_0)+f^\prime(x_0)(x-x_0)+\dfrac{1}{2!}f^{\prime\prime}(x_0)(x-x_0)^2+\cdots+\dfrac{1}{n!}f^{(n)}(x_0)(x-x_0)^n+R_n(x)$
1. 皮亚诺型余项：$R_n(x)=o(x-x_0)^n$
2. 拉格朗日型余项：$R_n(x)=\dfrac{f^{(n+1)}(\xi)}{(n+1)!}(x-x_0)^{(n+1)}$

### 常用泰勒公式
1. $e^x=1+x+\dfrac{x^2}{2!}+\cdots+\dfrac{x^n}{n!}+\dfrac{e^{\theta x}}{(n+1)!}x^{n+1}$
2. $\sin x=x-\dfrac{x^3}{3!}+\cdots+(-1)^{n-1}\dfrac{x^{2n-1}}{(2n-1)!}+(-1)^n\dfrac{\cos\theta x}{(2n+1)!}x^{2n+1}$
3. $\cos x=1-\dfrac{x^2}{2!}+\cdots+(-1)^n\dfrac{x^{2n}}{(2n)!}+(-1)^{n+1}\dfrac{\cos\theta x}{(2n+2)!}x^{2n+2}$
4. $\ln(1+x)=x-\dfrac{x^2}{2}+\cdots+(-1)^{n-1}\dfrac{x^n}{n}+(-1)^n\dfrac{x^{n+1}}{(n+1)(1+\theta x)^{n+1}}$
5. $(1+x)^\alpha=1+\alpha x+\dfrac{\alpha(\alpha-1)}{2!}x^2+\cdots+\dfrac{\alpha(\alpha-1)\cdots(\alpha-n+1)}{n!}x^n+\dfrac{\alpha(\alpha-1)\cdots(\alpha-n+1)(\alpha-n)}{(n+1)!}(1+\theta x)^{\alpha-n-1}x^{n+1}$

## 积分
---
### 不定积分基本公式
|不定积分||不定积分|
|--|--|--|
|$\int0dx=C$||$\int x^2dx=\dfrac{1}{a+1}x^{a+1}+C(a\neq1)$
|$\int\dfrac{1}{x}dx=\ln\vert x\vert+C$||$\int a^xdx=\dfrac{a^x}{\ln a}+C(a>0,a\neq1)$|
|$\int\limits e^xdx=e^x+C$||$\int\sin xdx=-\cos x+C$|
|$\int\cos xdx=\sin x+C$||$\int\sec^2xdx=\tan x+C$|
|$\int\csc^2xdx=-\cot x+C$||$\int\sec x\tan xdx=\sec x+C$|
|$\int\csc x\cot xdx=-csc x+C$||$\int\dfrac{1}{\sqrt{1-x^2}}dx=\arcsin x+C$|
|$\int\dfrac{1}{1+x^2}dx=\arctan x+C$||$\int\dfrac{dx}{\sqrt{a^2-x^2}}=\arcsin\dfrac{x}{a}+C$|
|$\int\dfrac{dx}{a^2+x^2}=\dfrac{1}{a}\arctan\dfrac{x}{a}+C$||$\int\dfrac{dx}{x^2-a^2}=\dfrac{1}{2a}\ln\left\vert\dfrac{x-a}{x+a}\right\vert+C$|
|$\int\dfrac{dx}{\sqrt{x^2+a^2}}=\ln\left(x+\sqrt{x^2+a^2}\right)+C$||$\int\dfrac{dx}{\sqrt{x^2-a^2}}=\ln\left\vert x+\sqrt{x^2-a^2}\right\vert+C$|
|$\int\sec xdx=\ln\left\vert\sec x+\tan x\right\vert+C$||$\int\csc xdx=-\ln\left\vert\csc x+\cot x\right\vert+C$|


### 定积分
#### 定积分性质
##### 不等式性质
(1) 在区间$[a,b]$上$f(x)\leq g(x)$，则$\int_a^bf(x)dx\leq\int_a^bg(x)dx$
(2) 若$M$及$m$分别是$f(x)$在$[a,b]$上的最大值和最小值，则$$m(b-a)\leq\int_a^bf(x)dx\leq M(b-a)$$
(3) $\left\vert\int_a^bf(x)dx\right\vert\leq\int_a^b\left\vert f(x)\right\vert dx$

##### 中值定理
(1) 若$f(x)$在$[a,b]$上连续，则$$\int_a^bf(x)dx=f(\xi)(b-a)\quad \xi\in(a,b)$$称$\dfrac{1}{b-a}\int_a^bf(x)dx$为函数$y=f(x)$在区间$[a,b]$上的平均值；
(2) 若$f(x),g(x)$在$[a,b]$上连续，$g(x)$不变好，则$$\int_a^bf(x)g(x)dx=f(\xi)\int_a^bg(x)dx\quad  \xi\in[a,b]$$


#### 定积分公式
(1) 华理士公式（点火公式）
$$\int_0^{\frac{\pi}{2}}\sin^nxdx=\int_0^{\frac{\pi}{2}}\cos^nxdx=\begin{cases}\dfrac{n-1}{n}\dfrac{n-3}{n-2}\cdots\dfrac{1}{2}\dfrac{\pi}{2}, &n\text{为偶数}\\ \dfrac{n-1}{n}\dfrac{n-3}{n-2}\cdots\dfrac{2}{3},&n\text{为大于1的奇数}\end{cases}$$

(2) $\int_0^\pi xf(\sin x)dx=\dfrac{\pi}{2}\int_0^\pi f(\sin x)dx\quad(\text{其中}f(x)\text{连续})$
