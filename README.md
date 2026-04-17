# Venus Fly Trap — Poisson Closure Model 🌱

A stochastic model of insect arrivals and trap closures in a Venus fly trap,
built cell by cell, next to the actual plant it models.

---

## The origin

A few weeks ago I got a new plant.
I named her Lambda.

Not because I planned to model her —
but because she felt like a rate.
Something that happens at a certain frequency,
unpredictably, in continuous time.

Then I started watching her.
And I noticed I never saw her close.

That question — *why does it never close when I'm watching?* —
turned into a probability question:
how rare is a closure, really?
What would I need to observe to see one?

And that turned into this.

---

## The thought process

It started with a simple observation:
the trap has two states — open and closed.
But the *event* that causes the transition is hidden.

That's already a stochastic process.

Then came the first model:
insects arrive randomly, with no fixed schedule, no memory.
That's Poisson.

Then the refinement:
not every arrival triggers a closure.
The trap requires two touches within a short time window —
a biological filter against false positives.
That's thinning.

Then the question got interesting:
why two touches? Why not one? Why not three?
Because closing costs energy.
A wrong closure wastes a resource the plant can't easily recover.

That's an optimization problem.

And the trap can only close a limited number of times before it wears out —
typically 3 to 7 closures per lobe.
That's a constraint.

So Lambda is not just a plant.
She is a small inference machine with a limited budget,
solving an optimization problem under uncertainty,
one insect at a time.

---

## The model

| Layer | Description |
|-------|-------------|
| 1 | Insect arrivals as a Poisson process with rate λ |
| 2 | Thinning: each arrival triggers a closure with probability p |
| 3 | Value function V(p) = λ[B·q(p) − C·p] |
| 4 | Constrained optimization: wear limits Lambda's closure budget |

---

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
