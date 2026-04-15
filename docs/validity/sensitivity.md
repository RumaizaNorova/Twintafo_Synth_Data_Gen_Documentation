# Sensitivity analyses

Sensitivity sweeps explore how pipeline behavior changes as key parameters vary (most commonly gating/overlap thresholds).

## What we sweep (public examples)
- overlap-related thresholds
- scenario shift strength (where presets expose it)
- replicate counts (for stability checks)

## What we report
- gating pass rate as a function of the swept parameter (“turn-on” behavior)
- diagnostic summary trends (aggregate)
- borrowing/ESS trends (when enabled)

!!! important
    We do not publish reproduction-grade parameter grids or internal acceptance recipes. Sensitivity is documented as a methodology and reporting structure.
