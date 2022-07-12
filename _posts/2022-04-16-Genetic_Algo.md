---
layout: post
title: "Portfolio Optimization with Genetic Algorithm "
subtitle: "A demonstration of genetic alogoritms used in portfolio optimization"
date: 2020-01-26 23:45:13 -0400
background: '/img/posts/10.jpg'
usemathjax: true
---

## Portfolio Optimisation in R using a Genetic Algorithm

Portfolio optimisation is one of the most interesting fields of study in financial mathematics. Many scientists have studied a lot of analytical and numerical methods to build the best investment portfolio according to a defined set of assets.

In this article, I’ll show a method to optimize a portfolio by using a numerical technique based on genetic algorithms. The power of genetic algorithms makes it possible to find the optimal portfolio even when the objective function isn’t smooth or differentiable.

### Portfolio Composition

Given we have *N* financial asset we want to invest in. These can be made up of bonds, ETFs, diversified funds and stock. Each being made up of **historical returns**  that are the price relative difference from on period to another. 

The **return** of the *i* -th asset between period *t* and period *t-1* is defined as:

$$
p_{i}(t) = \frac{\text{Price}_{i}(t)-\text{Price}_{i}(t-1)}{\text{Price}_{i}(t-1)}
$$


 