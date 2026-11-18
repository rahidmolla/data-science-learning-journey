# Other Visualization: Bokeh and Interactive Apps

## 1. Introduction and definition
Bokeh creates interactive browser-based visualizations, from individual plots to linked selections and applications.

## 2. Why we need this
It is useful when a visualization needs custom browser interactions or integration with a Python server.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``figure`` | Create a plot. |
| ``p.line`, `p.circle`, `p.vbar`` | Add glyphs. |
| ``ColumnDataSource`` | Share structured data with glyphs. |
| ``HoverTool`` | Show tooltips. |
| ``output_file`, `show`` | Configure and display output. |
| ``save`` | Save a plot. |
| ``column`, `row`, `gridplot`` | Compose layouts. |
| ``Select`, `Slider`` | Add widgets. |
| ``CustomJS`` | Add browser-side JavaScript callbacks. |
| ``bokeh serve`` | Run a Bokeh server app. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
from bokeh.plotting import figure, show
from bokeh.models import ColumnDataSource, HoverTool
source = ColumnDataSource(data={"x": [1, 2, 3], "y": [4, 2, 5]})
p = figure(title="Interactive points", tools="pan,wheel_zoom,reset")
p.circle("x", "y", source=source, size=12)
p.add_tools(HoverTool(tooltips=[("x", "@x"), ("y", "@y")]))
show(p)
```

## 5. Advanced examples
```python
# Add a slider or selection widget for a richer app.
# For production, validate inputs and control the amount of data sent to the browser.
```

## 6. Practical real-world applications
Build custom interactive visual analytics, linked plots and browser-based data exploration.

## 7. Common mistakes
Sending millions of raw points to the browser; exposing untrusted HTML/JavaScript; forgetting Bokeh server deployment requirements.

## 8. Practice questions
Create a plot with hover; arrange two plots; add a slider to control a parameter.

## 9. Interview questions
What is a glyph? What does ColumnDataSource do? Difference between standalone output and Bokeh server?

## 10. Related functions and concepts
Altair, Plotly, dashboards and browser performance.
