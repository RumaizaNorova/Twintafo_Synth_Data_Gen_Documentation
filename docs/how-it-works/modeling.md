# Modeling approach (statistical)

Our current public description emphasizes a **statistical (non-deep-learning) approach** suitable for constrained health data, where:
- schemas can be complex,
- missingness is informative,
- rare events matter,
- and interpretability/debuggability is useful.

## High-level idea
We aim to model:
- **marginals** (per-feature distributions),
- **dependencies** (associations between features),
- **constraints** (valid ranges, category sets, structural rules),
then sample from the learned representation and **repair** invalid outputs.

## Why statistical methods here
- **Constraint friendliness**: easier to incorporate hard rules and plausibility checks.
- **Data efficiency**: can behave well when data is limited or heavily sparse.
- **Auditability**: easier to explain failures and iterate with domain experts.

## What to look for in results
Good synthesis should preserve:
- stratified distributions (across cohorts),
- clinically meaningful associations (not just global correlations),
- tail behavior for rare but important variables.

!!! note "Boundaries"
    This page intentionally avoids implementation-grade detail (exact model families per column, conditioning structure, and tuning strategy).
