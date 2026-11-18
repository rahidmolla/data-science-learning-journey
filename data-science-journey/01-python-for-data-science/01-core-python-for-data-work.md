# Python Core for Data Science

## 1. Introduction and definition
Python is the language used to load, transform, analyze and automate data workflows. This lesson reviews the language features that appear repeatedly in data tasks.

## 2. Why we need this
Good Python fundamentals make analysis reproducible, readable and easier to debug.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``type`, `isinstance`` | Inspect object types and type relationships. |
| ``len`, `range`, `enumerate`` | Count items, generate ranges and loop with indexes. |
| ``zip`` | Iterate over multiple iterables together. |
| ``sorted`, `reversed`` | Return sorted or reversed iterators/sequences. |
| ``any`, `all`` | Test whether any or all values are truthy. |
| ``sum`, `min`, `max`` | Aggregate built-in iterables. |
| ``map`, `filter`` | Transform or filter iterables; comprehensions are often clearer. |
| ``dict.get`, `setdefault`` | Safely access or initialize dictionary values. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
values = [12, 8, 20, 15]
print(len(values))       # 4
print(sum(values))       # 55
print(max(values))       # 20
print(list(enumerate(values, start=1)))
```

## 5. Advanced examples
```python
records = [{"team": "A", "runs": 12}, {"team": "B", "runs": 20}]
by_runs = sorted(records, key=lambda row: row["runs"], reverse=True)
print(by_runs[0]["team"])  # B
```

## 6. Practical real-world applications
Use dictionaries for records, functions for reusable transformations, comprehensions for concise transformations, and exceptions to handle malformed files or API responses.

## 7. Common mistakes
Mutating a list while iterating over it; confusing `==` with `is`; using a mutable default argument; assuming dictionary order implies sorted order; swallowing exceptions without logging.

## 8. Practice questions
Write a function that returns min, max and mean; count category frequencies; safely parse numeric strings; flatten a list of lists.

## 9. Interview questions
What is the difference between a list and tuple? What does `enumerate` return? When should a generator be used? Explain shallow vs deep copy.

## 10. Related functions and concepts
Functions, comprehensions, iterators, generators, dictionaries, sets, exceptions, modules and file handling.
