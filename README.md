# Venus Fly Trap — Poisson Closure Model 

A stochastic model of insect arrivals and trap closures in a Venus fly trap,
built next to a real plant named Lambda.

## The idea

Venus fly traps don't close on every touch.
They wait for two signals within a short time window —
a biological filter that reduces false positives and saves energy.

This project models that behavior using:
- **Poisson processes** to model random insect arrivals
- **Thinning** to model the probability of a closure given a visit
- **A value function** to quantify the tradeoff between captures and costs
- **Constrained optimization** to find the optimal closure policy

## Structure
notebooks/
└── poisson_venus_fly_trap.ipynb   ← full model, built cell by cell

## Layers

| Layer | Description |
|-------|-------------|
| 1 | Insect arrivals as a Poisson process |
| 2 | Thinning: not every visit triggers a closure |
| 3 | Value function V(p): benefit vs cost |
| 4 | Constrained optimization: wear limits Lambda's sensitivity |

## Requirements
numpy
matplotlib

## Inspiration

A plant. A desk. A question:
*why does it never close when I'm watching?*
