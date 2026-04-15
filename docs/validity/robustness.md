# Robustness tests

Robustness answers: **does the generator keep working when conditions change?**

## Stressors we test (examples)
- **Cohort shift**: generate for different subpopulations and compare quality slice-wise
- **Rare event emphasis**: focus evaluation on low-prevalence outcomes/variables
- **Missingness stress**: increase/decrease missingness and validate stability
- **Schema variation**: add/remove columns, change categorical cardinalities
- **Temporal stress**: varying window lengths and sampling frequency

## What we report
- which stressors were applied
- where performance/utility degrades
- remediation actions (e.g., additional constraints, revised configuration)

!!! note "Why robustness matters for health data"
    Health data pipelines vary widely across sites; robustness is often more informative than a single “best-case” benchmark.
