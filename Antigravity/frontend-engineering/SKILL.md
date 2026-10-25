---
name: frontend-engineering
description: "Implement or review production frontend interfaces, design systems, responsive layouts, accessibility, client-side state, data fetching, or user-facing error and empty states."
---

# Frontend engineering

Use `frontend-design` for visual direction and `webapp-testing` for browser-based interaction when they fit the task.

## Workflow

1. Inspect the existing framework, routes, design tokens, components, data flow, and supported browsers.
2. Tie visual choices to the product, audience, content, and user task. Reuse the project's design system unless the brief calls for a change.
3. Design loading, empty, success, validation, permission, offline, and failure states along with the happy path.
4. Keep state and data-fetching boundaries explicit. Handle cancellation, stale results, retries, and optimistic updates only where needed.
5. Check responsive behavior, semantic markup, keyboard access, visible focus, contrast, accessible names, reduced motion, and zoom/reflow. Use the project's target; consult W3C WCAG 2.2 for normative criteria.
6. Consider visual regression and real-browser checks for behavior that static inspection cannot confirm.
7. Review the implemented UI against the brief and remove unrelated visual or architectural changes.

## Guardrails

Do not claim WCAG conformance from a quick scan. Follow the user's design constraints and the repository's components. Do not replace real product content with placeholders unless asked.

Reference: https://www.w3.org/TR/WCAG22/