---
layout: post
title: "Portfolio Optimization with Genetic Algorithm "
subtitle: "A demonstration of genetic alogoritms used in portfolio optimization"
date: 2020-01-26 23:45:13 -0400
background: '/img/posts/10.jpg'
usemathjax: true
---

## Portfolio Optimisation Using a Genetic Algorithm

Portfolio optimisation is one of the most interesting fields of study in financial mathematics. Many scientists have studied a lot of analytical and numerical methods to build the best investment portfolio according to a defined set of assets.

In this article, I’ll show a method to optimize a portfolio by using a numerical technique based on genetic algorithms. The power of genetic algorithms makes it possible to find the optimal portfolio even when the objective function isn’t smooth or differentiable.

### Portfolio Composition

Given we have *N* financial asset we want to invest in. These can be made up of bonds, ETFs, diversified funds and stock. Each being made up of **historical returns**  that are the price relative difference from on period to another. 

The **return** of the *i* -th asset between period *t* and period *t-1* is defined as:

$$
p_{i}(t) = \frac{\text{Price}_{i}(t)-\text{Price}_{i}(t-1)}{\text{Price}_{i}(t-1)}
$$

With this the weighted portfolio return at a time *t* is then:

$$
P(t)= \displaystyle\sum\limits_{i=1}^{N}x_{i}\cdot p_i(t)
$$

 The weighted return is given as a fraction of the capital allocated to each asset. 
 The goal will be to determine the optimal value of weights that will maximize our objective function with respect to some constraints which are:

$$
\displaystyle\sum\limits_{i=1}^{N}x_{i}=1 \quad 0 \leq x_{i}\leq 1
$$

### Objective function
A usefull objective function for portfolio optimization is the **Sharpe Ratio**, defined as:

$$
\text{Portfolio Sharpe} = \frac{E(P)}{\sqrt{Var(P)}}
$$

Where E(P) is the **expected return** of the portfolio, Var(p) is the **variance**. 
The overall aim is to determine a portfolio whose returns are stable around the mean. Thus it is not the highest return that is sought, but the **highest stability of portfolio**.

### Penalty Function method
'/img/posts/explicit_my3.gif'




As you can see, the portfolio return (black thick line) is the **most stable** curve, although it’s not the best performing one (Amazon performs better). It’s nice to see that our portfolio outperforms S&P 500.