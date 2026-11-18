# Plotly: Animation, Facets, Maps and Dashboards

## 1. Introduction and definition
Plotly supports animation frames, small multiples, geographic plots and interactive application integration.

## 2. Why we need this
These capabilities help users explore changes over time, compare segments and interact with maps.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``animation_frame`` | Animate a chart over a variable. |
| ``animation_group`` | Keep entities consistent across frames. |
| ``facet_row`, `facet_col`` | Create small multiples. |
| ``px.choropleth`` | Color geographic regions. |
| ``px.scatter_map`` | Plot points on a map (API availability depends on Plotly version). |
| ``geo` layout` | Configure geographic projection. |
| ``frames`` | Define animation frames in Graph Objects. |
| `Dash` | Build Plotly web applications. |
| `Streamlit + Plotly` | Embed interactive figures in a Streamlit app. |
| ``write_html`` | Share a self-contained interactive chart. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import plotly.express as px
df = px.data.gapminder()
fig = px.scatter(df, x="gdpPercap", y="lifeExp", animation_frame="year",
                 animation_group="country", color="continent",
                 size="pop", hover_name="country", log_x=True)
fig.show()
```

## 5. Advanced examples
```python
# Facets make subgroup comparisons easier to scan.
iris = px.data.iris()
fig = px.scatter(iris, x="sepal_width", y="sepal_length",
                 color="species", facet_col="species")
fig.show()
```

## 6. Practical real-world applications
Create time-evolving population charts, interactive region comparisons and dashboards for stakeholders.

## 7. Common mistakes
Animating inconsistent scales; using maps without checking geographic identifiers; relying on a map token/API without documenting it; making a dashboard with no user question.

## 8. Practice questions
Animate a trend; facet by region; build a map from valid geographic fields; embed a chart in Streamlit.

## 9. Interview questions
What is a facet? What is an animation frame? When use a map rather than a bar chart?

## 10. Related functions and concepts
Plotly Express, Graph Objects, Folium, GeoPandas and dashboard design.
