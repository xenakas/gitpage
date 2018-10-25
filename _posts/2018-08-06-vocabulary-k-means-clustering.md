---
title: "K-means Clustering"
layout: post
excerpt_separator: "<!--more-->"
categories:
  - ML
tags:
  - ml
  - clustering
  - vocabulary
---

[k-means clustering](https://en.wikipedia.org/wiki/K-means_clustering) is a method of vector quantization that is popular for cluster analysis in data mining. k-means clustering aims to partition n observations into k clusters in which each observation belongs to the cluster with the nearest mean, serving as a prototype of the cluster. 

<!--more-->

The problem is computationally difficult (NP-hard); however, there are efficient heuristic 
algorithms that are commonly employed and converge quickly to a local optimum. 
These are usually similar to the expectation-maximization algorithm for mixtures of 
Gaussian distributions via an iterative refinement approach employed by both k-means
and Gaussian mixture modeling. 

The algorithm has a loose relationship to the **k-nearest neighbor classifier**, 
a popular machine learning technique for classification that is often confused with k-means due to the 
k in the name. One can apply the 1-nearest neighbor classifier on the cluster centers 
obtained by k-means to classify new data into the existing clusters. 
This is known as nearest centroid classifier or Rocchio algorithm.

[K-means algorithm](http://www.onmyphd.com/?p=k-means.clustering)

1. Initialize the center of the clusters
2. Attribute the closest cluster to each data point	
3. Set the position of each cluster to the mean of all data points belonging to that cluster
4. Repeat steps 2-3 until convergence

The algorithm eventually converges to a point, although it is not necessarily the minimum of the sum of squares. 

That is because the problem is non-convex and the algorithm is just a heuristic, converging to a local minimum. The algorithm stops when the assignments do not change from one iteration to the next.
