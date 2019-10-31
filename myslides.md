---
author: Josh Mitchell
title: Computational Chemistry Considered ???
date: November 9, 2019

theme: simple
slideNumber: \"c/t\"
margin: 0.2

revealjs-url: reveal.js
---
# Why am I here
::: incremental
- Computational methods can be...
    - Complementary to experiment
    - Faster/cheaper than experiment
    - More detailed than experiment
- Though usually not at the same time
:::

# Lets think statistically

## Protein structure forms according to a probability distribution

Ready for some maths?

----

##### The Boltzmann Distribution

[$$
    P_i = \frac{\exp(-\beta\epsilon_i)}{Z}
$$]{style="font-size: 54px"}

$P_i$ is the probability of state $i$

$\exp(x)$ is the exponential function $e^x$

$\epsilon_i$ is the energy of state $i$

::: notes
Which energy $\epsilon_i$ represents depends on how state $i$ is represented
- Free energy for coarse grained representations
- Hamiltonian for canonical ensemble in phase space
- Potential energy for canonical ensemble in configuration space
:::

$\beta = \frac{1}{K_BT}$ incorporates the temperature

. . .

$$
    Z = \sum_{i}\exp(-\beta\epsilon_i)
$$

## Fast methods assume there's only one state

[$$
    P_i = \frac{\exp(-\beta\epsilon_i)}{Z}
$$]{style="font-size: 54px"}

$$
    Z = \sum_{i}\exp(-\beta\epsilon_i)
$$

# No more maths

I promise

# So
