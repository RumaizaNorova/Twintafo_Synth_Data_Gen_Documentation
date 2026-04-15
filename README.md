# Twintafo Synthetic Data Generator — Public Documentation

**Regulated-style synthetic clinical data generator scaffold** producing oncology-like cohorts (baseline covariates, survival outcomes, longitudinal ctDNA) plus **review artifacts** (diagnostics, transportability gating, adjusted estimates, optional borrowing/ESS, and HTML reports).

> The implementation lives in a separate **private** repository.  
> This repo is intentionally **documentation-only** so others can evaluate the logic, methodology, and evidence without reproduction-grade details.

## At a glance

```mermaid
flowchart LR
  A[YAML preset + seed] --> B[Simulate internal + external cohorts]
  B --> C[Hard schema contract]
  C --> D[Diagnostics: balance + overlap]
  D --> E[Deterministic gating<br/>pass/fail + reasons]
  E --> F[Adjusted estimate<br/>(PROCOVA-style Cox PH)]
  F --> G{Borrowing enabled<br/>and gated in?}
  G -- yes --> H[Borrowing / ESS artifact]
  G -- no --> I[Internal-only path]
  H --> J[Final estimate payload]
  I --> J
  J --> K[HTML run report + JSON artifacts]
  K --> L[(Evidence pack optional)]
```

## What you’ll find here
- **Executive summary**: what this is and who it’s for (`docs/executive-summary.md`)
- **Outputs contract**: exact categories of artifacts produced (`docs/outputs/artifacts.md`)
- **How it works (public view)**: pipeline, gating, estimands (`docs/how-it-works/`)
- **Validation**: OC + sensitivity methodology (`docs/validity/`)
- **Privacy & safety**: defensible claims + explicit non-claims (`docs/privacy/`)

## Disclosure boundaries (public vs private)
- **We share**: goals, assumptions, artifact contracts, evaluation methodology, and aggregate summaries.
- **We may share**: toy examples and screenshots of reports where safe.
- **We do NOT share**: reproduction-critical recipes (exact simulation dynamics, tuning defaults, internal fallbacks) or anything enabling a competitor to rebuild quickly.

## Read the docs
This repo is structured as a small docs site using MkDocs + Material.

- **Local preview**:
  1. `python3 -m venv .venv`
  2. `source .venv/bin/activate`
  3. `pip install -r requirements.txt`
  4. `mkdocs serve`

## Contact
If you’re evaluating Twintafo and need deeper technical access under NDA, this documentation is the starting point.
