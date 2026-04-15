# Executive summary

## One-liner
Twintafo is a **regulated-style synthetic clinical data generator scaffold** that produces **oncology-like cohorts** (baseline covariates, survival outcomes, longitudinal ctDNA) and emits **analysis + review artifacts** (diagnostics, transportability gating, adjusted estimates, optional borrowing/ESS, and HTML reports).

## 30-second pitch
Provide a **YAML preset**, **seed**, and **output directory**. The system simulates internal + external cohorts under a strict schema, computes **transportability diagnostics** (balance + overlap), applies **deterministic gating** to decide whether external data can be borrowed, runs a **PROCOVA-style Cox PH adjusted estimate**, optionally computes **borrowing/ESS**, and writes an **HTML run report** plus **machine-readable JSON artifacts** designed for audit and downstream UI/API use.

## Who this is for
- **Biostatisticians / data scientists** validating analysis and review workflows under controlled scenarios
- **Developers** generating consistent “review bundles” (artifacts + report) for integration and testing

## What makes it different
- **Regulated-style traceability**: config copy, run metadata, structured assumptions, reasoned gating outcomes, evidence manifests/hashes
- **Decision-centric pipeline**: diagnostics → gating → estimate → optional borrowing → final estimate, rather than generic synthetic tabular modeling
- **Hard schema contract**: fail-fast enforcement so artifacts remain reviewable and machine-consumable
