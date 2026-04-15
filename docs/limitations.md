# Limitations & known failure modes (public-safe)

This project is designed for **controlled scenario simulation** and **workflow validation**. It is not a general-purpose synthetic data engine.

## Notable limitations
- **Not a privacy guarantee**: this documentation does not claim differential privacy or formal disclosure-risk guarantees.
- **Schema is opinionated**: outputs follow a fixed contract intended for review bundles.
- **Simplified external shifts**: external cohort “shift” models are intentionally simplified to support testing.

## Known failure modes (high-level)
- **Small-N / low-event scenarios** can make adjusted estimation unstable. The private implementation includes guardrails and may return conservative outputs when fits are not reliable.
- **Threshold sensitivity**: gating and borrowing behavior is inherently sensitive to diagnostics and thresholds; this is why OC and sensitivity sweeps exist.

## How we mitigate (public)
- Provide OC and sensitivity tooling to understand behavior under known scenarios.
- Emit traceable artifacts so reviewers can inspect diagnostics, gating reasons, and analysis outputs.
