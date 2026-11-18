# NumPy: Random Number Generation

## 1. Introduction and definition
NumPy's `Generator` API produces reproducible pseudo-random samples from many distributions.

## 2. Why we need this
Randomness is used for simulations, sampling, shuffling, bootstrapping and creating reproducible experiments.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``np.random.default_rng`` | Create a modern random Generator. |
| ``rng.random`` | Uniform samples in [0,1). |
| ``rng.integers`` | Random integers from a specified interval. |
| ``rng.normal`, `rng.uniform`` | Samples from normal or uniform distributions. |
| ``rng.choice`` | Sample values, optionally with probabilities. |
| ``rng.shuffle`, `rng.permutation`` | Shuffle in place or return a permutation. |
| ``rng.binomial`, `rng.poisson`, `rng.exponential`` | Sample from common distributions. |
| ``rng.multivariate_normal`` | Sample correlated multivariate normal values. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import numpy as np
rng = np.random.default_rng(seed=42)
print(rng.integers(1, 7, size=5))
print(rng.choice(["A", "B", "C"], size=4))
```

## 5. Advanced examples
```python
rng = np.random.default_rng(7)
population = np.arange(1000)
sample = rng.choice(population, size=100, replace=False)
print(sample.mean())
```

## 6. Practical real-world applications
Create repeatable train/test samples, bootstrap confidence intervals and Monte Carlo simulations.

## 7. Common mistakes
Using global legacy random state; forgetting the seed when reproducibility matters; sampling without replacement when sample size exceeds population; confusing a seed with a guarantee across all library versions.

## 8. Practice questions
Simulate 10,000 dice rolls; sample 10% of records; compare normal and uniform samples.

## 9. Interview questions
Why use `default_rng`? What is sampling with replacement? Why set a seed?

## 10. Related functions and concepts
Probability, distributions, sampling, simulation and evaluation.
