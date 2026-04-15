# Robustness tests

Robustness answers: **does the generator keep working when conditions change?**

## Stressors we test (examples)
- **External shift scenarios**: vary external cohort shifts and observe diagnostic + gating behavior
- **Rare events / low-event regimes**: observe stability of estimation artifacts and decision outcomes
- **Missingness + dropout stress**: alter longitudinal missingness/dropout and observe downstream stability
- **Multi-external settings**: pairwise gating behavior when multiple external cohorts exist
- **Temporal/visit schedule stress**: vary ctDNA schedules and irregularity patterns (public-safe)

## What we report
- which stressors were applied
- where performance/utility degrades
- remediation actions (e.g., additional constraints, revised configuration)

!!! note "Why robustness matters for health data"
    Health data pipelines vary widely across sites; robustness is often more informative than a single “best-case” benchmark.
