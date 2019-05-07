---
layout: post
title: "Brownian Bridge"
excerpt_separator: "<!--more-->"
categories:
  - Maths
tags:
  - stochastics
  - vocabulary 
---

<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>


### [Brownian Bridge:](http://www.randomservices.org/random/brown/Bridge.html)


In the most common formulation, the Brownian bridge process is obtained by taking a standard Brownian motion process $$X$$, restricted to the interval $$[0,1]$$, and conditioning on the event that $$X_1 = 0$$. Since  also $$X_0 =0$$, the process is tied down at both ends, and so the process in between forms a bridge. The Brownian bridge turns out to be an interesting stochastic process with surprising applications, including a very important application to statistics. In terms of a definition, however, we will give a list of characterizing properties as we did for standard Brownian motion and for Brownian motion with drift and scaling.

The expected value of the bridge is zero, with variance $$\frac{t(T-t)}{T}$$, implying
that the most uncertainty is in the middle of the bridge, with zero uncertainty at the nodes. 
The increments in a Brownian bridge are not independent.

A Brownian bridge is the result of Donsker's theorem (a functional extension of the CLT) in the area of empirical processes. It is also used in the Kolmogorov–Smirnov test in the area of statistical inference.


<!--more-->

A Brownian bridge is a stochastic process $$X = \{X_t:t\in[0,1]\}$$  with state space $$\mathbb{R}$$ that satisfies the following properties:
- $$X_0=0$$ and $$X_1=0$$  w.p.1
- $$X$$ is a Gaussian process.
- $$E(X_t)=0$$ for $$t\ in [0,1]$$.
- $$cov(X_s,X_t) = min\{s,t\}-st$$ for $$s,t\in [0,1]$$.
- w.p.1 $$t \to X_t$$  is continuous on $$[0,1]$$.

[__Properties:__](http://pluto.mscc.huji.ac.il/~mszucker/BIOSTAT/bm.pdf)

1. If $${B(t)}$$ is a BM and $$A$$ is any positive number, then $$\tilde{B}(t) = A^{1/2}B(t/A)$$ is also a
BM.
2. If $${B(t)}$$ is a BM, then $$\tilde{B}^◦(u) = B(u) − uB(1), u ∈ [0, 1]$$, is a BB.
3. If $$\{B^◦(u)\}$$ is a BB, then $$\tilde{B}(t) = (t + 1)B^◦
(t/(t + 1))$$ is a BM.
4. If $$\{B(t)\}$$ is a BM and $$T$$ is a fixed positive number, then $$\tilde{B}(t) = B(T + t) − B(T)$$
is also a BM. Also, $$\tilde{B}(t)$$ is independent of $$\{B(s), s ∈ [0, T]\}$$.

[__Application of Brownian bridge__:](https://dspace.mit.edu/bitstream/handle/1721.1/37302/18-175Spring-2005/NR/rdonlyres/1974B061-49AB-4653-9696-1F5CDB1B690D/0/lecture29.pdf)

1. Brownian bridge is the limit of the empirical distribution?
2. BB could reduce the simulation paths, this reduces computation effort, especially when the underlying factors are a lot (say 20-30).
3. BB could reduce the computation effort on path-dependent derivatives. For example, during pricing of a barrier option, a path could be simulated with monthly scenarios of the factors; then BB could be used to estimate the probability of the path "knock-out" of the barrier

[Donsker’s Theorem:](https://ocw.mit.edu/courses/mathematics/18-650-statistics-for-applications-fall-2016/lecture-slides/MIT18_650F16_Testing_GF.pdf)

If $$F$$ is continuous, then

$$\sqrt(n) \sup_{t\in R} |F_n(t) − F(t)| \to^{(d)}_{n\to\infty} \sup_{0\leq t\leq 1} |B(t)|$$ 

where $$B$$ is a Brownian bridge on $$[0, 1]$$.

