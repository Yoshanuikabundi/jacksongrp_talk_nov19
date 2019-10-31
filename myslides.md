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
$$]{style="font-size: 54px"}

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
    1 = P_\mathrm{min} = \frac{
        \exp(-\beta\epsilon_\mathrm{min})
    }{
        Z
    }
    \\
    Z = \sum_i^1\exp(-\beta\epsilon_{i}) = \exp(-\beta\epsilon_\mathrm{min})
$$

. . .

Entropic effects must be part of the energy $\epsilon$

## Anyone want more maths?

A really nice way to think about entropy is only a few algebraic manipulations away!

## What *is* energy

$$
    P_i = \frac{
        \exp(-\beta\epsilon_i)
    }{
        Z
    }
$$

. . .

$$
    \exp(-\frac{1}{K_B T}\epsilon_i) = P_i Z
$$

. . .

$$
    -\frac{1}{K_B T}\epsilon_i = \log(P_i Z)
$$

. . .

$$
    \epsilon_i = - K_B T \log(P_i) - K_B T \log(Z)
$$

## What about the difference?

$$
    \epsilon_i = - K_B T \log(P_i) - K_B T \log(Z)
    \\
    \epsilon_j = - K_B T \log(P_j) - K_B T \log(Z)
$$

. . .

$$
    \epsilon_i - \epsilon_j = - K_B T \log(P_i) + K_B T \log(P_j)
$$

. . .

$$
    \epsilon_i - \epsilon_j = - K_B T \log(\frac{P_i}{P_j})
$$

. . .

$$
    \Delta \epsilon = - K_B T \log(\Delta P)
$$

This is a bit abusive towards notation

## What is entropy

$$
    S_i = K_B \log(\Omega_i)
$$

$\Omega_i$ is the number of microstates within state $i$

$$
    \Delta G = \Delta H - T \Delta S
$$

. . .

$$
    \Delta G = - K_B T \log(\Delta P) - K_B T \log(\Delta \Omega)
$$

. . .

$$
    \Delta G = - K_B T \log(\Delta \Omega \Delta P)
$$

. . .

In reality, not all the microstates have the same energy, but this is the gist.

## If you want more, check out stat mech!

## Relative energies are negative log likelihoods

[$$
    \epsilon_i = - K_B T \log(P_i) - K_B T \log(Z)
$$]{style="font-size: 32px"}

. . .

[$$
    \epsilon_{i\mathrm{rel}} = - K_B T \log(P_i)
$$]{style="font-size: 48px"}

. . .

When we add energies, we multiply probabilities

[$$
    \epsilon_{i\mathrm{rel}} + \epsilon_{j\mathrm{rel}} = - K_B T \log(P_i P_j)
$$]{style="font-size: 48px"}

# What happens if we don't make that assumption?
MD!

## What happens if we don't make that assumption?

We need to "sample" from the entire Boltzmann distribution

# No more maths

I promise
