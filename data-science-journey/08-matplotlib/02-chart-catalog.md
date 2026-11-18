# Matplotlib: Chart Catalog and When to Use Each Chart

## 1. Introduction and definition
Matplotlib supports many chart families. Select the chart based on variable type and analytical question.

## 2. Why we need this
Good chart selection makes patterns visible without misleading the reader.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``plot`` | Line chart: trend or ordered sequence. |
| ``scatter`` | Relationship between two numeric variables. |
| ``bar` / `barh`` | Compare categories. |
| ``hist`` | Show numeric distribution. |
| ``boxplot`` | Compare median, quartiles and outliers. |
| ``violinplot`` | Show distribution shape by group. |
| ``errorbar`` | Show estimates with uncertainty. |
| ``fill_between`` | Show ranges or areas. |
| ``stackplot`` | Show cumulative composition over an ordered axis. |
| ``pie`` | Show simple part-to-whole when few categories. |
| ``hexbin` / `hist2d`` | Show dense 2D distributions. |
| ``imshow`` | Display image or matrix data. |
| ``contour` / `contourf`` | Show level sets of a 2D surface. |
| ``eventplot`, `stem`, `step`` | Specialized discrete/event plots. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import matplotlib.pyplot as plt
fig, axes = plt.subplots(2, 2, figsize=(8, 6))
x = [1, 2, 3, 4]
axes[0, 0].plot(x, [2, 4, 3, 6]); axes[0, 0].set_title("Line")
axes[0, 1].bar(["A", "B", "C"], [4, 7, 5]); axes[0, 1].set_title("Bar")
axes[1, 0].hist([1, 2, 2, 3, 3, 3, 4], bins=4); axes[1, 0].set_title("Histogram")
axes[1, 1].scatter([1, 2, 3], [3, 2, 5]); axes[1, 1].set_title("Scatter")
plt.tight_layout(); plt.show()
```

## 5. Advanced examples
```python
# Error bars can communicate uncertainty around estimates.
fig, ax = plt.subplots()
ax.errorbar(["A", "B", "C"], [10, 13, 12], yerr=[1, 2, 1.5], fmt="o", capsize=4)
ax.set_ylabel("Mean value ± uncertainty")
plt.show()
```

## 6. Practical real-world applications
Choose a line chart for time trends, bar chart for category comparisons, histogram for distribution and scatter plot for numeric relationships.

## 7. Common mistakes
Using a pie chart for many categories; using a line chart for unordered categories; truncating bar axes without explanation; using 3D effects that obscure values.

## 8. Practice questions
Choose a chart for 10 scenarios; build a histogram and box plot for the same variable; show uncertainty with error bars.

## 9. Interview questions
When is a histogram better than a bar chart? What does a box plot summarize? How do error bars help?

## 10. Related functions and concepts
Seaborn chart families, visual encoding, statistical summaries and accessibility.
