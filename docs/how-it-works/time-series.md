# Longitudinal ctDNA (public view)

In this scaffold, the primary longitudinal modality is **ctDNA** represented in a long table (`ctdna_long`).

## What’s modeled (conceptually)
- **Measurement schedule**: when ctDNA is observed (including optional irregularity/jitter).
- **Missingness + dropout**: skipped observations and truncated follow-up are represented by missing rows (public convention).
- **Values**: ctDNA values are simulated in a way that supports downstream diagnostics, feature derivation, and estimation workflows.

## What we validate
We validate longitudinal behavior at a workflow level:
- distributions of measurement counts per subject
- patterns of missingness/dropout over time
- stability across internal vs external cohorts (where shifts are configured)
- consistency with downstream artifact generation (features → diagnostics/gating → estimation)

!!! note
    This page intentionally avoids the reproduction-critical ctDNA dynamics and parameterization.
