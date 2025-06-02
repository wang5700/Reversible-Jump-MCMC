This project contains a 10-page essay titled "Monte Carlo Simulation" by Xiaolong Wang from the Department of Statistics, University of Chicago. The essay explores the Reversible Jump Markov Chain Monte Carlo (RJMCMC) method, a powerful extension of traditional MCMC techniques for Bayesian inference across models with varying dimensions. RJMCMC enables trans-dimensional sampling, making it ideal for Bayesian model selection and variable selection tasks.
The essay provides a detailed introduction to RJMCMC, including its algorithm, applications in Bayesian linear regression, and Bayesian model selection (Poisson vs. Negative Binomial). It also includes simulation results and a discussion of implementation challenges and recent advancements.
Essay Structure

Section 1: Reversible Jump MCMC

Introduces the RJMCMC method and its algorithm (Algorithm 1.1).
Explains how RJMCMC extends traditional MCMC by allowing jumps between models of different dimensions while preserving convergence properties.


Section 2: Variable Selection using RJMCMC

Applies RJMCMC to Bayesian Linear Regression for variable selection.
Models considered:
Model 0: $ ( Y_i = \beta_0 + \beta_1 X_{1i} + \epsilon_i ) $
Model 1: $ ( Y_i = \beta_0 + \beta_1 X_{1i} + \beta_2 X_{1i}^2 + \epsilon_i )$


Details within-model (Metropolis-Hastings) and between-model moves (Model 0 to Model 1 and vice versa).
Simulation results include trace plots and histograms for (\beta_0), (\beta_1), and (\beta_2), showing convergence and posterior distribution estimates.


Section 3: Bayesian Model Selection

Demonstrates RJMCMC in a Poisson vs. Negative Binomial model selection problem for count data.
Likelihoods are reparameterized to share a common mean (\lambda).
Discusses within-model and between-model moves, including Jacobian calculations for dimension changes.
Posterior model probabilities and Bayesian model-averaged posterior mean of (\lambda) are computed.


Section 4: Discussion and Bibliography

Discusses challenges in RJMCMC implementation, such as designing efficient proposal distributions.
Reviews recent advancements in improving RJMCMC efficiency (e.g., adaptive proposals, irreversible jump processes).



Key Details

Simulation Setup (Section 2.5):

True data-generating process: ( Y_i = 1 + 2X_{1i} + 0.5X_{1i}^2 + \epsilon_i ), where (\epsilon_i \sim N(0, 0.5)).
Prior parameters: (\sigma_\beta^2 = 10), (\sigma_u^2 = 1), (\tau^2 = 0.05).
Transition probabilities: ( h = \begin{bmatrix} 0.5 & 0.5 \ 0.5 & 0.5 \end{bmatrix} ).
Prior beliefs: ( P(M=0) = P(M=1) = 0.5 ).


Bayesian Model Selection (Section 3):

Compares Poisson (Model 0) and Negative Binomial (Model 1) distributions for count data.
Reparameterization: (\lambda = r(1-p)/p) for Negative Binomial to align means.
Posterior probabilities approximated via RJMCMC iterations: ( P(\text{Model 0} \mid X) \approx N_0/N ), ( P(\text{Model 1} \mid X) \approx N_1/N ).



References
The essay cites several key works on RJMCMC, including:

Green (1995) - Introduction of RJMCMC.
Hastie and Green (2012) - Model choice using RJMCMC.
Ma et al. (2018) - Irreversible samplers for improved efficiency.
Norets (2020) - Optimal auxiliary priors for RJMCMC.

Usage
This essay serves as a theoretical and applied introduction to RJMCMC. Researchers and students can use it to:

Understand the RJMCMC algorithm and its implementation.
Explore practical applications in Bayesian linear regression and model selection.
Review simulation techniques and interpret MCMC diagnostics (trace plots, histograms).

For further details, refer to the full essay document: Xiaolongw_essay_RJMCMC (1).pdf.
