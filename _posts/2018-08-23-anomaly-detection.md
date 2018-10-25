---
layout: post
title: Anomaly Detection 
excerpt_separator: "<!--more-->"
categories:
  - Econometrics
tags:
  - anomalies
  - R
---

Anomaly Detection with the Normal Distribution, with the Poisson Distribution, with Delta Time method


<!--more-->

### [Anomaly Detection with the Normal Distribution](https://anomaly.io/anomaly-detection-normal-distribution)

- 68% of all values fall between $$\[mean-\sigma, mean+\sigma\]$$
- 95% of all values fall between $$\[mean-2*\sigma, mean+2*\sigma\]$$
- 99,7% of all values fall between $$\[mean-3*\sigma, mean+3*\sigma\]$$

The last 3 rules are also known as the [68–95–99.7 rule](https://en.m.wikipedia.org/wiki/68–95–99.7_rule) or the “three-sigma rule of thumb”.

Detecting a Change in the Normal Distribution

To detect this kind of anomaly we use a “window” containing the n most recent elements

When the standard deviation or the mean change, something unusual is happening. To detect such changes, for each upcoming point “p” we create of window from “p” to “p-100″. Then, we calculate the standard deviation and mean of this window. If it changes too much, an anomaly has been detected.


### [Anomaly Detection with the Poisson Distribution](https://anomaly.io/anomaly-detection-poisson-distribution/)

Focus on Time Per Event: After the aggregation process is finished, the accumulator reveals the final count of events during the fixed period. Comparing this number to our model (or prediction) will tell us if the value is anomalous.

### [Delta Time (Δt) for Anomaly Detection](https://anomaly.io/anomaly-detection-delta-time/)

The alternative is to change the problem to studying the period of time between events.

### [Anomaly Detection with Twitter in R](https://anomaly.io/anomaly-detection-twitter-r/)

R-script [here](https://github.com/martin-magakian/Anomaly-Detection-test)










