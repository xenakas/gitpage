---
layout: post
title: "Shrinkage"
excerpt_separator: "<!--more-->"
categories:
  - Maths
tags:
  - shrinkage 
  - vocabulary 
  - bayes
---


<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

In statistics, [shrinkage](https://en.wikipedia.org/wiki/Shrinkage_(statistics)) has two meanings, though a common idea underlying both of these meanings is
the reduction in the effects of sampling variation:

- in regression analysis, a fitted relationship 
appears to perform less well on a new data set than on the data set used for fitting.
In particular the value of the coefficient of determination 'shrinks'. 
This idea is complementary to overfitting

- to describe general types of estimators, or the effects of some types of estimation, 
whereby a naive or raw estimate is improved by combining it with other information 
(see shrinkage estimator). 


<!--more-->



[Shrinking data can result in:]((https://www.statisticshowto.datasciencecentral.com/shrinkage-estimator/))
- Better, more stable, estimates for true population parameters,
- Reduced sampling and non-sampling errors,
- Smoothed spatial fluctuations.

However, the method has many disadvantages, including:

- Serious errors if the population has an atypical mean. 
- Shrunk estimators can become biased estimators, tending to underestimate the true parameters.
- Shrunk fitted models can perform more poorly on new data sets compared to the original data
set used for fitting. Specifically, r-squared “shrinks.”





A [shrinkage estimator](https://en.wikipedia.org/wiki/Shrinkage_estimator)  is an estimator that, 
either explicitly or implicitly, incorporates the effects of shrinkage. 
In loose terms this means that a naive or raw estimate is improved by combining
it with other information. The term relates to the notion that the improved estimate 
is made closer to the value supplied by the 'other information' than the raw estimate. 
In this sense, shrinkage is used to regularize ill-posed inference problems.


A shrinkage estimator is a new estimate produced by shrinking a raw estimate (like the sample mean). 
For example, two extreme mean values can be combined to make one more centralized mean value; 
repeating this for all means in a sample will result in a revised sample mean 
that has “shrunk” towards the true population mean. 

Shrinkage estimators:

- Lasso estimator (used in lasso regression),
- Ridge estimator: used in ridge regression to improve the least-squares estimate when multicollinearity is present,
- Stein-type estimators, including the “original” James-Stein estimator.





Shrinkage is implicit in Bayesian inference and penalized likelihood inference, 
and explicit in James–Stein-type inference. In contrast, simple types of maximum-likelihood 
and least-squares estimation procedures do not include shrinkage effects, 
although they can be used within shrinkage estimation schemes.






Hausser and Strimmer "develop a James-Stein-type shrinkage estimator, 
resulting in a procedure that is highly efficient statistically as well as computationally. 
It outperforms  other entropy estimation procedures across a diverse range of 
sampling scenarios and data-generating models, even in cases of severe undersampling. 
The proposed shrinkage estimators of entropy and mutual information, as well as all 
other investigated entropy estimators, have been implemented in R package ``entropy`` 






