# EDA: Reporting, Insight Writing and Storytelling

## 1. Introduction and definition
An EDA report turns analysis into a clear sequence of questions, evidence, interpretations and recommendations.

## 2. Why we need this
Decision-makers need meaning and limitations, not a gallery of disconnected charts.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| `Question` | State what decision or uncertainty is being explored. |
| `Metric` | Define numerator, denominator, unit and time window. |
| `Evidence` | Show a relevant summary or chart. |
| `Interpretation` | Explain the pattern without overstating causality. |
| `Caveat` | Mention sample, missingness, bias and data limits. |
| `Recommendation` | Suggest an action proportionate to evidence. |
| `Reproducibility` | Keep code, sources and environment. |
| `Executive summary` | Communicate the most important findings first. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
# Example insight structure
insight = {
    "question": "Which channel has the highest average order value?",
    "evidence": "Channel A: 42; Channel B: 35 (currency units).",
    "interpretation": "Channel A has the higher observed mean in this sample.",
    "caveat": "Sample size and acquisition costs have not been compared.",
    "next_step": "Compare confidence intervals and contribution margin."
}
print(insight)
```

## 5. Advanced examples
```python
# A chart should answer one question.
# Include title, units, source, date range and a concise takeaway.

```

## 6. Practical real-world applications
Produce stakeholder-ready analysis, portfolio case studies and business recommendations.

## 7. Common mistakes
Writing 'sales increased because of campaign' from correlation alone; omitting denominators; using decorative charts; hiding limitations.

## 8. Practice questions
Write five insights from a dataset; turn a chart into a headline; add one caveat and one actionable next step.

## 9. Interview questions
What makes an insight actionable? How do you avoid causal overclaiming? What belongs in an executive summary?

## 10. Related functions and concepts
EDA, data visualization, business metrics and communication.
