# Data Preprocessing: Scaling, Encoding and Transformations

## 1. Introduction and definition
Feature transformations change numerical scales or represent categories in a form suitable for downstream algorithms.

## 2. Why we need this
Some algorithms are sensitive to scale and require numeric input; transformation can also reduce skew.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``StandardScaler`` | Center to mean zero and scale to unit variance. |
| ``MinMaxScaler`` | Scale to a chosen range. |
| ``RobustScaler`` | Scale using median and quantile range. |
| ``Normalizer`` | Normalize each sample vector. |
| ``OneHotEncoder`` | Create indicator columns for categories. |
| ``OrdinalEncoder`` | Encode categories with integer codes where order is meaningful. |
| ``PowerTransformer`` | Apply power transform to stabilize variance / reduce skew. |
| ``QuantileTransformer`` | Map features to a target distribution. |
| `Log transform` | Compress positive right-skewed values; handle zeros/negatives deliberately. |
| `Feature extraction` | Derive useful variables from dates, text or domain fields. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
from sklearn.preprocessing import StandardScaler, OneHotEncoder
import numpy as np
X = np.array([[10.], [20.], [30.]])
print(StandardScaler().fit_transform(X).round(2))
```

## 5. Advanced examples
```python
from sklearn.compose import ColumnTransformer
from sklearn.preprocessing import OneHotEncoder, StandardScaler
from sklearn.pipeline import Pipeline
from sklearn.impute import SimpleImputer
numeric_pipe = Pipeline([("impute", SimpleImputer(strategy="median")),
                         ("scale", StandardScaler())])
preprocessor = ColumnTransformer([
    ("num", numeric_pipe, ["age", "income"]),
    ("cat", OneHotEncoder(handle_unknown="ignore"), ["city"])
])
```

## 6. Practical real-world applications
Prepare mixed numeric/categorical customer features for models and compare robust scaling for skewed data.

## 7. Common mistakes
Scaling before train/test split; ordinal-encoding nominal categories; assuming scaling removes outliers; forgetting unknown categories at inference.

## 8. Practice questions
Compare StandardScaler and MinMaxScaler; encode a city column; choose a transform for income data.

## 9. Interview questions
When does scaling matter? Difference between one-hot and ordinal encoding? Why use `handle_unknown`?

## 10. Related functions and concepts
Pipelines, feature engineering, missing data, model validation and leakage.
