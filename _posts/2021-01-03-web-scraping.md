---
layout: post
title: "Markov Reward Process"
subtitle: "A basic introduction into Markov decision processes"
date: 2020-01-26 23:45:13 -0400
background: '/img/posts/01.png'
usemathjax: true
---

#### Markov Reward Process
 A _Markov reward process_ (MRP) is a _Markov process_ with _rewards_. It consists of states, state transition probability matrix **plus** reward function and a discount factor. See the follwing example of an MRP with reward process.

**Rewards** are the **numerical values** that the agent receives on performing some action at some **state(s)** in the environment. The numerical value can be positive or negative based on the actions of the agent.

Mathematically, we define Markov Reward Process as :
$$
R_s = E[R_{t+1}|S_t]
$$
We define MRP as (S,P, R,ɤ) , where :

-   $$\mathcal{S}$$ is a set of states,
-   $$\mathcal{P}$$ is the Transition Probability Matrix,
-   $$\mathcal{R}$$ is the Reward function, we saw earlier,
-   $$\mathcal{\gamma}$$ is the discount factor


In **[[Reinforcement Learning]]**, we care about **maximizing** the cumulative reward (all the rewards agent receives from the environment) instead of, the reward agent receives from the current state(also called immediate reward). This **total sum of reward** the agent receives from the environment is called **returns**.
![[Pasted image 20220602203440.png]]
**Return** is a total discounted *reward* from the present. The *discount factor* is the present value rewards and has a value between 0 and 1. When the discount factor is close to 0, it prefers immediate reward to delayed reward. When its close to 1, it values delayed reward above immediate reward.

we want to avoid infinite returns by setting the discount factor less than 1. Second, immediate rewards may actually be more valuable. Third, human behavior shows a preference for immediate _rewards_, such as choosing to shop now instead of saving for the future.

The *return*  (**G**) can be calculated using reward (**R**) and discount factor (**gamma**) as follows:
$$
G_1 = R_{t+1} + \gamma  R_{t+2} + \gamma^2 R_{t+3} + ...+ = 
\displaystyle\sum\limits_{k=0}^{\infty } \gamma^{k} R_{t+k+1}
$$
Example:
For a sample episode [C1 C2 C3 Pass Sleep] the return is
$G = -2 + (-2*0.5) + (-2*0.5^2) + (10*0.5^3)=-2.25$

**[[Value Function]]** is the expected return from a state. A value function determines the value of a _state_ which indicates the desirability of a _state_. Using the **Bellman equation**, we can calculate current state value with only the current *reward* and the next *state value*.

$$
v(s) = E[G_t| S_t =s]
$$

$$
v(s) = E[R_{t+1} + \gamma v(S_{t+1}) | S_t = s] 
$$

Which is equivalent to:

$$
v(s) = \mathcal{R}_s + \gamma \displaystyle\sum\limits_{s'\in \mathcal{S}} \mathcal{P}_{ss'}v(s')
$$

The current state value is equal to the current reward plus the sum of the next state values multiplied with their transisition probability and the discount gamma. 

What this means is that we only need the next _state_ to calculate the total _value_ of a _state_. In other words, we can have a recursive function until the process ends.

Let’s take a look at the Student MRP again with _gamma_ equals to **1**. The image below represents the Student MRP with a _value_ in each _state_. This value has been calculated before, now we want to verify the _value_ in Class 3 (red circle) with the equation



![[Pasted image 20220602205419.png]]

We can see from Class 3 that the _value_ is calculated by summing the immediate _reward_ (-2) with the expected _value_ of two next _states_. To calculate the expected _value_ of the next _state_, we can multiply the transition probability with the value of the _state_. Hence, we get:
$-2 + 0.6*10* + 0.4*0.8=4.3$ 

The Bellman equation can be expressed with matrices:

$$
\begin{bmatrix} v(1) \\  ... \\ v(n)  \end{bmatrix} = \begin{bmatrix} \mathcal{R}_1 \\  ... \\ \mathcal{R}_n   \end{bmatrix} + \gamma \begin{bmatrix} \mathcal{P}_11 & ...&  \mathcal{P}_{1n} \\  ... \\ \mathcal{P}_{n1} & ...&  \mathcal{P}_{nn}   \end{bmatrix}\begin{bmatrix} v(1) \\  ... \\ v(n)  \end{bmatrix}
$$

Which is a linear equation that can be solved:

$$
\begin{aligned}
v &= \mathcal{R} + \gamma  \mathcal{P}v\\
 (I - \gamma \mathcal{P})v   &=\mathcal{R}\\
  v &= (I - \gamma \mathcal{P})^{-1}\mathcal{R}
\end{aligned}
$$

Where I is the identity matrix, Unfortunately this matrix inversion is too slow, except for small MDPs, so we use iterative methods for larger MDP (MC evaluation and TD learning)

[[Markov Decision]] Process is a Markov reward process with decisions

