# Reversible Jump MCMC (RJMCMC) Essay

## Overview
This repository contains a 10-page essay titled *"Monte Carlo Simulation"* by Xiaolong Wang from the Department of Statistics, University of Chicago. The essay explores the Reversible Jump Markov Chain Monte Carlo (RJMCMC) method, an extension of traditional MCMC techniques for Bayesian inference across models with varying dimensions. RJMCMC enables trans-dimensional sampling, making it ideal for Bayesian model selection and variable selection tasks.

The essay provides a detailed introduction to RJMCMC, including its algorithm, applications in Bayesian linear regression, and a Poisson vs. Negative Binomial model selection example. It also includes simulation results and a discussion of implementation challenges and recent advancements.

## Essay Structure
- **Section 1: Reversible Jump MCMC**
  - Introduces the RJMCMC method and its algorithm (Algorithm 1.1).
  - Explains how RJMCMC extends traditional MCMC by allowing jumps between models of different dimensions while preserving convergence properties.

- **Section 2: Variable Selection using RJMCMC**
  - Applies RJMCMC to Bayesian Linear Regression for variable selection.
  - Models considered:
    - Model 0: \( Y_i = \beta_0 + \beta_1 X_{1i} + \epsilon_i \)
    - Model 1: \( Y_i = \beta_0 + \beta_1 X_{1i} + \beta_2 X_{1i}^2 + \epsilon_i \)
  - Details within-model (Metropolis-Hastings) and between-model moves.
  - Simulation results include trace plots and histograms for \(\beta_0\), \(\beta_1\), and \(\beta_2\), showing convergence and posterior distribution estimates.

- **Section 3: Bayesian Model Selection**
  - Demonstrates RJMCMC in a Poisson vs. Negative Binomial model selection problem for count data.
  - Reparameterizes likelihoods to share a common mean \(\lambda\).
  - Discusses within-model and between-model moves, including Jacobian calculations.
  - Computes posterior model probabilities and Bayesian model-averaged posterior mean of \(\lambda\).

- **Section 4: Discussion and Bibliography**
  - Discusses challenges in RJMCMC implementation, such as designing efficient proposal distributions.
  - Reviews recent advancements (e.g., adaptive proposals, irreversible jump processes).

## Key Details
- **Simulation Setup (Section 2.5)**:
  - True data-generating process: \( Y_i = 1 + 2X_{1i} + 0.5X_{1i}^2 + \epsilon_i \), where \(\epsilon_i \sim N(0, 0.5)\).
  - Prior parameters: \(\sigma_\beta^2 = 10\), \(\sigma_u^2 = 1\), \(\tau^2 = 0.05\).
  - Transition probabilities: \( h = \begin{bmatrix} 0.5 & 0.5 \\ 0.5 & 0.5 \end{bmatrix} \).
  - Prior beliefs: \( P(M=0) = P(M=1) = 0.5 \).

- **Bayesian Model Selection (Section 3)**:
  - Compares Poisson (Model 0) and Negative Binomial (Model 1) distributions.
  - Reparameterization: \(\lambda = r(1-p)/p\) for Negative Binomial.
  - Posterior probabilities approximated via RJMCMC iterations: \( P(\text{Model 0} \mid X) \approx N_0/N \), \( P(\text{Model 1} \mid X) \approx N_1/N \).

## Repository Structure
