---
layout: post
title: "kNN-Mode Seeking clustering Algorithm"
subtitle: "Demonstration of a new clustering algorithm named kNN-Mode seeking"
date: 2020-01-26 23:45:13 -0400
background: '/img/posts/10.jpg'
usemathjax: true
bibliography: references.bib  
---

## Clustering

**Clustering** is the task of dividing the population or data points into a number of groups such that data points in the same groups are more similar to other data points in the same group and dissimilar to the data points in other groups. It is basically a collection of objects on the basis of similarity and dissimilarity between them.

![[Pasted image 20220714121035.png]]

**Density-Based Methods** consider the clusters as the dense region having some similarities and differences from the lower dense region of the space. These methods have good accuracy and the ability to merge two clusters.
Density based clustering is one of the fundamental directions in unsupervised learning.

Myhre et al. (2017) introduces a new strategy to carry out mode based clustering, in this approach the traditional mean shift algorithm is replaced by a much faster *k* nearest neighbour (KNN) mode seeking method.


knitr::include_app("https://yihui.shinyapps.io/miniUI/",
  height = "600px")

in a paper by  our aim is to take mode based clustering further by proposing a different strategy. In our approach, traditional mean shift is replaced altogether by a much faster k-nearest neighbour (kNN) mode seeking method.

##### References

Nordhaug Myhre, J., Øyvind Mikalsen, K., Løkse, S. & Jenssen, R. (2018),  
‘Robust clustering using a knn mode seeking ensemble’, Pattern Recognition  
76, 491–505.  
URL: https://www.sciencedirect.com/science/article/pii/S0031320317304776  

