# Modeling approach (public view)

This project is a **simulation-based clinical generator scaffold**. It is designed to produce **oncology-like cohorts** with:
- baseline covariates,
- time-to-event outcomes (with censoring/dropout),
- longitudinal ctDNA measurements,
and to emit **decision pipeline artifacts** (diagnostics → gating → estimation → optional borrowing).

## High-level ingredients
- **Baseline covariates**: generated from field-specific distributions and simple relationships (public-safe description).
- **Outcome process**: time-to-event simulation from parametric families with configurable censoring/dropout; optional competing risks representations in some scenarios.
- **Longitudinal ctDNA**: simulated measurement schedule + values with missingness/dropout patterns; may be coupled to outcome-related latent structure at a high level.
- **Adjusted estimation**: PROCOVA-style Cox PH to produce an adjusted estimate artifact for review workflows.

## Why this approach
- **Auditability**: the system is meant to generate traceable artifacts and reviewer-oriented summaries, not just “realistic rows”.
- **Decision validation**: the goal is to validate how diagnostics, gating, and borrowing behave under known scenarios.
- **Schema contract**: outputs are constrained to a strict artifact contract so downstream review bundles and tooling remain stable.

!!! note "Boundaries"
    This page intentionally avoids reproduction-grade details (exact simulation dynamics, constants, tuning defaults, and fallback heuristics).
