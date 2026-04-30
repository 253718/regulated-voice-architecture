# Auditability (without marketing)

Auditability is frequently misinterpreted as either:
- "we have logs" or
- "we are compliant"

Neither is sufficient.

## Principle

Treat auditability as a **design input**:
- define what evidence must exist
- define how evidence is produced (read-only where possible)
- define how evidence is packaged and handed over

## Examples of evidence types

- configuration exports (read-only snapshots)
- routing overview (policies, routes, dial plans)
- recording policy assignment summaries (aggregated)
- run outputs with integrity manifests

## Common pitfall

Do not claim compliance because you have evidence.
Evidence supports audits and reviews; compliance remains a governance outcome.
