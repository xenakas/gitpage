---
layout: post
categories:
  - Vocabulary
title: K-means Clustering
tags:
  - ml
  - clustering
  - vocabulary
---

http://www.onmyphd.com/?p=k-means.clustering

K-means algorithm

1. Initialize the center of the clusters
2. Attribute the closest cluster to each data point	
3. Set the position of each cluster to the mean of all data points belonging to that cluster
4. Repeat steps 2-3 until convergence

The algorithm eventually converges to a point, although it is not necessarily the minimum of the sum of squares. 

That is because the problem is non-convex and the algorithm is just a heuristic, converging to a local minimum. The algorithm stops when the assignments do not change from one iteration to the next.

