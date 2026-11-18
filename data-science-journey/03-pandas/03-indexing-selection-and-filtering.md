# pandas: Indexing, Selection and Filtering

## 1. Introduction and definition
pandas provides label-based, position-based and boolean selection tools for rows and columns.

## 2. Why we need this
Correct selection is central to every analysis and helps avoid accidental data modification.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``.loc`` | Select by labels and label slices. |
| ``.iloc`` | Select by integer position. |
| ``.at`, `.iat`` | Fast scalar access by label or position. |
| `Boolean masks` | Filter rows using conditions. |
| ``.query`` | Filter with an expression string. |
| ``.isin`` | Membership filtering. |
| ``.between`` | Inclusive range test. |
| ``.filter`` | Select labels by name pattern/list. |
| ``.where`, `.mask`` | Keep or replace values conditionally. |
| ``.assign`` | Return a DataFrame with new or updated columns. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import pandas as pd
df = pd.DataFrame({"name": ["A", "B", "C"], "age": [20, 25, 19], "score": [70, 90, 85]})
print(df.loc[df["age"] >= 20, ["name", "score"]])
print(df.iloc[0:2, 0:2])
```

## 5. Advanced examples
```python
result = (df.query("age >= 20 and score >= 80")
            .assign(passed=lambda x: x["score"] >= 85)
            .sort_values(["score", "age"], ascending=[False, True]))
print(result)
```

## 6. Practical real-world applications
Filter customers by purchase behavior, select columns for a report and create derived flags.

## 7. Common mistakes
Using `and` instead of `&` for Series conditions; forgetting parentheses around conditions; mixing labels and positions; modifying a slice without `.loc`.

## 8. Practice questions
Select rows 1 and 3; filter scores between 70 and 90; select numeric columns; create a boolean pass column.

## 9. Interview questions
Difference between `loc` and `iloc`? Why are parentheses needed with `&`? What is chained assignment?

## 10. Related functions and concepts
Index alignment, sorting, conditional assignment and query optimization.
