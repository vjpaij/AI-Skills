---
name: requirements-planning
description: Turn a new application, feature, or ambiguous request into agreed requirements, acceptance criteria, priorities, dependencies, and an implementation plan. Use before substantial implementation when scope or success conditions need clarification.
---

# Requirements and planning

## Workflow

1. Restate the user's goal, audience, main use cases, constraints, and what is out of scope.
2. Inspect project docs and issue conventions before proposing a new PRD or ticket format.
3. Separate observed facts from assumptions. Ask only questions that change architecture, scope, safety, or delivery order; state reversible assumptions.
4. Turn the goal into testable acceptance criteria, including failure, empty, permission, and boundary cases.
5. Identify functional and non-functional needs: latency, availability, privacy, accessibility, scale, cost, and support where relevant.
6. Break work into small deliverable slices. Map dependencies, risks, rollout order, and a rollback or stop condition for risky changes.
7. Return the plan in the smallest format that supports a decision: checklist, issue list, user stories, or short specification.

## Guardrails

Do not invent stakeholders, business rules, deadlines, or repository capabilities. Avoid large plans for small changes. Distinguish requirements from implementation suggestions. Revisit the criteria when new evidence changes the scope.
