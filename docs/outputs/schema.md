# Synthetic cohort schema (public)

The generator emits a **hybrid schema**:
- patient-level baseline table(s)
- outcome table with time-to-event structure
- longitudinal long-format ctDNA measurements

## Key join keys (conceptual)
- A stable subject identifier (e.g., `patient_id`)
- A data source/cohort indicator (e.g., `data_source` for internal vs external)
- Optional cohort ID for multi-external scenarios

## Missingness conventions (public)
- Longitudinal missingness is represented by **absence of a row** for a subject/timepoint (i.e., “missing by omission”).
- Dropout can truncate scheduled timepoints.

## Competing risks (when enabled)
Some presets may include an `event_type` field that enables competing risks analyses and reporting payloads.

!!! note
    This page intentionally stays conceptual to avoid publishing reproduction-grade data dictionaries. The private implementation enforces a strict schema contract and will fail fast if outputs deviate.
