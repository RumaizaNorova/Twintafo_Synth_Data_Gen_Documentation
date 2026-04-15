# Validation overview (decision-centric)

We validate this system as a **decision pipeline** (diagnostics → gating → estimate → optional borrowing → report), not just as “synthetic data”.

We evaluate along three axes:
- **Diagnostic validity**: do balance/overlap diagnostics behave sensibly under known shifts?
- **Decision validity**: do gating/borrowing decisions behave as intended under controlled data-generating processes?
- **Robustness**: does behavior remain stable under stressors (cohort shift, missingness, schema variation, and edge cases)?

!!! important "What this is (and isn’t)"
    This section documents **methodology** and **reporting structure**.  
    Specific benchmark results may be published as aggregate tables/figures depending on partner constraints.

## Evaluation principles
- Prefer **decision-relevant** evaluations (gating pass rates, error rates, bias) over generic similarity metrics.
- Use **operating characteristics (OC)** to summarize behavior across replicates.
- Use **sensitivity sweeps** to understand threshold and overlap effects.
- Report **failure modes** and known limitations.

## Reporting
For each dataset/configuration, we report:
- public-safe scenario description
- artifacts produced (diagnostics, gating, estimates, borrowing, final)
- OC summaries (pass rate, error/bias summaries, ESS summaries where applicable)
- sensitivity summaries (threshold “turn-on” behavior)
- robustness notes and limitations
