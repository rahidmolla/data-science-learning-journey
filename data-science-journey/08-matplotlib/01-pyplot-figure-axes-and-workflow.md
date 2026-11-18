# Matplotlib: Pyplot, Figure, Axes and the Plotting Workflow

## 1. Introduction and definition
Matplotlib is a foundational Python plotting library. A Figure is the overall canvas; an Axes is an individual plotting area.

## 2. Why we need this
It provides fine-grained control over static charts, publication figures and multi-panel layouts.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``plt.subplots`` | Create a Figure and one or more Axes. |
| ``ax.plot`` | Draw line plots. |
| ``ax.scatter`` | Draw scatter plots. |
| ``ax.bar`, `ax.barh`` | Vertical and horizontal bars. |
| ``ax.hist`` | Draw histograms. |
| ``ax.set_title`, `set_xlabel`, `set_ylabel`` | Add chart text. |
| ``ax.legend`, `ax.grid`` | Add legend and grid. |
| ``plt.tight_layout`, `constrained_layout`` | Improve spacing. |
| ``fig.savefig`` | Save a figure. |
| ``plt.show`, `plt.close`` | Display or close figures. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import matplotlib.pyplot as plt
months = ["Jan", "Feb", "Mar"]
sales = [12, 18, 15]
fig, ax = plt.subplots()
ax.plot(months, sales, marker="o", label="Sales")
ax.set(title="Monthly sales", xlabel="Month", ylabel="Units")
ax.legend()
plt.show()
```

## 5. Advanced examples
```python
fig, axes = plt.subplots(1, 2, figsize=(9, 3), constrained_layout=True)
axes[0].bar(months, sales)
axes[0].set_title("Sales by month")
axes[1].plot(months, sales, marker="o")
axes[1].set_title("Sales trend")
fig.savefig("sales.png", dpi=160, bbox_inches="tight")
```

## 6. Practical real-world applications
Create reports, scientific plots, chart grids and custom visualizations with explicit layout and styling.

## 7. Common mistakes
Mixing pyplot state and object-oriented APIs in complex figures; forgetting labels/units; saving before layout adjustment; not closing figures in batch jobs.

## 8. Practice questions
Create line and bar charts; make a 2x2 subplot grid; save a high-resolution PNG.

## 9. Interview questions
Difference between Figure and Axes? Why use `subplots`? What does dpi mean?

## 10. Related functions and concepts
Chart types, styling, annotations, Seaborn and Plotly.
