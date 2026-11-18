# Other Visualization: Streamlit Dashboards and Choosing a Chart

## 1. Introduction and definition
Streamlit turns Python scripts into interactive data apps. A dashboard combines metrics, controls, charts and explanations around a user task.

## 2. Why we need this
A dashboard helps people explore a dataset without editing code, but should answer a defined question rather than display every available chart.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``st.title`, `st.header`, `st.caption`` | Structure the app. |
| ``st.dataframe`, `st.table`` | Display tabular data. |
| ``st.metric`` | Show a key metric. |
| ``st.selectbox`, `st.multiselect`, `st.slider`` | Collect user selections. |
| ``st.pyplot`, `st.plotly_chart`, `st.altair_chart`` | Render charts. |
| ``st.cache_data`` | Cache data computations. |
| ``st.file_uploader`` | Accept user-uploaded files. |
| ``st.sidebar`` | Place controls in a sidebar. |
| ``st.tabs`, `st.columns`` | Organize layout. |
| ``streamlit run app.py`` | Launch the app locally. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import streamlit as st
import pandas as pd
st.title("Sales explorer")
uploaded = st.file_uploader("Upload a CSV", type="csv")
if uploaded:
    df = pd.read_csv(uploaded)
    st.metric("Rows", len(df))
    st.dataframe(df.head())

```

## 5. Advanced examples
```python
# Good dashboard pattern:
# 1. Define audience and decision.
# 2. Put key metric and date range first.
# 3. Add filters that change visible results.
# 4. Explain definitions and caveats.
# 5. Keep raw data access and privacy in mind.
```

## 6. Practical real-world applications
Build an interactive sales, sports analytics or operations dashboard for a portfolio project.

## 7. Common mistakes
Too many controls; expensive recomputation without caching; showing metrics without definitions; exposing sensitive data in a public app.

## 8. Practice questions
Build a CSV explorer; add date/category filters; display three KPIs and two charts; write an app README.

## 9. Interview questions
What makes a dashboard useful? What does `st.cache_data` do? How do you avoid misleading KPI cards?

## 10. Related functions and concepts
Plotly, Altair, Bokeh, EDA, user experience and deployment.
