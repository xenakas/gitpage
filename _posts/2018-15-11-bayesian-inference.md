---
title: "Bayesian inference"
layout: post
excerpt_separator: "<!--more-->"
tags:
  - bayesian
  - vocabulary
categories:
  - Econometrics
---

<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

[Bayesian inference](https://en.m.wikipedia.org/wiki/Bayesian_inference) is a method of statistical 
inference in which Bayes' theorem is used to update the probability for an hypothesis as
more evidence or information becomes available. 
Bayesian updating is particularly important in the dynamic analysis of a sequence of data. 

Many Bayesian methods required a lot of computation to complete, 
and most methods that were widely used during the century were based on 
the frequentist interpretation. However, with the advent of powerful computers 
and new algorithms like Markov chain Monte Carlo, Bayesian methods have seen increasing 
use within statistics coming into the 21st century.

<!--more-->

### Bayes' theorem:

$$ P(A \vert B)  = \dfrac{P(B \vert A) P(A)}{P(B)} $$

Specific interpretation in Bayesian statistics: $$A$$ usually represents a proposition 
and $$B$$  represents the evidence, or new data that is to be taken into account. 
$$P(A)$$ is the prior probability of $$A$$   which expresses one's beliefs about $$A$$  before 
evidence is taken into account. $$P(B\mid A)$$  is the likelihood function, 
which can be interpreted as the probability of the evidence $$B$$ given that $$A$$  is true. 
The likelihood quantifies the extent to which the evidence $$B$$  supports the proposition 
$$A$$. $$P(A\mid B)$$  is the posterior probability, 
the probability of the proposition $$A$$  after taking the evidence 
$$B$$  into account. 

The probability of the evidence $$P(B)$$  can be calculated using the law of total probability. 

$$P(B)=\sum_{i}P(B\mid A_{i})P(A_{i})$$ 

When there are an infinite number of outcomes, it is necessary to integrate over all outcomes 
to calculate $$P(B)$$ using the law of total probability. 
Often, it  is difficult to calculate, so often only the product of the prior and likelihood 
is considered, since the evidence does not change in the same analysis. 
The posterior is proportional to this product:

$$P(A\mid B)\propto P(B\mid A)P(A)$$

The **maximum a posteriori**, which is the mode of the posterior and is often computed 
in Bayesian statistics using mathematical optimization methods, remains the same. 
The posterior can be approximated even without computing the exact value of $$P(B)$$ 
with methods such as **Markov chain Monte Carlo** or **variational Bayesian methods**.

### Bayesian inference

Data point's distribution - $$\displaystyle x\sim p(x\mid \theta )$$ 

**The prior distribution** is the distribution of the parameter(s) before any data is observed, 
i.e. $$ \theta \sim p(\theta \mid \alpha )$$, where  $$\alpha$$ is  the hyperparameter. 
The prior distribution might not be easily determined. 
In this case, we can use the [Jeffreys prior](https://en.m.wikipedia.org/wiki/Jeffreys_prior) to 
obtain the posterior distribution before updating them with newer observations.

**The sampling distribution** is the distribution of the observed data conditional on its parameters, 
i.e. $$p(\mathbf {X} \mid \theta )$$, where  $$\mathbf {X}$$  is the sample. 
This is also termed the likelihood, especially when viewed as a function of the parameter(s), 
sometimes written $$ \operatorname{L} (\theta \mid \mathbf {X} )=p(\mathbf {X} \mid \theta )$$ 

**The marginal likelihood** (sometimes also termed the evidence) is the distribution 
of the observed data marginalized over the parameter(s), 
i.e. $$p(\mathbf {X} \mid \alpha )=\int p(\mathbf {X} \mid \theta )p(\theta \mid \alpha ) d\theta $$ 

**The posterior distribution** is the distribution of the parameter(s) after taking into account 
the observed data. This is determined by Bayes' rule, which forms the heart of Bayesian inference:
$$  p(\theta \mid \mathbf {X},\alpha )={\frac {p(\mathbf {X} \mid \theta )p(\theta \mid \alpha )}{p(\mathbf {X} \mid \alpha )}} $$ 

The posterior **predictive** distribution is the distribution of a new data point $$ \tilde{x} $$ , 
marginalized over the posterior:
$$  p({\tilde {x}}\mid \mathbf {X} ,\alpha )=\int p({\tilde {x}}\mid \theta )p(\theta \mid \mathbf {X} ,\alpha ) d \theta  $$

The prior **predictive** distribution is the distribution of a new data point, 
marginalized over the prior:
$$ p({\tilde {x}}\mid \alpha )=\int p({\tilde {x}}\mid \theta )p(\theta \mid \alpha ) d\theta $$ 


