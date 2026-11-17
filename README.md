# ASS-1-MVA

Bayesian Statistics --- Beta-Binomial Model
Overview
This notebook introduces Bayesian statistics and demonstrates sequential
Bayesian updating with a conjugate Beta-Binomial model. A simulated
coin-flip experiment is used to update a prior belief about the
probability of heads after observing data.
Objectives
- Understand prior, likelihood, posterior, and evidence in Bayes'
  theorem.
- Apply the Beta-Binomial conjugate model.
- Update a prior distribution using observed coin-flip outcomes.
- Calculate a 95% Bayesian credible interval.
- Compare the Bayesian interval interpretation with a frequentist
  confidence interval.
- Visualize how the posterior changes as more observations are
  collected.
- Explore connections between Bayesian inference and machine learning.
Tools and Libraries
- Python
- NumPy
- SciPy (scipy.stats)
- Matplotlib
Bayes' Theorem
Bayesian inference updates a prior belief using observed evidence:
`\frac{P(\text{data} \mid \theta)P(\theta)}{P(\text{data})}`{=tex} \]

-   **Prior:** belief about the parameter before observing data.
-   **Likelihood:** probability of the observed data under a parameter
    value.
-   **Posterior:** updated belief after observing data.
-   **Evidence:** normalizing constant.

## Beta-Binomial Conjugate Model

For a coin-flip probability (p), the notebook uses a Beta prior:

\[ p
`\sim `{=tex}`\operatorname{Beta}`{=tex}(`\alpha`{=tex},`\beta`{=tex})
After observing (k) heads in (n) flips, the posterior is:
`\operatorname{Beta}`{=tex}(`\alpha`{=tex}+k,`\beta`{=tex}+n-k) \]

This conjugate update can be computed directly without numerical
integration.

## Notebook Workflow

### 1. Set up the prior and simulate data

-   Prior: `Beta(2, 2)`, with prior mean 0.50.
-   Simulated true probability: `0.65`.
-   Number of coin flips: `50`.
-   Random generator seed: `42`.

### 2. Update the posterior

The simulation produces 28 heads out of 50 flips. The posterior becomes
`Beta(30, 24)`, with posterior mean approximately `0.5556`.

### 3. Calculate intervals

The notebook calculates a 95% Bayesian credible interval from the
posterior distribution and also calculates a frequentist 95% Wald
interval for comparison.

The notebook output reports: - Bayesian 95% credible interval:
`(0.4228, 0.6844)` - Frequentist 95% Wald interval: `(0.4224, 0.6976)`

A Bayesian credible interval describes a range containing 95% posterior
probability for the parameter. A frequentist confidence interval has a
repeated-sampling interpretation: 95% of intervals constructed by the
procedure would contain the true parameter.

### 4. Visualize sequential updating

The notebook plots posterior distributions at checkpoints of 1, 5, 10,
25, and 50 flips. The visualization shows how the posterior distribution
changes as observations accumulate.

### 5. ML/AI connection

The notebook discusses these connections: - **Ridge (L2)
regularization:** corresponds to MAP estimation with a Gaussian prior on
weights. - **Lasso (L1) regularization:** corresponds to a Laplace prior
on weights. - **Bayesian hyperparameter optimization:** maintains a
posterior over model performance and uses it to guide subsequent
trials. - **Uncertainty quantification:** Bayesian deep learning can
provide predictive distributions rather than only point predictions.

## How to Run

1.  Clone or download this repository.

2.  Install the required libraries:

    ``` bash
    pip install numpy scipy matplotlib jupyter
    ```

3.  Start Jupyter Notebook:

    ``` bash
    jupyter notebook
    ```

4.  Open `28 Bayesian Statistics.ipynb` and run the cells in order.

## Key Result

With the notebook's fixed random seed, 28 heads are observed in 50
flips. Starting from `Beta(2, 2)`, the posterior is `Beta(30, 24)`. This
illustrates how observed evidence updates an initial prior belief.

## Author

Add your name here.
