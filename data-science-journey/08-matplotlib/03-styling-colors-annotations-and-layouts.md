# Matplotlib: Styling, Colors, Annotations and Layouts

## 1. Introduction and definition
Matplotlib styling controls visual hierarchy, readability, color, axes, labels and multi-panel arrangement.

## 2. Why we need this
Readable visual design helps a chart communicate accurately in reports and presentations.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``plt.style.use`` | Apply a built-in style sheet. |
| ``rcParams`` | Set global plotting defaults. |
| ``color`, `cmap`` | Choose color or colormap. |
| ``annotate`, `text`` | Add explanatory labels. |
| ``axvline`, `axhline`` | Add reference lines. |
| ``set_xlim`, `set_ylim`` | Set visible ranges. |
| ``tick_params`, `set_xticks`` | Control tick appearance and positions. |
| ``twinx`, `twiny`` | Create a secondary axis when justified. |
| ``GridSpec`, `subplot_mosaic`` | Build custom layouts. |
| ``savefig`` | Export with format, dpi and bounding box. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import matplotlib.pyplot as plt
fig, ax = plt.subplots()
x = [1, 2, 3]
y = [2, 4, 3]
ax.plot(x, y, marker="o")
ax.annotate("Peak", xy=(2, 4), xytext=(2.2, 4.4),
            arrowprops={"arrowstyle": "->"})
ax.axhline(3, linestyle="--", label="Reference")
ax.legend()
plt.show()
```

## 5. Advanced examples
```python
plt.rcParams.update({"figure.figsize": (7, 4), "axes.grid": True})
fig, ax = plt.subplots(constrained_layout=True)
ax.bar(["North", "South"], [25, 31])
ax.set_ylabel("Revenue (thousands)")
fig.savefig("regional_revenue.png", dpi=200, bbox_inches="tight")
```

## 6. Practical real-world applications
Prepare consistent chart styles for notebooks, reports, presentations and dashboards.

## 7. Common mistakes
Using color alone to encode meaning; excessive annotations; dual axes that imply misleading relationships; unreadable tick labels.

## 8. Practice questions
Build a consistent chart theme; annotate a peak; export for a report; improve a crowded x-axis.

## 9. Interview questions
What is a colormap? When can a secondary axis mislead? Difference between `tight_layout` and constrained layout?

## 10. Related functions and concepts
Figure/Axes, chart catalog, accessibility and data storytelling.
