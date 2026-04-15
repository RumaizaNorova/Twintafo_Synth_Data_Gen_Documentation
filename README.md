# Twintafo Synthetic Data Generator — Public Documentation

Twintafo is a **regulated-style synthetic clinical data generator scaffold** producing **oncology-like cohorts** (baseline covariates, survival outcomes, longitudinal ctDNA) plus **review artifacts** (diagnostics, transportability gating, adjusted estimates, optional borrowing/ESS, and HTML reports).

> The implementation lives in a separate **private** repository.  
> This repo is intentionally **documentation-only** so others can evaluate the logic, methodology, and evidence without reproduction-grade details.

## Quick links
- **Start here**: [`docs/index.md`](docs/index.md)
- **Executive summary**: [`docs/executive-summary.md`](docs/executive-summary.md)
- **Outputs contract**: [`docs/outputs/artifacts.md`](docs/outputs/artifacts.md)
- **Pipeline & decision flow**: [`docs/how-it-works/pipeline.md`](docs/how-it-works/pipeline.md)
- **Transportability & gating**: [`docs/how-it-works/gating.md`](docs/how-it-works/gating.md)
- **Validation (OC + sensitivity)**: [`docs/validity/overview.md`](docs/validity/overview.md)
- **Privacy claims / non-claims**: [`docs/privacy/claims.md`](docs/privacy/claims.md)

## At a glance (pipeline)
```mermaid
%%{init: {"theme":"base","flowchart":{"nodeSpacing":55,"rankSpacing":70},"themeVariables":{
  "fontSize":"16px",
  "lineColor":"#94a3b8",
  "textColor":"#0b1220",
  "primaryColor":"#e2e8f0",
  "primaryBorderColor":"#64748b"
}}}%%

flowchart TB
  A[YAML preset + seed]:::input

  subgraph GEN[Simulation]
    B[Simulate internal + external cohorts]:::gen
    C[Hard schema contract]:::gen
  end

  subgraph DEC[Diagnostics + decisioning]
    D[Diagnostics: balance + overlap]:::diag
    E[Deterministic gating: pass-fail + reasons]:::gate
  end

  subgraph EST[Estimation]
    F[Adjusted estimate: PROCOVA-style Cox PH]:::est
    G{Borrowing enabled and gated in}:::decision
    H[Borrowing and ESS artifact]:::borrow
    I[Internal-only path]:::borrow
    J[Final estimate payload]:::est
  end

  subgraph OUT[Artifacts + review bundle]
    K[HTML run report + JSON artifacts]:::out
    L[Evidence pack optional]:::out
  end

  A --> B --> C --> D --> E --> F --> G
  G -- yes --> H --> J
  G -- no --> I --> J
  J --> K --> L

  classDef input fill:#e0f2fe,stroke:#0284c7,stroke-width:2px,color:#0b1220;
  classDef gen fill:#dcfce7,stroke:#16a34a,stroke-width:2px,color:#052e16;
  classDef diag fill:#fef9c3,stroke:#ca8a04,stroke-width:2px,color:#422006;
  classDef gate fill:#ffedd5,stroke:#f97316,stroke-width:2px,color:#431407;
  classDef est fill:#e0e7ff,stroke:#4f46e5,stroke-width:2px,color:#1e1b4b;
  classDef decision fill:#fae8ff,stroke:#a855f7,stroke-width:2px,color:#3b0764;
  classDef borrow fill:#fce7f3,stroke:#db2777,stroke-width:2px,color:#500724;
  classDef out fill:#f1f5f9,stroke:#334155,stroke-width:2px,color:#0f172a;
```

## What you can evaluate from this repo
- **Artifact contract**: what files exist, what they mean, how they fit together
- **Decision logic (public view)**: diagnostics → gating → estimate → optional borrowing → reporting
- **Validation methodology**: operating characteristics and sensitivity sweeps for decision behavior
- **Explicit boundaries**: what we do and do not claim publicly

## Disclosure boundaries (public vs private)
- **We share**: goals, assumptions, artifact contracts, evaluation methodology, and aggregate summaries.
- **We may share**: toy examples and screenshots of reports where safe.
- **We do NOT share**: reproduction-critical recipes (exact simulation dynamics, tuning defaults, internal fallbacks) or anything enabling a competitor to rebuild quickly.

## Preview the docs site locally
This repo is structured as a small docs site using MkDocs + Material.

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
mkdocs serve
```

## Contact
If you’re evaluating Twintafo and need deeper technical access under NDA, this documentation is the starting point.
