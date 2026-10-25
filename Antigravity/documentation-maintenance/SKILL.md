---
name: documentation-maintenance
description: Create or maintain software README and setup guides, architecture or API docs, changelogs, troubleshooting, dependency upgrades, technical-debt records, incident response, or postmortems.
---

# Documentation and maintenance

## Workflow

1. Identify the document's reader, the decision or task it supports, and the authoritative source in code/configuration.
2. Inspect the current behavior and docs before editing. Keep commands, paths, versions, flags, and examples aligned with the repository.
3. Update setup and README steps when prerequisites, environment variables, data flows, or user-visible behavior change.
4. Document API contracts and architecture trade-offs at the boundary where maintainers will look for them. Prefer a short ADR for durable decisions.
5. Follow existing changelog and release conventions. Include user-visible changes and migration notes; do not claim a release happened if it did not.
6. For troubleshooting, state symptoms, likely causes, safe diagnostics, and recovery steps. Avoid destructive commands without clear scope and backup guidance.
7. For incidents and postmortems, separate timeline, impact, contributing factors, response, and follow-up actions. Keep sensitive data out of public docs.
8. For dependency upgrades or technical debt, state current/target versions, compatibility evidence, migration effort, and verification still needed.

## Guardrails

Do not document intended behavior as implemented behavior. Prefer links to maintained primary docs for version-specific details. Remove stale guidance rather than layering contradictory instructions.
