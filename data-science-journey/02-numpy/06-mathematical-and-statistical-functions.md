# NumPy: Mathematical and Statistical Functions

## 1. Introduction and definition
NumPy provides vectorized arithmetic, trigonometric, rounding, aggregation and statistical operations.

## 2. Why we need this
These functions are the building blocks for summaries, feature transformations and numerical analysis.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``np.sum`, `np.prod`` | Sum or multiply values along selected axes. |
| ``np.mean`, `np.average`` | Arithmetic or weighted average. |
| ``np.median`, `np.percentile`, `np.quantile`` | Robust center and quantile summaries. |
| ``np.std`, `np.var`` | Standard deviation and variance. |
| ``np.min`, `np.max`, `np.argmin`, `np.argmax`` | Extremes and their positions. |
| ``np.nanmean`, `np.nansum`, `np.nanstd`` | NaN-aware reductions. |
| ``np.sqrt`, `np.exp`, `np.log`, `np.log10`` | Common mathematical transforms. |
| ``np.abs`, `np.round`, `np.floor`, `np.ceil`` | Absolute value and rounding. |
| ``np.sin`, `np.cos`, `np.tan`` | Trigonometric functions. |
| ``np.cumsum`, `np.cumprod`` | Cumulative operations. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import numpy as np
x = np.array([2, 4, 6, 8])
print(np.mean(x))       # 5.0
print(np.median(x))     # 5.0
print(np.std(x))        # 2.2360679...
print(np.percentile(x, 75))
```

## 5. Advanced examples
```python
scores = np.array([[80, 90, 70], [75, 85, 95]])
print(scores.mean(axis=0))  # [77.5 87.5 82.5]
print(scores.mean(axis=1))  # [80. 85.]
```

## 6. Practical real-world applications
Summarize sales, calculate percentile thresholds, normalize values, inspect distributions and aggregate measurements by axis.

## 7. Common mistakes
Confusing population standard deviation (`ddof=0`) with sample standard deviation (`ddof=1`); ignoring NaNs; misunderstanding axis; assuming weighted average equals mean.

## 8. Practice questions
Compute row/column means; find 90th percentile; compare `std` with `nanstd`; calculate cumulative sales.

## 9. Interview questions
What is an axis? What is `ddof`? Difference between mean and median? When use percentiles?

## 10. Related functions and concepts
Statistics, pandas aggregation, missing values and broadcasting.
