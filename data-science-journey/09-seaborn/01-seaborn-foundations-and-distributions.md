# Seaborn: Foundations and Distribution Plots

## 1. Introduction and definition
Seaborn is a statistical visualization library built on Matplotlib with concise APIs, pandas integration and attractive defaults.

## 2. Why we need this
It speeds up common statistical charts and makes grouping by categorical variables straightforward.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``sns.set_theme`` | Set global theme and context. |
| ``histplot`` | Histogram, optionally with KDE. |
| ``kdeplot`` | Kernel density estimate. |
| ``ecdfplot`` | Empirical cumulative distribution. |
| ``rugplot`` | Show individual observations along an axis. |
| ``displot`` | Figure-level distribution interface. |
| ``jointplot`` | Bivariate plot with marginal distributions. |
| ``pairplot`` | Pairwise relationships across variables. |
| ``FacetGrid`` | Create a grid of conditional plots. |
| ``JointGrid`` | Build custom joint and marginal charts. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import seaborn as sns
import matplotlib.pyplot as plt
tips = sns.load_dataset("tips")
sns.histplot(data=tips, x="total_bill", bins=20, kde=True)
plt.title("Distribution of total bill")
plt.show()
```

## 5. Advanced examples
```python
sns.displot(data=tips, x="total_bill", hue="time", kind="kde", fill=True)
sns.pairplot(data=tips, vars=["total_bill", "tip", "size"], hue="time")
plt.show()
```

## 6. Practical real-world applications
Explore distributions, compare groups and inspect relationships among numeric variables.

## 7. Common mistakes
Comparing KDEs with very different sample sizes without context; treating KDE bandwidth as objective truth; plotting too many pairplot dimensions.

## 8. Practice questions
Compare histogram and ECDF; plot distributions by category; create a pairplot for three numeric features.

## 9. Interview questions
What is KDE? Difference between axes-level and figure-level functions? What does `hue` do?

## 10. Related functions and concepts
Matplotlib, EDA, distributions, categorical plots and faceting.
