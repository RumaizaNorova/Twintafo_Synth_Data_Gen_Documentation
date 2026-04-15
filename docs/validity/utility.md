# Utility tests

Utility answers: **can the synthetic data support the analyses we care about?**

## Statistical similarity (examples)
- **Univariate**: distribution distance per feature (continuous + categorical)
- **Bivariate**: association preservation (correlations, contingency structure)
- **Stratified**: repeat metrics within cohorts (age bands, diagnosis groups, etc.)

## Downstream task utility (examples)
We compare models trained/evaluated on real vs synthetic data for tasks like:
- risk prediction / classification
- regression tasks (length of stay proxies, costs)
- time-to-event or sequence forecasting (when applicable)

We report:
- performance deltas (aggregate)
- calibration changes (aggregate)
- cohort stability (slice-wise)

## Acceptance criteria
Utility is application-specific; we document:
- target thresholds
- known caveats (where synthesis is weaker)
- intended safe uses vs non-recommended uses

!!! tip "Public-safe artifacts"
    Utility can often be shown without leaking sensitive data by sharing **aggregate distances**, **task-level metrics**, and **plots without raw points**.
