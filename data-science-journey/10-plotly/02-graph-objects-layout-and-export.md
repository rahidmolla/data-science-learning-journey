# Plotly: Graph Objects, Layout, Traces and Export

## 1. Introduction and definition
Plotly Graph Objects provide lower-level control over figures, traces, axes, annotations and layout.

## 2. Why we need this
Use Graph Objects when a high-level Express chart needs custom traces, complex layering or precise layout control.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``go.Figure`` | Create or manage a figure. |
| ``go.Scatter`, `go.Bar`, `go.Histogram`` | Create trace objects. |
| ``.add_trace`` | Add a trace. |
| ``.update_layout`` | Set titles, dimensions, legend and theme. |
| ``.update_xaxes`, `.update_yaxes`` | Configure axes. |
| ``.add_annotation`` | Add text annotation. |
| ``.add_shape`` | Add reference line/shape. |
| ``.update_traces`` | Update trace properties. |
| ``.show`` | Render figure. |
| ``.write_html`, `.write_image`` | Export interactive HTML or static image (image export may require Kaleido). |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import plotly.graph_objects as go
fig = go.Figure()
fig.add_trace(go.Bar(x=["A", "B"], y=[10, 15], name="Revenue"))
fig.update_layout(title="Revenue by segment", yaxis_title="Revenue")
fig.show()
```

## 5. Advanced examples
```python
fig.add_trace(go.Scatter(x=[1, 2, 3], y=[2, 4, 3],
                          mode="lines+markers", name="Trend"))
fig.add_hline(y=3, line_dash="dash", annotation_text="Target")
fig.write_html("interactive_report.html")
```

## 6. Practical real-world applications
Create custom dashboards, combine chart layers and export interactive reports.

## 7. Common mistakes
Overusing multiple y-axes; failing to label traces; expecting static image export without the required engine; embedding sensitive data in public HTML.

## 8. Practice questions
Combine bar and line traces; add a target line; export a standalone HTML file.

## 9. Interview questions
When choose Graph Objects over Express? What is a trace? Difference between `write_html` and `write_image`?

## 10. Related functions and concepts
Plotly Express, Dash/Streamlit, chart layout and interactive reporting.
