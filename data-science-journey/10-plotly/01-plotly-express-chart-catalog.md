# Plotly Express: Interactive Chart Catalog

## 1. Introduction and definition
Plotly Express is a high-level API for creating interactive charts with concise function calls.

## 2. Why we need this
Interactive hover, zoom, pan and selection are useful for exploring large or detailed datasets.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``px.scatter`` | Interactive scatter plot. |
| ``px.line`` | Interactive line chart. |
| ``px.bar`` | Bar chart. |
| ``px.histogram`` | Histogram. |
| ``px.box`, `px.violin`` | Distribution comparisons. |
| ``px.strip`, `px.ecdf`` | Individual points and empirical CDF. |
| ``px.density_heatmap`, `px.density_contour`` | 2D density. |
| ``px.scatter_matrix`` | Pairwise relationships. |
| ``px.imshow`` | Display matrix/image. |
| ``px.area`, `px.pie`, `px.treemap`, `px.sunburst`` | Composition and hierarchy charts. |
| ``px.funnel`, `px.timeline`` | Funnel and timeline charts. |
| ``px.choropleth`, `px.scatter_geo`` | Geographic charts. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import plotly.express as px
df = px.data.iris()
fig = px.scatter(df, x="sepal_width", y="sepal_length",
                 color="species", hover_data=["petal_width"])
fig.show()
```

## 5. Advanced examples
```python
gap = px.data.gapminder().query("year == 2007")
fig = px.scatter(gap, x="gdpPercap", y="lifeExp", size="pop",
                 color="continent", hover_name="country",
                 log_x=True, size_max=55)
fig.show()
```

## 6. Practical real-world applications
Build exploratory interactive charts, share data stories and allow users to inspect individual observations.

## 7. Common mistakes
Using too many hover fields; hiding units; using pie charts with many categories; assuming a browser can display a figure without exporting HTML or using a supported renderer.

## 8. Practice questions
Build an interactive scatterplot; create a faceted histogram; map a country-level metric.

## 9. Interview questions
What is Plotly Express? What does hover_data do? Difference between `facet_col` and `color`?

## 10. Related functions and concepts
Graph Objects, dashboards, maps, HTML export and chart design.
