# Time series handling

Health datasets often include sequences (visits, labs, vitals, utilization) with:
- irregular sampling,
- censoring,
- seasonality and trends,
- event-triggered measurements.

## Public-level approach
We treat time series synthesis as a combination of:
- **event generation** (when observations occur),
- **value generation** (what is observed at each event),
- **consistency rules** (ordering, plausible intervals, cohort-specific patterns).

## What we validate
We evaluate whether synthetic sequences preserve:
- event-time distributions (inter-event time, seasonality)
- distribution of sequence lengths
- stability across cohort slices
- clinically plausible co-movements (e.g., vitals and interventions)
