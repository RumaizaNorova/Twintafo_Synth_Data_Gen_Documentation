# Web app & evidence pack (public view)

An optional web application can sit on top of the generator to:
- run jobs
- stream logs
- serve run artifacts
- assemble an “evidence pack” bundle for review

## Evidence pack concept
An evidence pack is a reviewer-friendly bundle that may include:
- core run artifacts (tables + JSON)
- run report
- OC and sensitivity summaries (when generated)
- a **manifest** listing included files and hashes (traceability / tamper-evidence)

## Security posture (public)
By default, this kind of web layer is typically intended for:
- local use or trusted networks
- explicit governance controls in deployment environments

!!! important
    This documentation does not assert a complete security model. Any production deployment should add authentication/authorization, rate limiting, and operational controls appropriate to the environment.
