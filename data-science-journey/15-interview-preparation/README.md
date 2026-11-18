# Data Science Foundations Interview Preparation

## Python
- List vs tuple vs set vs dictionary
- Mutable vs immutable objects
- Shallow vs deep copy
- Iterators vs generators
- Exceptions and context managers
- JSON serialization and API error handling

## NumPy
- ndarray vs Python list
- Shape, axis and dtype
- Views vs copies
- Broadcasting rules
- Vectorization and ufuncs
- `reshape` vs `ravel` vs `flatten`
- `argsort` vs `sort`
- `default_rng` and reproducibility
- NaN behavior and `nan*` functions

## pandas
- Series vs DataFrame
- `loc` vs `iloc`
- `count` vs `size`
- `merge` vs `concat` vs `join`
- `agg` vs `transform` vs `apply`
- `pivot` vs `pivot_table` vs `melt`
- `isna` vs `notna`
- `drop_duplicates` and business keys
- `axis=0` vs `axis=1`
- `groupby` split-apply-combine

## Statistics
- Mean vs median
- Variance vs standard deviation
- Population vs sample
- Correlation vs causation
- p-value and confidence interval
- Type I/II errors and power
- Sampling bias and confounding

## Visualization
- Histogram vs bar chart
- Box vs violin plot
- Line vs scatter plot
- Matplotlib Figure vs Axes
- Seaborn axes-level vs figure-level
- Plotly Express vs Graph Objects
- Choropleth vs point map
- Accessibility and misleading axes

## Data quality and preprocessing
- MCAR vs MAR vs MNAR
- Missing-value strategies
- Outlier investigation
- Data leakage
- Train/test split
- Scaling and encoding
- Why fit preprocessing only on training data

## Case-study answer structure
1. Clarify the decision/question.
2. Define metrics and population.
3. Inspect source, schema and quality.
4. Clean with documented rules.
5. Explore distributions and relationships.
6. Select visuals that answer the question.
7. Quantify uncertainty and limitations.
8. Recommend next action and validation.
