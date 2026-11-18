# Seaborn: Categorical and Relational Plots

## 1. Introduction and definition
Categorical plots compare distributions or estimates across groups; relational plots show how numeric variables vary together.

## 2. Why we need this
These charts are central to exploratory analysis of business and scientific datasets.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``scatterplot`` | Show relationship between two numeric variables. |
| ``lineplot`` | Show ordered trends with optional estimator/uncertainty. |
| ``relplot`` | Figure-level relational interface with facets. |
| ``barplot`` | Show an estimate and uncertainty by category. |
| ``countplot`` | Count observations by category. |
| ``boxplot`` | Show quartiles and potential outliers. |
| ``violinplot`` | Show distribution density by category. |
| ``stripplot`, `swarmplot`` | Show individual observations. |
| ``pointplot`` | Show point estimates and intervals. |
| ``catplot`` | Figure-level categorical interface. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import seaborn as sns
import matplotlib.pyplot as plt
tips = sns.load_dataset("tips")
sns.boxplot(data=tips, x="day", y="total_bill", hue="sex")
plt.show()
```

## 5. Advanced examples
```python
sns.relplot(data=tips, x="total_bill", y="tip", hue="time",
             col="smoker", kind="scatter")
sns.catplot(data=tips, x="day", y="total_bill", kind="violin", inner="quartile")
plt.show()
```

## 6. Practical real-world applications
Compare sales across regions, understand tip behavior by day, and explore customer groups.

## 7. Common mistakes
Confusing barplot's estimator with raw counts; overlapping points; interpreting confidence intervals as spread of individual observations; using too many hue categories.

## 8. Practice questions
Compare countplot and barplot; choose box vs violin; facet a scatterplot by category.

## 9. Interview questions
What does `estimator` do in barplot? Difference between box and violin plots? What is faceting?

## 10. Related functions and concepts
Distributions, relational plots, confidence intervals and EDA.
