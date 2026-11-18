# Other Visualization: Altair and Vega-Lite

## 1. Introduction and definition
Altair is a declarative statistical visualization library. You describe data, encodings and marks; the Vega-Lite system specifies rendering.

## 2. Why we need this
Declarative grammar can make chart intent concise, consistent and easy to compose.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``alt.Chart`` | Start a chart from a DataFrame. |
| ``.mark_point`, `.mark_line`, `.mark_bar`` | Choose visual mark. |
| ``.encode`` | Map data fields to visual channels. |
| ``alt.X`, `alt.Y`` | Configure axes and data types. |
| ``.properties`` | Set title, size and metadata. |
| ``.facet`` | Create small multiples. |
| ``.transform_filter`` | Filter data in the chart specification. |
| ``.transform_aggregate`` | Aggregate data. |
| ``.interactive`` | Enable interactive navigation. |
| ``.save`` | Export supported chart specifications. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import altair as alt
import pandas as pd
df = pd.DataFrame({"month": ["Jan", "Feb", "Mar"], "sales": [10, 15, 12]})
chart = alt.Chart(df).mark_line(point=True).encode(
    x="month:N", y="sales:Q", tooltip=["month", "sales"]
).properties(title="Monthly sales")
chart
```

## 5. Advanced examples
```python
chart = alt.Chart(df).mark_bar().encode(
    x=alt.X("month:N", sort=None),
    y=alt.Y("sales:Q", title="Sales"),
    color="month:N"
).interactive()
chart
```

## 6. Practical real-world applications
Build concise statistical charts, layered views and interactive small multiples.

## 7. Common mistakes
Mislabeling quantitative and nominal types; hitting default row limits in notebook renderers; assuming a chart object is a Matplotlib Figure.

## 8. Practice questions
Create line/bar charts; add tooltips; facet by a category; export an HTML chart.

## 9. Interview questions
What is a declarative chart grammar? What do `N` and `Q` mean in encodings?

## 10. Related functions and concepts
Vega-Lite, Plotly Express, chart grammar and interactive visualization.
