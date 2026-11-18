# EDA: Workflow and Univariate Analysis

## 1. Introduction and definition
Exploratory Data Analysis uses summaries and visualizations to understand structure, quality, distributions and potential patterns.

## 2. Why we need this
EDA helps form questions and test whether assumptions are reasonable before modeling or reporting.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| `Dataset overview` | Shape, types, missingness and unique counts. |
| `Frequency table` | Counts of categorical values. |
| `Histogram` | Distribution of a numeric variable. |
| `KDE` | Smoothed estimate of a distribution. |
| `Box plot` | Median, quartiles and potential extreme values. |
| `ECDF` | Cumulative proportion at or below each value. |
| `Skewness` | Distribution asymmetry. |
| `Value counts` | Category frequency and proportions. |
| `Quantiles` | Position summaries. |
| `Data dictionary` | Meaning and units of fields. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import pandas as pd
import matplotlib.pyplot as plt
df = pd.DataFrame({"price": [10, 12, 12, 15, 20, 35]})
print(df["price"].describe())
df["price"].hist(bins=5)
plt.xlabel("Price"); plt.ylabel("Frequency"); plt.show()
```

## 5. Advanced examples
```python
# Compare center and spread robustly
summary = df["price"].agg(["mean", "median", "std", "min", "max"])
q = df["price"].quantile([.1, .25, .5, .75, .9])
print(summary, q)
```

## 6. Practical real-world applications
Understand customer spend, product price distributions, student scores and operational measurements.

## 7. Common mistakes
Plotting without units; selecting bins without considering scale; interpreting a histogram as exact probability; failing to note small sample size.

## 8. Practice questions
Profile a dataset; explain skew; compare mean/median; choose a histogram bin count and justify it.

## 9. Interview questions
What is univariate EDA? What does a box plot show? Why use ECDF?

## 10. Related functions and concepts
Descriptive statistics, missingness, chart selection and bivariate EDA.
