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

## What is entropy?

Suppose we have a state $i$ that comprises $\Omega_i$ microstates, each of probability $p_i$

$$
    P_i = \Omega_i p_i
$$

. . .

$$
    \epsilon_i = - K_B T \log(\Omega_i p_i) - K_B T \log(Z)
$$

## What's the difference?

$$
    \epsilon_i = - K_B T \log(\Omega_i p_i) - K_B T \log(Z)
    \\
    \epsilon_j = - K_B T \log(\Omega_j p_j) - K_B T \log(Z)
$$

. . .

$$
    \epsilon_i - \epsilon_j =  - K_B T \log(\Omega_i p_i) + K_B T \log(\Omega_j p_j)
$$

. . .

$$
    \epsilon_i - \epsilon_j =   - K_B T \log(p_i) + K_B T \log(p_j)
    \\ \qquad \qquad \qquad - K_B T \log(\Omega_i) + K_B T \log(\Omega_j)
$$

. . .

$$
    \Delta \epsilon =  \Delta[- K_B T \log(p)] - T \Delta[K_B \log(\Omega)]
$$

## Anyone recognise this?

$$
    \Delta \epsilon =  \Delta[- K_B T \log(p)] - T \Delta[K_B \log(\Omega)]
$$

. . .

$$
G = \epsilon
\\
H = - K_B T \log(p)
\\
S = K_B \log(\Omega)
$$

. . .

$$
    \Delta G =   \Delta H - T \Delta S
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
