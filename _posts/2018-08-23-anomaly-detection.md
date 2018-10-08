---
layout: post
title: Anomaly Detection
tags:
  - anomalies
  - data science
  - JS
  - R
---


### Anomaly Detection with the Normal Distribution

- 68% of all values fall between [mean-σ, mean+σ]
- 95% of all values fall between [mean-2*σ, mean+2*σ]
- 99,7% of all values fall between [mean-3*σ, mean+3*σ]

The last 3 rules are also known as the 68–95–99.7 rule or the “three-sigma rule of thumb”.

https://en.m.wikipedia.org/wiki/68–95–99.7_rule

Detecting a Change in the Normal Distribution

To detect this kind of anomaly we use a “window” containing the n most recent elements

When the standard deviation or the mean change, something unusual is happening. To detect such changes, for each upcoming point “p” we create of window from “p” to “p-100″. Then, we calculate the standard deviation and mean of this window. If it changes too much, an anomaly has been detected.

#R_script

https://anomaly.io/anomaly-detection-normal-distribution/




Anomaly Detection with the Poisson Distribution

#JS_script

https://anomaly.io/anomaly-detection-poisson-distribution/

Focus on Time Per Event: After the aggregation process is finished, the accumulator reveals the final count of events during the fixed period. Comparing this number to our model (or prediction) will tell us if the value is anomalous.




Delta Time (Δt) for Anomaly Detection

The alternative is to change the problem to studying the period of time between events.

https://anomaly.io/anomaly-detection-delta-time/




Anomaly Detection with Twitter in R

https://github.com/martin-magakian/Anomaly-Detection-test

https://anomaly.io/anomaly-detection-twitter-r/









