# LDPC Decoding with Loopy Belief Propagation

## Overview
This project implements a factor-graph-based LDPC decoder using loopy belief propagation in the log domain.

The work includes both the construction of a systematic generator matrix and iterative decoding under noisy observations.

## Components
The project consists of:
- constructing a systematic generator matrix from a parity-check matrix
- representing the code structure as a sparse graphical model
- performing iterative message passing for decoding
- recovering the transmitted message from the decoded codeword

## Implementation Notes
The implementation emphasizes:
- sparse neighborhood representations
- log-domain message updates
- clipping for numerical stability
- early stopping through parity checks

## Main Takeaways
This project helped me better understand:
- factor graph representations
- local message passing updates
- practical issues in iterative probabilistic decoding
- the gap between abstract BP equations and robust implementation details

## What to Look At
- `ldpc_belief_propagation.ipynb`
- `figures/tanner_graph.png`
- `figures/decoding_summary.png`

## Relevance
This project is most relevant to:
- graphical models
- message passing algorithms
- coding theory
- structured probabilistic inference
