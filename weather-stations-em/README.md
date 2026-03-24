# Mixture of Markov Chains with EM for Weather Station Identification

## Overview
This project studies a latent-variable sequence modeling problem: given a collection of symbolic weather sequences, infer which hidden weather station generated each sequence and estimate the corresponding dynamics.

I model the data using a mixture of first-order Markov chains and fit the model with the Expectation-Maximization (EM) algorithm.

## Problem Setup
Each observed sequence is assumed to come from one of several hidden weather stations.  
Each station is represented by:
- a mixture weight
- an initial-state distribution
- a transition matrix over weather states

The latent variable indicates which station generated a given sequence.

## Model
For each sequence \(x_m\), the model introduces a latent component \(z_m\), and factorizes the joint distribution as:

\[
p(x_m, z_m) = p(z_m)\, p(x_{m,1}\mid z_m)\, \prod_{t=2}^T p(x_{m,t}\mid x_{m,t-1}, z_m).
\]

The model parameters are:
- mixture weights
- initial probabilities
- transition probabilities

## Inference
The parameters are estimated with EM:

### E-step
Compute posterior responsibilities:
\[
r_{m,k} = p(z_m = k \mid x_m)
\]

### M-step
Update:
- mixture weights
- initial-state probabilities
- transition matrices

using expected sufficient statistics under the current responsibilities.

## Implementation Notes
The implementation is designed to be numerically stable and reproducible:
- likelihoods are computed in the log domain
- normalization uses `logsumexp`
- pseudocount smoothing prevents zero-probability transitions
- multiple random restarts are used because EM is non-convex

## Main Results
Across multiple random restarts, the model converged to several distinct local optima.  
This highlights the non-convex nature of EM and the practical importance of restart strategies in latent-variable estimation.

The learned parameters include:
- mixture weights for the hidden stations
- initial-state probabilities
- station-specific transition matrices

Posterior responsibilities for individual sequences also become sharply concentrated, indicating that the fitted components capture distinct sequence-generating behaviors.

## Main Takeaways
This project was particularly useful for understanding:
- latent-variable sequence models
- EM beyond textbook derivation
- sensitivity to initialization
- symmetry-related failure modes
- the importance of numerical stability in probabilistic modeling

## What to Look At
- `weather_stations_em.ipynb`
- `figures/em_restarts.png`
- `figures/learned_transition_matrices.png`
- `figures/posterior_assignments.png`

## Possible Extensions
Natural next steps include:
- comparing different initialization strategies
- selecting the number of components
- adding stronger priors or regularization
- comparing EM with gradient-based optimization

## Relevance
This mini-project is most relevant to research directions involving:
- probabilistic machine learning
- latent-variable modeling
- sequence modeling
- approximate inference
