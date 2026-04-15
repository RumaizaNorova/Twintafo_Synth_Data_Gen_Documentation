# Outputs & artifacts contract (public)

This page documents the **public-facing contract**: what a run produces and how reviewers should interpret it.

!!! note
    File names may vary slightly by preset/configuration, but the categories below are stable.

## Core tables (CSV)
- **`patients`**: baseline covariates for each subject (oncology-like cohort)
- **`outcomes`**: time-to-event outcomes with censoring/dropout representation
- **`ctdna_long`**: longitudinal ctDNA measurements in long format (repeated measures)
- **`latent_truth`**: an internal “truth spine” used to drive consistent simulation and stress tests (public-safe description only)

## Core artifacts (JSON)
- **`run_metadata`**: run ID, seed, environment metadata, and a structured summary of simulation assumptions
- **`diagnostics`**: transportability diagnostics (balance + overlap summaries)
- **`gating_result`**: deterministic pass/fail decision with reason strings and diagnostic summaries
- **`adjusted_estimates`**: adjusted estimation outputs (PROCOVA-style Cox PH) and optional competing risks payloads when configured
- **`borrowing_result`** (optional): borrowing/ESS summary when external borrowing is enabled and permitted
- **`final_estimate`**: the final estimate payload used for reporting/consumption (internal-only path vs borrowed path)

## Human-readable report (HTML)
- **`run_report.html`**: reviewer-oriented bundle summarizing config, diagnostics, gating, estimates, and key run facts

## Evidence pack (optional)
An evidence pack bundles a run (and optional OC/sensitivity outputs) with:
- **Manifest**: list of included artifacts with hashes for traceability
- **Rendered report**: a consolidated narrative suitable for review

## How to use these artifacts
- Use **JSON** artifacts for audit trails and downstream integration (UI/API).
- Use **HTML report** for human review.
- Use **OC/sensitivity** outputs to evaluate pipeline behavior across replicates and threshold sweeps.
