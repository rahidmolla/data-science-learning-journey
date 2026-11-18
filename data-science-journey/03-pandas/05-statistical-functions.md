# pandas: Statistical and Descriptive Functions

## 1. Introduction and definition
pandas provides Series and DataFrame methods for descriptive statistics, ranking, correlation and aggregation.

## 2. Why we need this
These summaries help understand central tendency, spread, extremes, relationships and data quality.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``.max`, `.min`` | Maximum/minimum by Series or DataFrame axis. |
| ``.mean`, `.median`, `.mode`` | Mean, median and most frequent value(s). |
| ``.sum`, `.count`, `.size`` | Sum, non-null count and group/axis size. |
| ``.std`, `.var`` | Standard deviation and variance. |
| ``.quantile`` | Calculate requested quantiles. |
| ``.describe`` | Generate summary statistics. |
| ``.idxmax`, `.idxmin`` | Return labels of maximum/minimum. |
| ``.corr`, `.cov`` | Correlation and covariance. |
| ``.rank`, `.nlargest`, `.nsmallest`` | Rank and select top/bottom values. |
| ``.cumsum`, `.cummin`, `.cummax`` | Cumulative summaries. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import pandas as pd
df = pd.DataFrame({"math": [80, 90, 70], "science": [85, 75, 95]})
print(df.max())
print(df.mean(axis=0))
print(df[["math", "science"]].max(axis=1))
```

## 5. Advanced examples
```python
print(df.quantile([0.25, 0.5, 0.75]))
print(df.corr(numeric_only=True))
print(df["math"].nlargest(2))
```

## 6. Practical real-world applications
Find top-performing products, calculate average order values, inspect score distributions and understand relationships among numeric variables.

## 7. Common mistakes
`DataFrame.max()` returns per-column results by default, not one scalar overall; `count` excludes missing values while `size` counts slots; `mode` can return multiple values; correlation does not imply causation.

## 8. Practice questions
Find maximum by row and column; calculate 36th percentile; compare `count` and `size`; rank the top five records; compute a correlation matrix.

## 9. Interview questions
Explain `axis`; difference between `count` and `size`; what does `skipna` do? What does a correlation of -0.8 mean?

## 10. Related functions and concepts
NumPy reductions, GroupBy aggregation, missing values, statistics and visualization.
