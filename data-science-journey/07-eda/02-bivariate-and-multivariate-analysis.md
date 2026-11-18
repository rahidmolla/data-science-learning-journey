# EDA: Bivariate and Multivariate Analysis

## 1. Introduction and definition
Bivariate analysis studies two variables; multivariate analysis examines several variables together.

## 2. Why we need this
It helps identify relationships, segments, interactions and possible confounding patterns.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| `Scatter plot` | Relationship between two numeric variables. |
| `Correlation matrix` | Pairwise numeric association. |
| `Grouped summary` | Compare metrics across categories. |
| `Box/violin plot` | Compare distributions across groups. |
| `Pair plot` | Visualize pairwise relationships across several numeric features. |
| `Heatmap` | Encode a matrix with color. |
| `Crosstab` | Summarize categorical combinations. |
| `Faceting` | Repeat a chart across subgroups. |
| `Bubble chart` | Add a third numeric variable using size. |
| `Parallel coordinates` | Compare many dimensions across observations. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import seaborn as sns
import matplotlib.pyplot as plt
tips = sns.load_dataset("tips")
sns.scatterplot(data=tips, x="total_bill", y="tip", hue="time")
plt.show()
```

## 5. Advanced examples
```python
corr = tips.select_dtypes("number").corr()
sns.heatmap(corr, annot=True, cmap="vlag", center=0)
plt.show()
```

## 6. Practical real-world applications
Compare sales by region and channel, study relationships between spend and revenue, and segment customers.

## 7. Common mistakes
Assuming correlation means causation; using too many colors; overplotting dense data; comparing groups with very different sample sizes without context.

## 8. Practice questions
Create a correlation heatmap; compare a metric across categories; investigate a confounder; write three evidence-based insights.

## 9. Interview questions
What is multicollinearity? What can a heatmap reveal? Why can aggregation hide variation?

## 10. Related functions and concepts
Statistics, visualization, feature engineering and causal reasoning.
