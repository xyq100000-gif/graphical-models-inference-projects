# Exact Inference, Mean Field, and Gibbs Sampling on a Binary Lattice

## Overview
This project compares exact and approximate inference methods on a binary lattice model.

The goal is not only to implement different inference algorithms, but also to examine how their behavior changes across coupling regimes.

## Methods
The project studies three approaches:

### 1. Exact Inference
Exact inference is performed by transforming the 2D lattice into a 1D chain of super-nodes via column clustering, followed by message passing.

### 2. Mean Field Approximation
A fully factorized mean field approximation is optimized with coordinate ascent updates.

### 3. Gibbs Sampling
Checkerboard Gibbs sampling is used to estimate the target distribution under different coupling strengths.

## Main Questions
This project focuses on the following methodological questions:
- When does mean field break symmetry?
- When does Gibbs suffer from slow mixing?
- How close are approximate methods to exact inference?
- What kinds of approximation errors remain even after heuristic fixes?

## Main Takeaways
The main lessons from this project are:
- exact and approximate inference can behave very differently under strong coupling
- mean field can collapse to a single mode due to symmetry breaking
- single-chain Gibbs can mix slowly in multi-modal settings
- heuristic symmetrization or multi-chain averaging can partially restore the correct behavior

## What to Look At
- `exact_vs_approx_inference.ipynb`
- `figures/beta4_comparison.png`
- `figures/beta1_comparison.png`
- `figures/beta001_comparison.png`

## Relevance
This project is most relevant to:
- probabilistic inference
- variational methods
- sampling-based inference
- statistical machine learning
