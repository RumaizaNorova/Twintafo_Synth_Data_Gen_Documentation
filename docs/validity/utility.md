# Utility (in this scaffold)

In this project, “utility” is primarily about whether the generated cohorts support the **intended review workflow** and produce credible **artifact bundles**.

## What we check (public examples)
- **Artifact completeness**: required tables and JSON artifacts are produced under the schema contract.
- **Diagnostic sensibility**: balance/overlap summaries behave predictably when scenario shifts are introduced.
- **Decision behavior**: gating outcomes align with diagnostic summaries (pass/fail with coherent reason strings).
- **Analysis viability**: adjusted estimation produces interpretable outputs when scenario conditions support it.

## How it’s reported
- run report summaries (HTML)
- machine-readable artifacts for audit and downstream UI/API use
- aggregate OC and sensitivity summaries (see those sections)

!!! note
    This repository does not document “train ML models on synthetic vs real” benchmarking because the scaffold does not ingest real partner datasets by default and the focus is decision-pipeline validation.
