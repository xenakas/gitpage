---
title: "BFGS"
excerpt_separator: "<!--more-->"
layout: post
categories:
  - Vocabulary
tags:
  - approximation
  - bfgs
  - vocabulary
---


In numerical optimization, the [Broyden–Fletcher–Goldfarb–Shanno](https://en.m.wikipedia.org/wiki/Broyden–Fletcher–Goldfarb–Shanno_algorithm) (BFGS) algorithm is an iterative method for solving unconstrained nonlinear optimization problems.[1]

<!--more-->

The BFGS method belongs to quasi-Newton methods, a class of hill-climbing optimization techniques that seek a stationary point of a (preferably twice continuously differentiable) function. For such problems, a necessary condition for optimality is that the gradient be zero. Newton's method and the BFGS methods are not guaranteed to converge unless the function has a quadratic Taylor expansion near an optimum. However, BFGS has proven to have good performance even for non-smooth optimizations.[2]

In quasi-Newton methods, the Hessian matrix of second derivatives is not computed. Instead, the Hessian matrix is approximated using updates specified by gradient evaluations (or approximate gradient evaluations). Quasi-Newton methods are generalizations of the secant method to find the root of the first derivative for multidimensional problems. In multi-dimensional problems, the secant equation does not specify a unique solution, and quasi-Newton methods differ in how they constrain the solution. The BFGS method is one of the most popular members of this class.[3] Also in common use is L-BFGS, which is a limited-memory version of BFGS that is particularly suited to problems with very large numbers of variables (e.g., >1000). The BFGS-B[4] variant handles simple box constraints.


In SciPy, the [scipy.optimize.fmin_bfgs](https://docs.scipy.org/doc/scipy/reference/generated/scipy.optimize.fmin_bfgs.html#scipy.optimize.fmin_bfgs) function implements BFGS. It is also possible to run BFGS using any of the L-BFGS algorithms by setting the parameter L to a very large number.


In R, the BFGS algorithm (and the L-BFGS-B version that allows box constraints) is implemented as an option of the base function [optim()](https://stat.ethz.ch/R-manual/R-devel/library/stats/html/optim.html).

#L-BFGS

[Limited-memory BFGS](https://en.m.wikipedia.org/wiki/Limited-memory_BFGS) (L-BFGS or LM-BFGS) is an optimization algorithm in the family of quasi-Newton methods that approximates the Broyden–Fletcher–Goldfarb–Shanno (BFGS) algorithm using a limited amount of computer memory. It is a popular algorithm for parameter estimation in machine learning.

The algorithm's target problem is to minimise f(x) over unconstrained values of the real-vector x where f is a differentiable scalar function.

Like the original BFGS, L-BFGS uses an estimation to the inverse Hessian matrix to steer its search through variable space, but where BFGS stores a dense n×n approximation to the inverse Hessian (n being the number of variables in the problem), L-BFGS stores only a few vectors that represent the approximation implicitly. Due to its resulting linear memory requirement, the L-BFGS method is particularly well suited for optimization problems with a large number of variables. Instead of the inverse Hessian Hk, L-BFGS maintains a history of the past m updates of the position x and gradient ∇f(x), where generally the history size m can be small (often m<10). These updates are used to implicitly do operations requiring the Hk-vector product.


