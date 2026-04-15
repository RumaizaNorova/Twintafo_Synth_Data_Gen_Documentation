# What we build

Twintafo produces **synthetic health datasets** intended to be *structurally compatible* with real-world analytics workflows while avoiding exposure of sensitive underlying data.

## Outputs (typical)
- **Tabular**: patient-level or encounter-level tables (one row per entity/event).
- **Time series**: sequences such as vitals, labs, visits, medication fills, or utilization over time.

## What we optimize for
- **Schema fidelity**: columns, types, value ranges, and constraints remain realistic.
- **Relationship fidelity**: clinically meaningful relationships (e.g., comorbidity patterns, co-medication rates) are preserved where feasible.
- **Operational realism**: missingness patterns, censoring, and event sparsity resemble real systems.

## Non-goals / explicit exclusions
We do not aim to:
- reproduce any real individual’s record,
- generate direct identifiers,
- provide “drop-in clinical truth” for patient care decisions.

## Evidence artifacts we can share publicly
Depending on dataset sensitivity and partner constraints, we can provide:
- **Aggregate similarity dashboards** (distributions, correlations, stratified slices)
- **Downstream task performance** comparisons (on agreed benchmark tasks)
- **Stress/robustness** results (schema changes, missingness, cohort shifts)
