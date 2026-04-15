# How to run (public-safe)

This page documents how runs are typically executed at a **command level** and what artifacts they produce. It intentionally avoids reproduction-critical details.

## Typical commands
- **Run a pipeline**: generate cohorts, compute diagnostics/gating, compute estimates, write report + artifacts
- **Diagnostics only**: compute diagnostic summaries for a completed run
- **Operating characteristics (OC)**: run many replicates and summarize pass rates / error / bias behavior (aggregate)
- **Sensitivity sweeps**: vary key thresholds and summarize “turn-on” behavior (aggregate)
- **Evidence pack**: bundle artifacts + manifests/hashes into a reviewer-friendly package

## What to expect on disk
See [Outputs & artifacts contract](outputs/artifacts.md).

!!! note
    The private implementation may expose additional options and presets. Public docs focus on stable concepts and artifact categories.
