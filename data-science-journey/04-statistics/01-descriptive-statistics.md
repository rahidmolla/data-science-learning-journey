# Statistics: Descriptive Statistics

## 1. Introduction and definition
Descriptive statistics summarize observed data using measures of center, spread, position and shape.

## 2. Why we need this
They make a dataset understandable before modeling or decision-making.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| `Mean` | Arithmetic average; sensitive to extreme values. |
| `Median` | 50th percentile; robust center. |
| `Mode` | Most frequent value. |
| `Range` | Maximum minus minimum. |
| `Variance` | Average squared deviation under a chosen convention. |
| `Standard deviation` | Square root of variance; in original units. |
| `Quartiles/IQR` | 25th/50th/75th percentiles and interquartile range. |
| `Skewness` | Asymmetry of a distribution. |
| `Kurtosis` | Tail/shape measure; conventions differ. |
| `Coefficient of variation` | Standard deviation divided by mean, when meaningful. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import pandas as pd
x = pd.Series([10, 12, 12, 15, 51])
print(x.mean(), x.median(), x.mode().tolist())
print(x.quantile([.25, .5, .75]))
```

## 5. Advanced examples
```python
q1, q3 = x.quantile([.25, .75])
iqr = q3 - q1
lower, upper = q1 - 1.5 * iqr, q3 + 1.5 * iqr
print("IQR bounds:", lower, upper)
```

## 6. Practical real-world applications
Summarize income, transaction size, exam scores, product demand and sensor measurements.

## 7. Common mistakes
Using mean for heavily skewed data without context; comparing standard deviations across different units; treating IQR fences as proof of erroneous outliers.

## 8. Practice questions
Compare mean and median under skew; calculate IQR; identify possible outliers; explain standard deviation.

## 9. Interview questions
When prefer median? What does IQR measure? Difference between population and sample variance?

## 10. Related functions and concepts
Probability, distributions, EDA, confidence intervals and robust statistics.
