---
name: backend-integrations
description: "Build or review backend services, REST or GraphQL APIs, authentication, authorization, validation, persistence, background jobs, or third-party integrations."
---

# Backend and integrations

## Workflow

1. Inspect the service framework, API conventions, data model, migrations, auth middleware, and error format already in use.
2. Define the contract: inputs, outputs, status/error behavior, compatibility, pagination, and versioning.
3. Validate types, structure, ranges, size, and business rules at trust boundaries. Check authorization separately from input validation.
4. Trace identity and access checks through every operation and object lookup. Use least privilege for service credentials.
5. For jobs and remote calls, set timeouts and explicit retry limits. Use idempotency keys or deduplication where repeating a request can change state.
6. Bound queues, payloads, concurrency, and rate limits. Handle partial failure and provider outages with observable errors.
7. Plan schema changes for old/new code overlap and document safe rollout and rollback.
8. Cover contract, validation, authorization, duplicate-request, and dependency-failure cases with the project's tests and tooling.

## Guardrails

Never log credentials or sensitive payloads. Do not retry non-idempotent operations blindly. Consult current framework and provider docs for version-specific APIs.

Reference: https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html