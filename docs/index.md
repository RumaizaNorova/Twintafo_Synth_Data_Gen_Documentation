# Twintafo Synthetic Data Generator (documentation)

<p align="center">
  <img src="../assets/Twintafo_AI_Logo_cropped%20%281%29%20copy.png" alt="Twintafo logo" width="140" />
</p>

Twintafo is a **regulated-style synthetic clinical data generator scaffold**. It produces **oncology-like cohorts** (baseline covariates, survival outcomes, longitudinal ctDNA) and emits **analysis + review artifacts** (diagnostics, transportability gating, adjusted estimates, optional borrowing/ESS, and HTML reports).

This site explains:
- **What we build** (and what we don’t)
- **How it works** at a public, non-reproducible level
- **Why it’s valid** through utility + robustness evaluation
- **Privacy & safety boundaries** for responsible use

!!! note "Why this repo exists"
    The implementation is private (startup IP). This repository is intentionally **documentation-only** so others can evaluate the *logic, methodology, and evidence* without access to proprietary code.

## What “good” means here
This project is **decision-centric**: synthetic data is generated so the full pipeline (diagnostics → gating → estimation → optional borrowing → reporting) can be validated under controlled scenarios.

## What we publicly claim today
- **Traceable artifacts**: each run emits machine-readable JSON artifacts + an HTML report suitable for review bundles.
- **Deterministic transportability gating**: explicit pass/fail gating based on diagnostic summaries (with reason strings).
- **Validation harness**: operating characteristics (OC) and sensitivity sweeps to understand gating/borrowing behavior under known data-generating processes.

We do **not** claim differential privacy or disclosure-risk guarantees in this documentation.

## Start here
- [Executive summary](executive-summary.md)
- [Outputs & artifacts contract](outputs/artifacts.md)
- [Pipeline & decision flow](how-it-works/pipeline.md)
- [Transportability diagnostics & gating](how-it-works/gating.md)
- [Validation overview](validity/overview.md)
