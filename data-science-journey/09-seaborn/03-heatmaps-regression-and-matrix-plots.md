# Seaborn: Heatmaps, Regression and Matrix Plots

## 1. Introduction and definition
Seaborn offers matrix visualizations and regression-oriented charts for correlation, clustering and relationships.

## 2. Why we need this
They reveal patterns across many variables and help investigate associations.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``heatmap`` | Visualize a matrix using color. |
| ``clustermap`` | Cluster rows and columns and display a heatmap. |
| ``regplot`` | Scatter plot with fitted regression model. |
| ``lmplot`` | Figure-level regression interface with facets. |
| ``residplot`` | Plot residuals against a predictor. |
| ``PairGrid`` | Custom pairwise variable grid. |
| ``FacetGrid`` | Condition plots on subsets. |
| ``regplot` options` | Use `order`, `logistic`, `robust`, `lowess` where appropriate. |
| ``annot` in heatmap` | Display matrix values. |
| ``mask` in heatmap` | Hide selected matrix cells. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import seaborn as sns
import matplotlib.pyplot as plt
penguins = sns.load_dataset("penguins").dropna()
corr = penguins.select_dtypes("number").corr()
sns.heatmap(corr, annot=True, center=0, cmap="vlag")
plt.show()
```

## 5. Advanced examples
```python
sns.lmplot(data=penguins, x="flipper_length_mm", y="body_mass_g",
           hue="species", col="sex", scatter_kws={"alpha": .5})
plt.show()
```

## 6. Practical real-world applications
Inspect feature relationships, compare correlation structure and examine whether a simple trend fits the data.

## 7. Common mistakes
Treating correlation heatmap as causality; using regression line without checking assumptions; clustering mixed scales without considering standardization.

## 8. Practice questions
Create a masked upper-triangle correlation heatmap; compare species relationships; inspect residual patterns.

## 9. Interview questions
What does a correlation heatmap show? When can clustermap help? Why inspect residuals?

## 10. Related functions and concepts
Correlation, regression, Matplotlib, EDA and multivariate analysis.
