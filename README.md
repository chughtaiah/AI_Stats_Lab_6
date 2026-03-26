# AI/Stats Lab: MLE for Bernoulli and Poisson

## Overview

This lab is about Maximum Likelihood Estimation (MLE), with emphasis on:

- likelihood and log-likelihood
- Bernoulli and Poisson models
- analytical MLE derivations
- comparing candidate parameter values
- writing robust Python code with input validation

You will complete **2 tasks** in `AI_stats_lab.py`.

---

## Learning Goals

By the end of this lab, you should be able to:

- compute Bernoulli and Poisson log-likelihoods
- derive and implement MLE estimators
- explain why the sample mean appears in MLE
- compare candidate parameter values using log-likelihood
- handle invalid inputs correctly

---

## Files

- `AI_stats_lab.py` — starter code you must complete
- `test_AIstats_lab.py` — public tests
- `README.md` — instructions

---

## Task 1: Bernoulli MLE Analysis

Implement:

### `bernoulli_log_likelihood(data, theta)`

For Bernoulli data \(x_i \in \{0,1\}\),

\[
\ell(\theta) = \sum_{i=1}^n \left[x_i \log(\theta) + (1-x_i)\log(1-\theta)\right]
\]

Your function must:

- validate that data is non-empty
- validate that each observation is either 0 or 1
- validate that \(0 < \theta < 1\)
- return the log-likelihood as a float

### `bernoulli_mle_with_comparison(data, candidate_thetas=None)`

For Bernoulli data, the MLE is:

\[
\hat{\theta} = \frac{1}{n}\sum_{i=1}^n x_i
\]

Your function must return a dictionary containing:

- `mle`
- `num_successes`
- `num_failures`
- `log_likelihoods`
- `best_candidate`

If `candidate_thetas` is not provided, use:

```python
[0.2, 0.5, 0.8]
