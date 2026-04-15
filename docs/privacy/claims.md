# Public claims & boundaries

This documentation is designed to be **credible** while remaining **non-reproducible**.

## What we claim publicly (today)
- This codebase is a **simulation-based generator scaffold**; it does not require ingesting real patient identifiers to run.
- The pipeline emits **traceable artifacts** (run metadata, config copy, manifests/hashes where enabled) for review and audit.
- We validate the pipeline primarily for **decision behavior** (diagnostics → gating → estimation → optional borrowing) using OC and sensitivity methodologies.

## What we do not claim publicly (today)
- We do not claim formal differential privacy (DP) guarantees in this repo.
- We do not claim the synthetic data is risk-free for every downstream use.
- We do not claim membership-inference / linkage / disclosure-risk guarantees based on the current public documentation.

## What we won’t publish here
- implementation details that enable full reproduction
- partner datasets or any real-row examples
- internal tuning or configuration recipes

## What we can publish safely
- aggregate quality metrics
- high-level pipeline and methodological rationale
- toy, non-sensitive examples (when useful)
