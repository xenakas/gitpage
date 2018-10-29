---
layout: post
title: "Estimation theory"
excerpt_separator: "<!--more-->"
categories:
  - Maths
tags:
  - estimation 
  - vocabulary 
  - mle
  - mape
  - regualrization
  - lasso
  - ridge
  - bayes 
  - mmse
---


<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>


Estimation theory is a branch of statistics that deals with estimating the 
values of parameters based on measured empirical data that has a random component. 
The parameters describe an underlying physical setting in such a way that their 
value affects the distribution of the measured data. An estimator attempts to approximate
the unknown parameters using the measurements. When the data consist of multiple variables 
and one is estimating the relationship between them, estimation is known as regression analysis.

In estimation theory, two approaches are generally considered:

- The probabilistic approach (described in this article) 
assumes that the measured data is random with probability distribution dependent 
on the parameters of interest
- The set-membership approach assumes that the measured data vector belongs to 
a set which depends on the parameter vector.

<!--more-->


## [Commonly used estimators (estimation methods):](http://people.ciirc.cvut.cz/~hlavac/TeachPresEn/55AutonomRobotics/2015-05-04ReinsteinBayes-ekf.pdf)

#### Maximum likelihood estimators

The method defines a maximum likelihood estimate:

$$ {\hat{\theta }} \in \{ { \operatorname {arg\,max}_{\theta \in \Theta } } {\mathcal {L}}(\theta \,;x)\}$$

if a maximum exists.



In practice, it is often convenient to work with the natural logarithm of 
the likelihood function, called the log-likelihood:

$$  \ell (\theta \,;x)=\ln {\mathcal {L}}(\theta \,;x)$$ 

A maximum likelihood estimator coincides with the most probable **Bayesian estimator** 
given a uniform prior distribution on the parameters. 
Indeed, the **maximum a posteriori estimate** is the parameter $$\theta$$ 
that maximizes the probability of $$\theta$$  given the data, given by Bayes' theorem:

$$  \operatorname {P} (\theta \mid x_{1},x_{2},\ldots ,x_{n})={\frac {f(x_{1},x_{2},\ldots ,x_{n}\mid \theta )\operatorname {P} (\theta )}{\operatorname {P} (x_{1},x_{2},\ldots ,x_{n})}}$$

where $$P(\theta )$$  is the prior distribution for the parameter $$\theta$$  and where
$$ \operatorname {P} (x_{1},x_{2},\ldots ,x_{n})$$  is the probability of the data 
averaged over all parameters. Since the denominator is independent of $$\theta$$, 
the Bayesian estimator is obtained by maximizing 
$$f(x_{1},x_{2},\ldots ,x_{n}\mid \theta )\operatorname {P} (\theta )$$  with respect to $$\theta$$ . 
If we further assume that the prior $$P(\theta )$$ is a **uniform distribution**, 
the Bayesian estimator is obtained by maximizing the likelihood function
$$ f(x_{1},x_{2},\ldots ,x_{n}\mid \theta )$$. 
Thus the **Bayesian estimator** coincides with the **maximum likelihood estimator**
for a **uniform prior distribution** $$\operatorname {P} (\theta)$$.



#### Bayes estimators

Bayes estimator   is an estimator or decision rule that minimizes the 
posterior expected value of a loss function (i.e., the posterior expected loss). 
Equivalently, it maximizes the posterior expectation of a utility function. 
An alternative way of formulating an estimator within Bayesian statistics 
is maximum a posteriori estimation

Suppose an unknown parameter $$\theta$$  is known to have a prior distribution $$ \pi $$. 
Let $$ \hat{\theta }(x) $$ be an estimator of $$\theta$$, and let 
$$ L(\theta ,{\widehat {\theta }})$$ be a loss function, 
such as squared error. 
The Bayes risk of $$ {\widehat {\theta }}$$  is defined as $$E_{\pi }(L(\theta ,{\widehat {\theta }}))$$ ,
where the expectation is taken over the probability distribution of $$\theta$$: 
this defines the risk function as a function of $${\widehat {\theta }}$$. 

An estimator $$ {\widehat {\theta }}$$  is said to be a **Bayes estimator** if 
it **minimizes the Bayes risk** among all estimators. 
Equivalently, the estimator which **minimizes the posterior expected loss** 
$$E(L(\theta ,{\widehat {\theta }})|x)$$  for each $$ x$$  also minimizes the Bayes risk 
and therefore is a Bayes estimator.

The most common **risk function** used for Bayesian estimation is the mean square error (MSE), 
also called squared error risk. 

$$ \mathrm {MSE} =E\left[({\widehat {\theta }}(x)-\theta )^{2}\right]$$

Using the MSE as risk, the Bayes estimate of the unknown parameter is simply 
the mean of the posterior distribution,

$$ {\widehat {\theta }}(x)=E[\theta |x]=\int \theta \,p(\theta |x)\,d\theta $$

This is known as the ** minimum mean square error (MMSE) ** estimator.


**Alternative risk functions:**

- A "linear" loss function

$$ L(\theta ,{\widehat {\theta }})=a|\theta -{\widehat {\theta }}| $$

$$  F({\widehat {\theta }}(x)|X)={\tfrac {1}{2}} $$

- The posterior mode, or a point close to it depending on the curvature and properties of 
the posterior distribution. 


####  Least squares

The least-squares method finds the optimal parameter values by minimizing the sum of squared residuals:

$$ S=\sum _{i=1}^{n}{r_{i}}^{2}.$$

When the observations come from an exponential family and mild conditions are satisfied, 
**least-squares estimates** and **maximum-likelihood estimates** are identical.
The method of least squares can also be derived as a **method of moments** estimator.

A special case of generalized least squares called **weighted least squares** 
occurs when all the off-diagonal entries of $$\Omega$$ 
(the correlation matrix of the residuals) are null; 
the variances of the observations (along the covariance matrix diagonal) 
may still be unequal (heteroscedasticity).

The first **principal component** about the mean of a set of points can 
be represented by that line which most closely approaches the data points 
(as measured by squared distance of closest approach, 
i.e. perpendicular to the line). In contrast, linear least squares tries to minimize
the distance in the $$y$$ direction only. 
Thus, although the two use a similar error metric, 
linear least squares is a method that treats one dimension of the data preferentially,
while PCA treats all dimensions equally.

##### Regularization

In mathematics, statistics, and computer science, particularly in the fields 
of machine learning and inverse problems, regularization is a process of introducing
additional information in order to solve an ill-posed problem or to prevent overfitting.

**Regularized least squares** is used for two main reasons. 
- The first comes up when the *number of variables in the linear system exceeds 
the number of observations.* In such settings, the ordinary least-squares problem 
is ill-posed and is therefore impossible to fit because the associated optimization 
problem has infinitely many solutions. RLS allows the introduction of further constraints 
that uniquely determine the solution.
- The second reason that RLS is used occurs when the number of variables 
does not exceed the number of observations, but the learned model suffers 
from poor generalization. RLS can be used in such cases to improve the generalizability 
of the model by constraining it at training time. This constraint can either force 
the solution to be "sparse" in some way or to reflect other prior knowledge about 
the problem such as information about correlations between features. A Bayesian understanding
of this can be reached by showing that *RLS methods are often equivalent to priors on the 
solution to the least-squares problem.*

**Tikhonov regularization**
(or ridge regression) adds a constraint that $$ \|\beta \|^{2}$$, the L2-norm of the parameter vector, 
is not greater than a given value. Equivalently, it may solve an unconstrained
minimization of the least-squares penalty with $$ \alpha \|\beta \|^{2}$$  added,
where $$\alpha $$  is a constant (this is the Lagrangian form of the constrained problem). 
In a **Bayesian context**, this is equivalent to placing a zero-mean normally 
distributed prior on the parameter vector.

**Lasso method**  (least absolute shrinkage and selection operator)  uses the constraint 
that $$ \|\beta \|^{2}$$, the L1-norm of the parameter vector, 
is no greater than a given value.  (As above, this is equivalent to an unconstrained 
minimization of the least-squares penalty with $$ \alpha  \|\beta  \|$$  added.) 
In a **Bayesian context**, this is equivalent to placing a zero-mean Laplace
prior distribution on the parameter vector.  
The optimization problem may be solved using quadratic programming or more general
convex optimization methods, as well as by specific algorithms such as the least angle 
regression algorithm.

One of the prime differences between Lasso and ridge regression is that in ridge regression, 
as the penalty is increased, all parameters are reduced while still remaining non-zero,
while in Lasso, increasing the penalty will cause more and more of the parameters 
to be driven to zero. This is an advantage of Lasso over ridge regression, 
as driving parameters to zero deselects the features from the regression.
Thus, Lasso automatically selects more relevant features and discards the others, 
whereas Ridge regression never fully discards any features.
Some feature selection techniques are developed based on the LASSO including **Bolasso** 
which bootstraps samples

#### Minimum variance unbiased estimator (MVUE)

In statistics a minimum-variance unbiased estimator (MVUE) unexpectedly is an unbiased estimator that 
has lower variance than any other unbiased estimator for all possible values of the parameter.

This has led to substantial development of statistical theory related to the problem of 
optimal estimation.

While combining the constraint of unbiasedness with the desirability metric of 
least variance leads to good results in most practical settings—making MVUE a natural 
starting point for a broad range of analyses—a targeted specification may perform 
better for a given problem; thus, MVUE is not always the best stopping point.

An unbiased estimator $$ \delta (X_{1},X_{2},\ldots ,X_{n})  $$ of  $$ g(\theta )$$  is UMVUE 
if $$ \forall \theta \in \Omega $$

$$ \operatorname {var} (\delta (X_{1},X_{2},\ldots ,X_{n}))\leq \operatorname {var} ({\tilde {\delta }}(X_{1},X_{2},\ldots ,X_{n}))$$

for any other unbiased estimator $$ {\tilde {\delta }}.$$


A Bayesian analog is a Bayes estimator, particularly with minimum mean square error (MMSE).



#### Minimum mean squared error (MMSE), also known as Bayes least squared error (BLSE)

In statistics and signal processing, a minimum mean square error (MMSE) estimator 
is an estimation method which minimizes the mean square error (MSE), which is a common 
measure of estimator quality, of the fitted values of a dependent variable. 
Linear MMSE estimators are a popular choice since they are easy to use, easy to calculate,
and very versatile. 
It has given rise to many popular estimators such as the **Wiener–Kolmogorov filter** and **Kalman filter.**


In the **Bayesian setting**, the term MMSE more specifically refers to estimation 
with quadratic loss function. 
In such case, the MMSE estimator is given by the posterior mean of the parameter 
to be estimated. 


For instance, we may have prior information about the range that the parameter can assume; 
or we may have an old estimate of the parameter that we want to modify when a new observation 
is made available; or the statistics of an actual random signal. 
This is in contrast to the non-Bayesian approach like **minimum-variance unbiased estimator** 
(MVUE) where absolutely nothing is assumed to be known about the parameter in advance 
and which does not account for such situations. 

Thus unlike non-Bayesian approach where parameters of interest are assumed to be deterministic, 
but unknown constants, the Bayesian estimator seeks to estimate a parameter that is itself a 
random variable. Furthermore, Bayesian estimation can also deal with situations where 
the sequence of observations are not necessarily independent. 
Thus Bayesian estimation provides yet another alternative to the MVUE. 
This is useful when the MVUE does not exist or cannot be found.

Let $$ x$$   be  hidden random vector variable, and let $$ y$$  be a 
known random vector variable (the measurement or observation),
both of them not necessarily of the same dimension. 
An estimator $${\hat {x}}(y)$$  of $$x$$ is any function of the measurement $$ y$$ .
The estimation error vector is given by $$ e={\hat {x}}-x$$  and its mean squared error 
(MSE) is given by the trace of error covariance matrix

$$ \operatorname {MSE} = \operatorname {tr} \left\{\operatorname {E} \{({\hat {x}}-x)({\hat {x}}-x)^{T}\}\right\} $$ 



When $$ x$$  is a scalar variable, the MSE expression simplifies to 
$$ \operatorname {E} \left\{({\hat {x}}-x)^{2}\right\} $$.

Note that MSE can equivalently be defined in other ways, since

$$  \operatorname {tr} \left\{\operatorname {E} \{ee^{T}\}\right\}=\operatorname {E} \left\{\operatorname {tr} \{ee^{T}\}\right\}=$$

$$ =\operatorname {E} \{e^{T}e\}=\sum _{i=1}^{n}\operatorname {E} \{e_{i}^{2}\}.$$

The MMSE estimator is then defined as the estimator achieving minimal MSE:

$$ {\hat {x}}_{\operatorname {MMSE} }(y)=\operatorname {argmin} _{\hat {x}}\operatorname {MSE} $$

In many cases, it is not possible to determine the analytical expression of the MMSE estimator. 
Two basic numerical approaches to obtain the MMSE estimate depends on either 
finding the conditional expectation $$ \operatorname {E} \{x\mid y\}$$  or finding 
the minima of MSE
- Direct numerical evaluation of the conditional expectation 
is computationally expensive since it often requires multidimensional integration 
usually done via Monte Carlo methods. 
- Another computational approach is to directly seek the minima of the MSE
using techniques such as the gradient descent methods; but this method still 
requires the evaluation of expectation. 


**Sequential linear MMSE estimation**

In many real-time application, observational data is not available in a single batch. 
Instead the observations are made in a sequence. A naive application of previous formulas 
would have us discard an old estimate and recompute a new estimate as fresh data is made available. 
But then we lose all information provided by the old observation. 
- When the observations are scalar quantities, one possible way of avoiding such re-computation 
is to first concatenate the entire sequence of observations and then apply the standard estimation 
formula. But this can be very tedious because as the number of 
observation increases so does the size of the matrices that need to be inverted and multiplied grow. 
- Another approach to estimation from sequential observations is to simply update
an old estimate as additional data becomes available, leading to finer estimates.

Thus a recursive method is desired where the new measurements can modify the old estimates. 
Implicit in these discussions is the assumption that the statistical properties 
of $$x$$  does not change with time (it is **stationary**).


For [sequential estimation](https://en.wikipedia.org/wiki/Minimum_mean_square_error#Sequential_linear_MMSE_estimation), if we have an estimate $$ {\hat {x}}_{1}$$  based on 
measurements generating space $$ Y_{1}$$, then after receiving another set 
of measurements, we should subtract out from these measurements that part
that could be anticipated from the result of the first measurements.
In other words, the updating must be based on that part of the new data which is 
orthogonal to the old data.


The repeated use of  equations of new estimate $$ {\hat {x}}_{t} $$ and  new error covariance 
$$ C_{e_{t+1}}$$   as more observations become available lead to recursive estimation techniques.

1. $$  K_{t+1}=C_{e_{t}}A^{T}(AC_{e_{t}}A^{T}+C_{Z})^{-1} $$
2. $$ {\hat {x}}_{t+1}={\hat {x}}_{t}+K_{t+1}(y-A{\hat {x}}_{t}) $$
3. $$  C_{e_{t+1}}=(I-K_{t+1}A)C_{e_{t}} $$ 

The matrix $$ K$$  is often referred to as the gain factor. 
The repetition of these three steps as more data becomes available leads to an 
iterative estimation algorithm. The generalization of this idea to non-stationary cases
gives rise to the **Kalman filter**.



#### Maximum a posteriori (MAP)

In Bayesian statistics, a maximum a posteriori probability (MAP) estimate is an estimate 
of an unknown quantity, that equals the **mode of the posterior distribution**. 
The MAP can be used to obtain a point estimate of an unobserved quantity on the basis 
of empirical data. It is [closely related to the method of maximum likelihood (ML) estimation](http://www.mi.fu-berlin.de/wiki/pub/ABI/Genomics12/MLvsMAP.pdf), 
but employs an augmented optimization objective which incorporates a prior 
distribution (that quantifies the additional information available through prior knowledge of
a related event) over the quantity one wants to estimate. 
MAP estimation can therefore be seen as a **regularization of ML estimation**



$$
\theta_{MLE} &= \mathop{\rm arg\,max}\limits_{\theta} P(X \vert \theta) \\[10pt]
             &= \mathop{\rm arg\,max}\limits_{\theta} \prod_i P(x_i \vert \theta)

$$

If we replace the likelihood in the MLE formula above with the posterior, we get:


$$
\theta_{MAP} &= \mathop{\rm arg\,max}\limits_{\theta} P(X \vert \theta) P(\theta) \\[10pt]
             &= \mathop{\rm arg\,max}\limits_{\theta} \log P(X \vert \theta) P(\theta) \\[10pt]
             &= \mathop{\rm arg\,max}\limits_{\theta} \log \prod_i P(x_i \vert \theta) P(\theta) \\[10pt]
             &= \mathop{\rm arg\,max}\limits_{\theta} \sum_i \log P(x_i \vert \theta) P(\theta)

$$



Also  [we could conclude that  MLE is a special case of MAP, where the prior is uniform](https://wiseodd.github.io/techblog/2017/01/01/mle-vs-map/). 
Just like **Bayesian estimator** coincides with the **maximum likelihood estimator**
for a **uniform prior distribution** $$\operatorname {P} (\theta)$$ (see above).


MAP estimates can be computed in several ways:

- Analytically, when the mode(s) of the posterior distribution can be given in closed form. 
- Via numerical optimization such as the conjugate gradient method or Newton's method.
This usually requires first or second derivatives, which have to be evaluated 
analytically or numerically.
- Via a modification of an expectation-maximization algorithm. 
This does not require derivatives of the posterior density.
- Via a Monte Carlo method using simulated annealing

**Criticism**

- MAP estimation  is not very representative 
of Bayesian methods in general. This is because MAP estimates are point estimates,
whereas Bayesian methods are characterized by the use of distributions 
to summarize data and draw inferences: thus, Bayesian methods tend to report 
the posterior mean or median instead, together with credible intervals. 
This is both because these estimators are optimal under squared-error 
and linear-error loss respectively - which are more representative of
typical loss functions - and because the posterior distribution may not
have a simple analytic form: in this case, the distribution can be simulated 
using Markov chain Monte Carlo techniques, while optimization to find its
mode(s) may be difficult or impossible.


- In many types of models, such as mixture models, the posterior may be multi-modal.
In such a case, the usual recommendation is that one should choose the highest mode: 
this is not always feasible (global optimization is a difficult problem),
nor in some cases even possible (such as when identifiability issues arise). 
Furthermore, the highest mode may be uncharacteristic of the majority of the posterior.

- Finally, unlike ML estimators, the MAP estimate is not invariant under 
reparameterization. Switching from one parameterization to another 
involves introducing a Jacobian that impacts on the location of the maximum.
