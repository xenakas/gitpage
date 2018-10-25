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

$$ P(\theta, y) = P(\theta)P(y|\theta) $$
