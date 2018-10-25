---
layout: post
title: "Fisher informationr"
excerpt_separator: "<!--more-->"
categories:
  - Econometrics
tags:
  - vocabulary 
  - bayesian
---


<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>


In mathematical statistics, the Fisher information 
is a way of measuring the amount of information that an observable random variable X carries 
about an unknown parameter θ of a distribution that models X. 
Formally, it is the variance of the score, or the expected value of the observed information.

In **Bayesian statistics**, the Asymptotic distribution of the posterior mode depends on the Fisher
information and not on the prior (according to the Bernstein–von Mises theorem, 
which was anticipated by Laplace for exponential families).
The Fisher information is also used in the calculation of the **Jeffreys prior**, 
which is used in Bayesian statistics.

The Fisher-information matrix is used to calculate the covariance matrices associated 
with maximum-likelihood estimates. It can also be used in the formulation of test statistics, 
such as the **Wald test**.

<!--more-->

The Fisher information is a way of measuring the amount of information that an observable 
random variable X carries about an unknown parameter θ upon which the probability of X depends. 

Let $$f(X; \theta)$$ be the probability density function for X conditional on the value of θ. 
This is also the likelihood function for θ. It describes the probability that we observe 
a given sample X, given a known value of θ. 

**Intuition:**  If f is sharply peaked with respect to changes in θ, it is easy to indicate the “correct” 
value of θ from the data, or equivalently, that the data X provides a lot of information 
about the parameter θ. If the likelihood f is flat and spread-out, then it would take many, 
many samples like X to estimate the actual “true” value of θ that would be obtained 
using the entire population being sampled. This suggests studying some kind of 
variance with respect to θ.

Formally, the partial derivative with respect to θ of the natural logarithm
of the likelihood function is called the “score”. 
Under certain regularity conditions, if θ is the *true parameter*, it can be shown that 
the expected value (the first moment) of the score is 0:

$$E \left[ {\frac{\partial}{\partial \theta }} \log f(X;\theta) \vert |\theta \right] = \int {\frac{ {\frac{\partial }{\partial \theta} } f(x;\theta )}{f(x;\theta )} }f(x;\theta ) dx = $$

$$ = {\frac {\partial }{\partial \theta }}\int f(x;\theta ) dx  = {\frac {\partial }{\partial \theta }}1 = 0 $$  

The variance (which equals the second central moment) is defined to be the Fisher information:

$$ \mathcal {I} (\theta )= E \left[ \left( {\frac{\partial }{\partial \theta }} \log f(X;\theta )\right)^{2} \vert \theta \right] = $$

$$ = \int \left({\frac {\partial }{\partial \theta }}\log f(x;\theta )\right)^{2} f(x;\theta ) dx $$ 

If $$log f(x; \theta)$$  is twice differentiable with respect to θ,
and under certain regularity conditions, then the Fisher information may 
be seen as the curvature of the support curve (the graph of the log-likelihood). 

Near the maximum likelihood estimate, low Fisher information therefore indicates that 
the maximum appears "blunt", that is, the maximum is shallow and there are many 
nearby values with a similar log-likelihood. Conversely, 
high Fisher information indicates that the maximum is sharp.


