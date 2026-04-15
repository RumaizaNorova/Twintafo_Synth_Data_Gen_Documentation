# Operating characteristics (OC)

Operating characteristics runs evaluate pipeline behavior across many synthetic replicates under a specified scenario.

## What OC answers
- How often does gating pass/fail under the scenario?
- Under “null effect” scenarios, what is the empirical false-positive behavior?
- Under “non-null” scenarios, what is the bias behavior (in aggregate)?
- When borrowing is enabled, what does borrowing/ESS look like in aggregate?

## What we report (public)
We report aggregate summaries such as:
- gating pass rate
- error/bias summaries (scenario-dependent)
- average/typical borrowing summaries (when applicable)

!!! note
    OC runs are designed to validate the **decision pipeline**. They are not intended to “prove privacy”, and they do not replace real-world domain validation.
