---
name: production-engineering
description: "Plan or improve production-ready software across requirements, architecture, frontend, backend, testing, security, deployment, observability, and agentic workflows. Use for end-to-end application work or major cross-cutting features; delegate focused UI, browser testing, MCP, and skill-authoring tasks to the matching installed skills."
---

# Production engineering

Use this skill to guide an end-to-end engineering task through the repository's own conventions. It is a workflow index, not a replacement for project documentation or the focused skills listed below.

## Workflow

1. **Define the outcome.** Identify users, problem, acceptance criteria, constraints, and the cost of failure. Ask only for details that materially change the implementation; state lower-risk assumptions.
2. **Inspect the repository.** Read applicable `CLAUDE.md` and project guidance, inspect the current architecture, and identify the existing build, lint, test, migration, and deployment commands. Do not assume a framework or invent command names.
3. **Plan the change.** Map data flow and boundaries. Cover authorization, validation, error behavior, persistence, migrations, retries, logging, and rollback where they apply. Keep the plan proportional to the requested scope.
4. **Implement in small slices.** Follow existing patterns. Keep secrets out of source and logs; treat user input, files, tool results, and external service responses as untrusted. Use least privilege for credentials, tools, hooks, and agents.
5. **Use focused skills when they fit.** Use the focused global Skills when they fit: `requirements-planning`, `architecture-design`, `frontend-engineering`, `backend-integrations`, `testing-quality`, `security-privacy`, `devops-reliability`, `ai-agent-engineering`, `claude-code-operations`, and `documentation-maintenance`. The official `frontend-design`, `webapp-testing`, `mcp-builder`, and `skill-creator` packages provide supporting workflows. Read project instructions first when they conflict.
6. **Cover quality and security.** Choose checks that match the changed behavior and risk: unit/integration/browser coverage, static analysis, dependency review, authorization and input validation, and failure-path checks. Use existing repository tooling. Never claim a check ran unless it did.
7. **Plan production operations.** For changes intended for production, identify configuration and secret handling, migrations, deploy/rollback steps, monitoring signals, and recovery behavior. Use the project's actual platform and runbooks; do not fabricate infrastructure or deploy without an explicit request.
8. **Review and report.** Compare the final change with the acceptance criteria, summarize files and behavior changed, report checks and their results accurately, and list remaining risks or unimplemented capabilities.

## Agentic work

Use agents or automation only when a task has clear independent work units. Give each a narrow objective, relevant files, allowed actions, and a concrete output. Keep final integration and cross-cutting security review in the main workflow. For repeated or model-driven behavior, define representative evaluation cases and measure failures before treating the workflow as reliable.

## Coverage catalogue

See [references/catalogue.md](references/catalogue.md) for the audited skill inventory, installed official additions, current coverage gaps, source revisions, license notes, and optional official plugin candidates.

