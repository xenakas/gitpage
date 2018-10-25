---
layout: post
title: "Jeffreys prior"
excerpt_separator: "<!--more-->"
categories:
  - Econometrics
tags:
  - bayesian 
  - vocabulary 
---


<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

In Bayesian probability, the [Jeffreys prior](https://en.m.wikipedia.org/wiki/Jeffreys_prior) is a 
non-informative (objective) prior distribution for a parameter space; 
it is proportional to the square root of the determinant of the Fisher information matrix:

$$p\left({\vec{\theta }}\right) \propto {\sqrt{\det{\mathcal{I}}\left({\vec{\theta }}\right)}}$$

It has the key feature that its functional dependence on the likelihood L  is invariant under 
reparameterization of the parameter vector $$\vec{\theta }$$ 
(the functional form of the prior density function itself is not invariant under 
reparameterization, of course: only the measure that is identically zero has that property). 
This makes it of special interest for use with scale parameters.

<!--more-->

For an alternative parameterization $$\varphi$$   we can derive:
$$ p(\varphi )\propto {\sqrt {I(\varphi )} } $$ 
from
$$ p(\theta )\propto {\sqrt {I(\theta )}} $$  
using the change of variables theorem for transformations and the definition of Fisher information.


Use of the Jeffreys prior violates the strong version of the likelihood principle.
When using the Jeffreys prior, inferences about $$\vec{\theta }$$  depend not just
on the probability of the observed data as a function of $$\vec{\theta }$$, but also 
on the universe of all possible experimental outcomes, as determined by the experimental design, 
because the Fisher information is computed from an expectation over the chosen universe.
Accordingly, the Jeffreys prior, and hence the inferences made using it, 
may be different for two experiments involving the same $$\vec{\theta }$$  parameter even 
when the likelihood functions for the two experiments are the same — a violation of the strong likelihood principle.

