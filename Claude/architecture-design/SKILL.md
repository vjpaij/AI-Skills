---
name: architecture-design
description: Design or review a software system, major component, data model, API contract, migration, or performance plan. Use when a change crosses service or data boundaries or needs explicit trade-offs.
---

# Architecture and design

## Workflow

1. Read the existing architecture notes and inspect the current code paths, data stores, and service boundaries.
2. Define constraints and quality attributes: security, availability, latency, scale, cost, operability, and compatibility.
3. Draw or describe the smallest useful context and component view. Trace important data and control flows.
4. Compare viable options against the constraints. Record material trade-offs and assumptions in the project's ADR format when one exists.
5. For schema or API changes, define invariants, ownership, compatibility, validation, versioning, and a safe migration/rollback sequence.
6. Identify bottlenecks and failure modes before introducing caches, queues, retries, replicas, or new services.
7. Check the design against the codebase and update the proposal when the repo contradicts an assumption.

## Guardrails

Prefer incremental changes that preserve working boundaries. Do not add abstraction, service, queue, or database technology without a concrete requirement. Never claim a design is scalable or fault-tolerant without stating the load and failure assumptions.
