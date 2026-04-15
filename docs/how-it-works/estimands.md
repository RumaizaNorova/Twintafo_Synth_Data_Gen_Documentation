# Estimands & analyses (public view)

This generator scaffold is designed to emit **analysis artifacts** that mimic a review-oriented clinical workflow.

## Primary adjusted estimate
The pipeline produces an adjusted estimate via a **PROCOVA-style Cox proportional hazards** analysis (Cox PH). The output includes:
- an effect estimate payload
- uncertainty summary suitable for reporting

## Competing risks (when enabled)
Some presets include an outcome representation that enables competing risks analyses. In those cases, the pipeline may additionally export:
- cause-specific estimates
- cumulative incidence payloads for reporting

## Final estimate payload
The pipeline always exports a **final estimate** artifact that represents the “decision output” of the run:
- internal-only estimate path, or
- borrowed estimate path (if gating permits and borrowing is enabled)

!!! note
    This page intentionally avoids implementation specifics (model fitting settings, convergence handling, and fallback heuristics).
