---
name: testing-quality
description: Create or review a risk-based test plan, unit or integration tests, browser tests, regression reproduction, TDD workflow, code review, refactoring, or static analysis.
---

# Testing and quality

Use `webapp-testing` for local browser workflows and Claude Code's built-in `/code-review` when available. Keep the project's own test commands authoritative.

## Workflow

1. Identify the behavior and regression risk. Turn acceptance criteria into observable outcomes.
2. Reproduce the defect or define a failing case before changing code when practical.
3. Choose the narrowest test level that covers the risk: unit for local logic, integration for boundaries, end-to-end for critical user journeys, plus static analysis where relevant.
4. Include edge cases, permissions, malformed input, timeouts, retries, and failure states when they affect the changed behavior.
5. Avoid tests coupled to implementation details. Prefer stable assertions on public behavior and invariants.
6. Run the repository's documented checks that are in scope. Report the exact commands and results; separate checks not run from checks that passed.
7. For refactors, preserve behavior first, make structural changes, then simplify only what improves readability without reducing coverage.
8. Use mutation testing or coverage analysis only when it answers a concrete quality question and the project supports it.

## Guardrails

A green test suite does not prove security, accessibility, or production readiness. Never claim coverage or successful verification that was not measured.
