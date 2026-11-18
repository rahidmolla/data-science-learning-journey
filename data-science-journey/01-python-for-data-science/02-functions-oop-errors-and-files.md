# Functions, OOP, Exceptions and Files

## 1. Introduction and definition
Functions package reusable logic; classes model objects with state and behavior; exceptions make failures explicit; file handling persists data.

## 2. Why we need this
Data workflows often need reusable cleaning functions, API clients, validation objects and safe file IO.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``def` / `return`` | Define a function and return a result. |
| ``*args`, `**kwargs`` | Accept variable positional and keyword arguments. |
| ``lambda`` | Create a small anonymous function. |
| ``@dataclass`` | Generate common data-container methods. |
| ``try/except/else/finally`` | Handle errors and cleanup reliably. |
| ``open` / `with`` | Read and write files while closing them safely. |
| ``json.load`, `json.dump`` | Read/write JSON files. |
| ``json.loads`, `json.dumps`` | Parse/serialize JSON strings. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
def clean_name(value):
    return str(value).strip().title()

print(clean_name("  ada lovelace "))  # Ada Lovelace
```

## 5. Advanced examples
```python
import json
record = {"name": "Asha", "score": 91}
with open("student.json", "w", encoding="utf-8") as file:
    json.dump(record, file, indent=2)

with open("student.json", encoding="utf-8") as file:
    loaded = json.load(file)
print(loaded["score"])  # 91
```

## 6. Practical real-world applications
Build reusable cleaners, data validators, file converters and small command-line data tools.

## 7. Common mistakes
Opening files without `with`; catching every exception and hiding the cause; confusing JSON text with a Python dictionary; using mutable class-level state unintentionally.

## 8. Practice questions
Write a CSV-to-JSON converter; create a `Student` dataclass; validate a record and raise a meaningful `ValueError`.

## 9. Interview questions
What is serialization? Why use context managers? Explain inheritance vs composition. What is the purpose of `finally`?

## 10. Related functions and concepts
Modules, packages, pathlib, CSV, JSON, logging, unit tests and type hints.
