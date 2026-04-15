<p align="center">
  <img src="assets/Twintafo_AI_Logo_cropped%20%281%29%20copy.png" alt="Twintafo logo" width="160" />
</p>

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
%%{init: {"theme":"dark","flowchart":{"nodeSpacing":40,"rankSpacing":65},"themeVariables":{
  "fontSize":"16px",
  "background":"#0b1020",
  "lineColor":"#334155",
  "textColor":"#e2e8f0",
  "primaryColor":"#0b1020",
  "primaryBorderColor":"#334155",
  "clusterBkg":"transparent",
  "clusterBorder":"#1f2937"
}}}%%

flowchart TB
  %% Two-column snake layout:
  %% Left column goes top -> down, then connects to top of right column.

  subgraph LEFT[ ]
    direction TB
    A[YAML preset + seed]:::input
    B[Simulate internal + external cohorts]:::gen
    C[Hard schema contract]:::gen
    D[Diagnostics: balance + overlap]:::diag
  end

  subgraph RIGHT[ ]
    direction TB
    E[Deterministic gating: pass-fail + reasons]:::gate
    F[Adjusted estimate: PROCOVA-style Cox PH]:::est
    G{Borrowing enabled and gated in}:::decision
    H[Borrowing and ESS artifact]:::borrow
    I[Internal-only path]:::borrow
    J[Final estimate payload]:::est
    K[HTML run report + JSON artifacts]:::out
    L[Evidence pack optional]:::out
  end

  A --> B --> C --> D
  D --> E
  E --> F --> G
  G -- yes --> H --> J
  G -- no --> I --> J
  J --> K --> L

  %% Make section containers transparent (no white boxes)
  style LEFT fill:transparent,stroke:transparent
  style RIGHT fill:transparent,stroke:transparent

  %% Neon-ish blocks on dark background
  classDef input fill:#0b1020,stroke:#38bdf8,stroke-width:2px,color:#e2e8f0;
  classDef gen fill:#0b1020,stroke:#34d399,stroke-width:2px,color:#e2e8f0;
  classDef diag fill:#0b1020,stroke:#facc15,stroke-width:2px,color:#e2e8f0;
  classDef gate fill:#0b1020,stroke:#fb923c,stroke-width:2px,color:#e2e8f0;
  classDef est fill:#0b1020,stroke:#818cf8,stroke-width:2px,color:#e2e8f0;
  classDef decision fill:#0b1020,stroke:#c084fc,stroke-width:2px,color:#e2e8f0;
  classDef borrow fill:#0b1020,stroke:#f472b6,stroke-width:2px,color:#e2e8f0;
  classDef out fill:#0b1020,stroke:#94a3b8,stroke-width:2px,color:#e2e8f0;
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
