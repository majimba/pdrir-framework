# First-Principles Thinking: A Practical Guide

Reason from the ground up by reducing problems to fundamental truths and rebuilding solutions without inherited assumptions.

## What it is

First-principles thinking separates facts (constraints, physics, protocols, invariants) from assumptions (habits, defaults, opinions). You decompose, validate each truth, and reconstruct the simplest system that must work under those truths.

## Core steps

- Define the goal: What outcome must be achieved, minimally?
- List fundamentals: What must be true? What are hard constraints? What are invariants?
- Expose assumptions: What are we taking for granted? How can we falsify them quickly?
- Model from basics: Sketch the minimal mechanism that satisfies the truths.
- Recombine: Add only what is necessary; prefer composable primitives.
- Test cheaply: Prototypes that validate or invalidate the riskiest assumptions first.

## How it supports PDRIR

- P (Problem): Clarifies the real need vs. the assumed need.
- D (Deconstruction): Primary driver—enumerate fundamental truths and constraints.
- R (Research): Targeted search for tools that satisfy identified truths.
- I (Implementation): Encourages minimal, composable architecture.
- R (Refinement): Remove accidental complexity; revisit assumptions that failed.

## Quick checklist

- Can we state the problem without mentioning a tool or UI?
- Which 3 constraints would make the solution impossible if wrong?
- What can we remove without breaking correctness?
- What is the cheapest test to invalidate our riskiest assumption?

## Common pitfalls

- Confusing popularity with necessity.
- Skipping falsification; only seeking confirming evidence.
- Overfitting to the first working prototype.

## Sources and further reading (add your own)

- TODO: Add articles, notes, and experiments validating/invalidating assumptions.

