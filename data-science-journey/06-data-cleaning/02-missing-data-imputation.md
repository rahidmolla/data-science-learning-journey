# Data Cleaning: Missing Data and Imputation

## 1. Introduction and definition
Missing-data handling identifies where values are absent and chooses whether to retain, remove or estimate them.

## 2. Why we need this
Missingness can bias results; the right treatment depends on why data is missing and the analysis objective.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| `MCAR` | Missingness unrelated to observed or unobserved values. |
| `MAR` | Missingness explained by observed variables. |
| `MNAR` | Missingness depends on unobserved value itself. |
| ``dropna`` | Remove rows/columns under a documented rule. |
| ``fillna`` | Fill with constant or statistic. |
| `Median/mode imputation` | Simple baseline for numeric/categorical fields. |
| `Forward/back fill` | Propagate nearby time-series values. |
| `Interpolation` | Estimate intermediate values. |
| `Missingness indicator` | Add a flag indicating original missingness. |
| ``SimpleImputer`` | Scikit-learn transformer for train-fitted imputation. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import pandas as pd
df = pd.DataFrame({"age": [20, None, 40], "city": ["A", "B", None]})
df["age_missing"] = df["age"].isna()
df["age"] = df["age"].fillna(df["age"].median())
df["city"] = df["city"].fillna(df["city"].mode().iloc[0])
print(df)
```

## 5. Advanced examples
```python
from sklearn.impute import SimpleImputer
import numpy as np
imputer = SimpleImputer(strategy="median", add_indicator=True)
X = np.array([[10.], [np.nan], [30.]])
print(imputer.fit_transform(X))
```

## 6. Practical real-world applications
Prepare customer and sensor datasets while retaining information about missingness.

## 7. Common mistakes
Fitting imputation statistics on the full dataset before train/test split; imputing every column with mean; ignoring MNAR mechanisms; using forward-fill across entities.

## 8. Practice questions
Compare row deletion vs median imputation; create missingness flags; design a time-series fill rule.

## 9. Interview questions
What are MCAR, MAR and MNAR? Why fit imputer on training data only?

## 10. Related functions and concepts
Data leakage, preprocessing pipelines, outliers and data quality.
