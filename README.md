# Graphical Models and Probabilistic Inference Projects

This repository contains three cleaned mini-projects developed from coursework in graphical models and later reorganized into research-oriented case studies.

The main focus is on:
- latent-variable sequence modeling
- exact and approximate inference
- message passing on graphical models
- numerical stability in probabilistic computation

## Featured Projects

### 1. Mixture of Markov Chains with EM
A latent-variable model for identifying hidden weather stations from observed symbolic sequences.  
This project implements a 3-component mixture of first-order Markov chains and estimates the model using the EM algorithm. The implementation highlights non-convex optimization, initialization sensitivity, log-domain likelihood computation, and smoothing for stable estimation.

**Keywords:** EM, latent variables, sequence modeling, Markov chains, numerical stability

### 2. Exact Inference vs Mean Field vs Gibbs Sampling
A comparative study of exact and approximate inference on a binary lattice model.  
This project contrasts transfer-matrix-based exact inference, fully factorized mean field, and checkerboard Gibbs sampling, with particular attention to symmetry breaking and mixing behavior under different coupling strengths.

**Keywords:** exact inference, variational inference, Gibbs sampling, Ising model, approximation error

### 3. LDPC Decoding with Loopy Belief Propagation
A factor-graph-based implementation of LDPC decoding.  
This project constructs a systematic generator matrix and performs log-domain loopy belief propagation for decoding under noisy observations.

**Keywords:** factor graphs, belief propagation, LDPC, message passing, probabilistic decoding

## Why this repository
Rather than presenting raw coursework chronologically, this repository reorganizes the material around methodological themes that are central to probabilistic machine learning:
- latent-variable estimation
- approximate inference
- structured probabilistic computation

## Repository Structure

- `weather-stations-em/`: EM for a mixture of Markov chains
- `exact-vs-approx-inference/`: exact inference, mean field, and Gibbs sampling
- `ldpc-belief-propagation/`: belief propagation for LDPC decoding
- `extras/`: smaller supporting exercises

## Reproducibility

Each subproject contains:
- a short project-specific README
- a cleaned notebook
- exported figures for quick inspection

## Research Relevance

These projects were selected and reorganized to highlight training in probabilistic modeling and inference, especially:
- formulating latent-variable models
- implementing inference algorithms beyond black-box usage
- analyzing optimization and approximation failure modes
- reasoning about structured probabilistic systems

Install dependencies with:

```bash
pip install -r requirements.txt

