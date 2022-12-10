---
layout: post
title: "kNN-Mode Seeking clustering Algorithm"
subtitle: "Demonstration of a new clustering algorithm named kNN-Mode seeking (Work in progress) "
date: 2020-01-26 23:45:13 -0400
background: '/img/posts/10.jpg'
usemathjax: true
bibliography: references.bib  
---

## Clustering

**Clustering** is the task of dividing the population or data points into a number of groups such that data points in the same groups are more similar to other data points in the same group and dissimilar to the data points in other groups. It is basically a collection of objects on the basis of similarity and dissimilarity between them.


![Cluster](/img/posts/cluster.jpeg){:width="100%"}


**Density-Based Methods** consider the clusters as the dense region having some similarities and differences from the lower dense region of the space. These methods have good accuracy and the ability to merge two clusters.
Density based clustering is one of the fundamental directions in unsupervised learning.

Myhre et al. (2017) introduces a new strategy to carry out mode based clustering, in this approach the traditional mean shift algorithm is replaced by a much faster *k* nearest neighbour (KNN) mode seeking method.
The algorithm is based on the same principles as mean shift, namely following the local gradient ascent of each point and using the mode.

### KNN mode seeking algorithm
Given a kNN-density estimate, where the density at a point $$\textbf{x}$$ is the reciprocal of the squared distance to the k-th nearest neighbour $$\textbf{x}_k$$:

$$
\hat{f}_{kNN} (\textbf{x}) = \frac{1}{|| \textbf{x}-\textbf{x}_k||^2}
$$

[Interactive Plot Demonstration](https://lrv2nt-kgosi.shinyapps.io/KNN_Mode_Seeking/)


##### References

Nordhaug Myhre, J., Øyvind Mikalsen, K., Løkse, S. & Jenssen, R. (2018),  
‘Robust clustering using a knn mode seeking ensemble’, Pattern Recognition  
76, 491–505.  
URL: https://www.sciencedirect.com/science/article/pii/S0031320317304776  

