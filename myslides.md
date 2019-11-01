---
author: Josh Mitchell
title: Computational Chemistry Considered ???
date: November 9, 2019

theme: simple
slideNumber: \"c/t\"
margin: 0.1

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

## Folded proteins have a funnel-shaped probability distribution

## Ready for some maths?

----

##### The Boltzmann Distribution

[$$
    P_i = \frac{\exp(-\beta\epsilon_i)}{Z}
$$]{style="font-size: 50px"}

$P_i$ is the probability of state $i$ at equilibrium

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

## There are two problems

[$$
    P_i = \frac{
        \exp(-\beta\epsilon_i)
    }{
        Z
    }
$$]{style="font-size: 72px"}

1. Which states are most important
2. How important are those states

## Fast methods assume there is only one important state

So we just find the minimum energy state

$$
    P_\mathrm{min} = \frac{
        \exp(-\beta\epsilon_\mathrm{min})
    }{
        \exp(-\beta\epsilon_\mathrm{min})
    } = 1
$$

. . .

Entropic effects must be part of the energy $\epsilon$

# What happens if we don't make that assumption? {style="font-size: 24px"}

[$$
    P_i = \frac{
        \exp(-\beta\epsilon_i)
    }{
        Z
    }
$$]{style="font-size: 72px"}

We need to "sample" from the entire Boltzmann distribution

# No more maths

I promise
