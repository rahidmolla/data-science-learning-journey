# Sampling, Confidence Intervals and Hypothesis Testing

## 1. Introduction and definition
Statistical inference uses sample data to estimate population quantities and assess evidence about hypotheses.

## 2. Why we need this
Business decisions often use samples; inference communicates uncertainty rather than presenting a sample statistic as exact truth.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| `Sampling distribution` | Distribution of a statistic across repeated samples. |
| `Standard error` | Estimated standard deviation of a statistic. |
| `Confidence interval` | Procedure that captures the true parameter at a stated long-run rate. |
| `Null/alternative hypothesis` | Competing statements about a population parameter. |
| `p-value` | Probability, under the null model, of data at least as extreme as observed. |
| `Type I/II errors` | False positive and false negative errors. |
| `Power` | Probability of detecting a specified effect when it exists. |
| `t-test` | Compare means under assumptions. |
| `Chi-square test` | Test association or fit for categorical counts. |
| `Mann–Whitney U` | Nonparametric comparison of distributions/ranks. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
from scipy import stats
group_a = [21, 22, 19, 24, 20]
group_b = [25, 27, 23, 26, 24]
result = stats.ttest_ind(group_a, group_b, equal_var=False)
print(result.statistic, result.pvalue)
```

## 5. Advanced examples
```python
import numpy as np
from scipy import stats
rng = np.random.default_rng(10)
x = rng.normal(50, 10, 100)
ci = stats.t.interval(.95, df=len(x)-1, loc=x.mean(), scale=stats.sem(x))
print(ci)
```

## 6. Practical real-world applications
Evaluate A/B tests, compare process changes, estimate average order value and communicate uncertainty.

## 7. Common mistakes
Interpreting p-value as probability the null is true; ignoring effect size; running many tests without correction; confusing statistical and practical significance.

## 8. Practice questions
Write null/alternative hypotheses; interpret a p-value; calculate a confidence interval; select a test for categorical data.

## 9. Interview questions
What does a 95% confidence interval mean? What is Type I error? Why report effect size?

## 10. Related functions and concepts
Experimental design, distributions, correlation, regression and business metrics.
