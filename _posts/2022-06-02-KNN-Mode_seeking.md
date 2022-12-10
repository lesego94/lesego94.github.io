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

Mean shift, mode seeking, and clustering are all techniques that can be used for data analysis and exploration. However, they are distinct methods that differ in their underlying assumptions and principles.

Mean shift is a non-parametric algorithm that is commonly used for density estimation and clustering. It is based on the idea of estimating the density of the data at each point, and then shifting each point in the direction of the maximum density until it reaches a "mode", or local peak, in the data distribution. The resulting modes can then be used as cluster centers or to estimate the underlying density of the data.

Mode seeking, on the other hand, is a method for finding the modes or local maxima in a data distribution. This can be useful for identifying clusters or groups of similar data points, or for identifying outliers or anomalies in the data. Mode seeking algorithms typically use a gradient-based optimization method to iteratively move each data point in the direction of the maximum gradient until it reaches a mode.

Clustering, on the other hand, is a broader category of techniques that can be used to group data points into clusters or groups based on their similarity or distance. There are many different types of clustering algorithms, including K-means, hierarchical clustering, and density-based clustering, each of which has its own unique characteristics and assumptions. Clustering algorithms can be used for a wide range of applications, including data exploration, classification, and anomaly detection.

In conclusion, mean shift, mode seeking, and clustering are all methods that can be used for data analysis and exploration. Mean shift and mode seeking are specific algorithms for density estimation and mode finding, respectively, while clustering is a broader category of algorithms that can be used for grouping data points into clusters.

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

