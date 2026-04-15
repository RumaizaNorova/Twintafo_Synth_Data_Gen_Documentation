# Transportability diagnostics & gating

The pipeline includes an explicit **transportability step**:
1) compute diagnostic summaries comparing **internal** vs **external** cohorts  
2) apply **deterministic gating** to decide whether external data can be borrowed

## Diagnostics (public view)
We compute reviewer-oriented summaries such as:
- **Balance**: numeric and categorical balance tables (e.g., standardized differences and proportion deltas)
- **Overlap**: overlap proxies summarizing whether external covariate support aligns with internal support
- (Optional) **Propensity overlap summary**: a simple overlap check based on predicted cohort membership

These diagnostics are exported as a machine-readable artifact and are included in the run report.

## Gating decision (public view)
Gating produces:
- **pass/fail**
- **reason strings** (why the run passed/failed)
- **summary scores** derived from diagnostic summaries

Gating is intentionally deterministic so it can be:
- tested under operating characteristics runs
- audited in evidence packs
- reviewed consistently across scenarios

## Multi-external scenarios
When multiple external cohorts are present, gating can be evaluated **pairwise**. The public behavior is:
- run comparisons across cohorts
- require all required comparisons to pass (according to configuration)

!!! important "What we don’t publish"
    We do not publish reproduction-grade thresholds, scoring formulas, or tuning defaults beyond high-level descriptions.
