# Probability and Common Distributions

## 1. Introduction and definition
Probability quantifies uncertainty. Distributions describe how values or outcomes occur under a probabilistic model.

## 2. Why we need this
Probability supports sampling, risk analysis, experiment design and statistical inference.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| `Complement rule` | P(not A) = 1 - P(A). |
| `Addition rule` | P(A or B), accounting for overlap. |
| `Multiplication rule` | P(A and B), using conditional probability when needed. |
| `Conditional probability` | P(A|B) = P(A and B)/P(B). |
| `Bayes' theorem` | Update a probability using evidence. |
| `Bernoulli/Binomial` | Binary trial and number of successes in fixed trials. |
| `Poisson` | Count events over a fixed interval under assumptions. |
| `Uniform` | Equal density over an interval. |
| `Normal` | Symmetric bell-shaped continuous distribution. |
| `Exponential` | Waiting time between Poisson-process events. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
from scipy import stats
print(stats.binom.pmf(3, n=10, p=0.5))
print(stats.norm.cdf(1.96))
```

## 5. Advanced examples
```python
import numpy as np
rng = np.random.default_rng(42)
sample = rng.normal(loc=100, scale=15, size=10000)
print(sample.mean(), sample.std())
```

## 6. Practical real-world applications
Estimate defect probabilities, model arrivals, understand measurement variation and calculate expected risk.

## 7. Common mistakes
Assuming independence without evidence; applying a distribution without checking assumptions; confusing probability density with probability at a point for continuous variables.

## 8. Practice questions
Calculate conditional probability; choose a distribution for count data; simulate coin tosses; interpret a normal quantile.

## 9. Interview questions
Explain Bayes' theorem. When use binomial vs Poisson? What assumptions support a normal model?

## 10. Related functions and concepts
Sampling, inference, simulation, hypothesis testing and confidence intervals.
