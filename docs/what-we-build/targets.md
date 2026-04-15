# Target data & constraints

This page documents the **design targets** we use when configuring a generator for a specific health dataset.

## Typical constraints
- **Value constraints**: valid ranges, allowed categories, code systems (where applicable).
- **Structural constraints**: keys, uniqueness, parent/child relationships between tables.
- **Temporal constraints**: ordering rules, time windows, plausible intervals between events.
- **Missingness constraints**: mechanisms and rates (MCAR/MAR-inspired approximations where useful).

## Quality targets (examples)
We define a target set like:
- Distribution similarity thresholds (per-feature, per-cohort)
- Correlation/association targets (pairwise, conditional)
- Time series pattern targets (trend/seasonality, event-time distributions)

!!! tip "How to use this page"
    Treat this as a checklist for documenting a release or benchmark run: what schema you targeted, what constraints you enforced, and which quality targets you reported.
