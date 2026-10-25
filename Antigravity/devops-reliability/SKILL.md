---
name: devops-reliability
description: "Plan or review CI/CD, Docker and environment configuration, production deployment, rollback, feature flags, observability, backups, disaster recovery, or restore procedures."
---

# DevOps and reliability

## Workflow

1. Inspect the actual hosting platform, CI workflows, deployment manifests, runbooks, environments, and secret store.
2. Keep build artifacts reproducible and configuration environment-specific. Avoid embedding secrets in images, logs, or checked-in files.
3. Scope CI credentials and deployment permissions to the smallest required actions. Separate validation from production release where the platform allows.
4. Define rollout and rollback conditions, migration ordering, health checks, and compatibility between old and new versions.
5. Identify user-facing service objectives and actionable alerts. Use correlated logs, metrics, and traces where the existing stack supports them.
6. For reliability risks, trace timeouts, retries, overload, queues, dependency outages, and recovery behavior.
7. Verify backup scope, retention, ownership, and restore steps. A backup plan is incomplete until a restore is exercised.
8. Document changes to infrastructure and operating procedures; state which steps were not run.

## Guardrails

Never deploy, rotate production secrets, alter live infrastructure, or perform a restore without an explicit request. Do not invent a cloud platform, SLO, or runbook. Confirm platform-specific commands against current vendor docs.

References:
- https://docs.docker.com/
- https://opentelemetry.io/docs/concepts/signals/