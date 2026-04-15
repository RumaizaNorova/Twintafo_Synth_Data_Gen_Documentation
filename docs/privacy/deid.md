# De-identification stance

We approach synthetic generation with a **de-identification mindset**:
- avoid direct identifiers in outputs,
- reduce the chance of producing rows that are too close to any single real individual,
- prefer reporting and sharing that does not expose raw sensitive values.

## Practical safeguards (public description)
- **Schema-level exclusion**: do not model or emit direct identifiers.
- **Constraint enforcement**: disallow out-of-domain values and suspicious combinations.
- **Aggregate-first reporting**: share evaluation outputs as aggregate summaries.

!!! warning "Not a formal privacy guarantee"
    De-identification is not the same as a formal privacy guarantee.  
    Where needed, we plan to expand disclosure risk evaluation (see next page).
