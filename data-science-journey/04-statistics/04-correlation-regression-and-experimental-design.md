# Correlation, Regression and Experimental Design

## 1. Introduction and definition
Correlation measures association; regression models relationships; experimental design helps identify causal effects through controlled assignment.

## 2. Why we need this
These tools help explore relationships while separating association from defensible causal conclusions.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| `Pearson correlation` | Linear association between numeric variables. |
| `Spearman correlation` | Rank-based monotonic association. |
| `Covariance` | Joint variation in original units. |
| `Simple linear regression` | Model outcome as intercept plus slope times predictor. |
| `Residuals` | Observed minus predicted values. |
| `R-squared` | Fraction of outcome variance explained in-sample under model definition. |
| `Confounding` | A third variable related to exposure and outcome. |
| `Random assignment` | Balances confounders in expectation. |
| `A/B test` | Randomized comparison of alternatives. |
| `Difference-in-differences` | Compare changes across treatment and control groups under assumptions. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import pandas as pd
df = pd.DataFrame({"ad_spend": [1, 2, 3, 4], "sales": [2, 3, 5, 6]})
print(df.corr(method="pearson"))
```

## 5. Advanced examples
```python
import statsmodels.api as sm
X = sm.add_constant(df["ad_spend"])
model = sm.OLS(df["sales"], X).fit()
print(model.params)
print(model.rsquared)
```

## 6. Practical real-world applications
Study relationships between marketing spend and sales, estimate demand trends and evaluate experiments.

## 7. Common mistakes
Treating correlation as causation; extrapolating outside observed data; ignoring residual patterns; using R-squared as the only measure of model quality.

## 8. Practice questions
Compare Pearson and Spearman; fit a simple regression; inspect residuals; identify confounders in a business scenario.

## 9. Interview questions
What does correlation measure? What does a slope mean? Why randomize an experiment?

## 10. Related functions and concepts
EDA, hypothesis tests, causal inference, feature engineering and machine learning.
