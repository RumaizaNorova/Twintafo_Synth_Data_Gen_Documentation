# Pipeline & decision flow (public view)

This section describes the pipeline at a level that supports **technical evaluation** without enabling full reproduction. The system is **decision-centric**: it generates cohorts so the downstream *diagnostics → gating → estimation → optional borrowing → reporting* workflow can be exercised.

## End-to-end stages
1. **Config intake + run initialization**
   - load YAML preset/config, create a run directory, write run metadata and assumptions summary
2. **Cohort simulation**
   - generate internal cohort and one or more external cohorts under configured shifts
   - emit baseline, outcomes (time-to-event), and longitudinal ctDNA tables
3. **Hard schema enforcement**
   - fail fast if outputs do not match the expected contract
4. **Transportability diagnostics**
   - compute balance and overlap summaries comparing internal vs external cohorts
5. **Deterministic gating**
   - decide whether external data is eligible for borrowing (pass/fail + reason strings)
6. **Adjusted estimation**
   - compute an adjusted estimate (PROCOVA-style Cox PH) and optional competing risks payloads (when enabled)
7. **Optional borrowing / ESS**
   - if gated in, compute borrowing artifacts and produce a final estimate payload
8. **Reporting + export**
   - write machine-readable JSON artifacts and an HTML run report; optionally bundle an evidence pack

## What we keep private
We do not publish:
- exact feature engineering/transforms (including ctDNA feature details)
- parameterization choices that make reproduction feasible
- numeric constants, tuning, or fallback heuristics that materially affect outputs

## What we do publish
- artifact contracts (what files exist and what they mean)
- evaluation methodology (OC + sensitivity + robustness)
- qualitative design rationale and public-safe limitations
