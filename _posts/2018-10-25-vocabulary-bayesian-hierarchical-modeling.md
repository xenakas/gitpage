---
title: "Bayesian hierarchical modeling"
layout: post
excerpt_separator: "<!--more-->"
tags:
  - bayesian
  - hierarchical
categories:
  - Vocabulary
---



[Bayesian hierarchical modelling](https://en.m.wikipedia.org/wiki/Bayesian_hierarchical_modeling) is a statistical model 
written in multiple levels that estimates the parameters of the posterior distribution using the Bayesian method.
The sub-models combine to form the hierarchical model, and Bayes' theorem is used to integrate them 
with the observed data and account for all the uncertainty that is present. 
The result of this integration is the posterior distribution, also known as the updated probability estimate, 
as additional evidence on the prior distribution is acquired.

<!--more-->

Frequentist statistics  may yield conclusions seemingly incompatible with those offered by Bayesian statistics 
due to the Bayesian treatment of the parameters as random variables and its use of subjective information 
in establishing assumptions on these parameters. 
As the approaches answer different questions the formal results aren't technically contradictory
but the two approaches disagree over which answer is relevant to particular applications. 
Bayesians argue that relevant information regarding decision making and updating beliefs 
cannot be ignored and that hierarchical modeling has the potential to overrule classical methods 
in applications where respondents give multiple observational data. 
Moreover, the model has proven to be robust, with the posterior distribution less sensitive 
to the more flexible hierarchical priors.

Hierarchical modeling is used when information is available on several different levels of observational units. 
The hierarchical form of analysis and organization helps in the understanding of multiparameter problems 
and also plays an important role in developing computational strategies.

### Bayes

Joint probability distribution for $$\theta_{j}$$  and $$y$$ can be rewritten as a product of the two 
distributions that are often referred to as the **prior distribution** $$P(\theta )$$  and 
the **sampling distribution** $$P(y\vert \theta )$$  respectively:

$$ P(\theta, y) = P(\theta)P(y\vert\theta) $$

So the posterior distribution will yield:

$$ P(\theta)P(y\vert\theta)  = \dfrac{P(y\vert\theta) P(\theta)}{P(y)} $$



**Exchangeability:**
$$P(y_{1}=1,y_{2}=0)=P(y_{1}=0,y_{2}=1)=\frac{1}{2}$$, then $$y_{1}$$  and $$y_{2}$$  are 
exchangeable.

But $$P(y_{2}=1\mid y_{1}=1) \neq P(y_{2}=1)$$, thus $$y_{1}$$  and $$y_{2}$$  are not independent.

If $$x_{1},\ldots ,x_{n}$$  are independent and identically distributed, then they are exchangeable, but the converse is not necessarily true.

### Hierarchical Models

**Hyperparameters** -  parameters of the prior distribution[^1]

[^1]: In machine learning, a hyperparameter is a parameter whose value is set before the learning process begins. By contrast, the values of other parameters are derived via training. For instance, LASSO is an algorithm that adds a regularization hyperparameter to ordinary least squares regression, which has to be set before estimating the parameters through the training algorithm.

**Hyperpriors** - distributions of Hyperparameters. In principle, one may iterate this, calling parameters of a hyperprior "hyperhyperparameters," and so forth.

The Bayesian hierarchical model contains the following stages:

- Stage I: $$y_{j}\mid \theta_{j},\phi \sim P(y_{j}\mid \theta_{j},\phi )$$ 
- Stage II: $$ \theta_{j}\mid \phi \sim P(\theta_{j}\mid \phi ) $$  
- Stage III: $$\phi \sim P(\phi )$$

The posterior distribution is proportional to:

$$  P(\phi ,\theta _{j}\mid y)\propto P(y_{j}\mid \theta _{j},\phi )P(\theta _{j},\phi ) = P(\phi ,\theta _{j}\mid y)\propto P(y_{j}\mid \theta _{j})P(\theta _{j}\mid \phi )P(\phi )$$









