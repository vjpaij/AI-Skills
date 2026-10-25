---
name: security-privacy
description: "Threat-model an application change or review secure design, OWASP risks, secrets, dependencies and licenses, prompt injection, privacy, data retention, or access controls."
---

# Security and privacy

## Workflow

1. Identify assets, data classifications, users, trust boundaries, entry points, and privileged operations affected by the change.
2. Trace untrusted input and tool output through parsing, authorization, storage, rendering, shell use, and outbound network calls.
3. Review authentication and authorization independently; validate ownership and tenant boundaries on every protected object operation.
4. Check for injection, XSS, SSRF, path traversal, unsafe deserialization, CSRF, secret leakage, insecure defaults, and dependency risk as relevant to the stack.
5. Minimize collected/retained data. Define access, encryption, deletion, audit, and incident response expectations.
6. For AI workflows, treat retrieved content and tool responses as untrusted; constrain tools, validate structured output, and protect secrets from prompts and logs.
7. Recommend concrete mitigations and verification steps. Use the project's SAST, dependency, secret, and policy tooling where available.

## Guardrails

Do not claim a security audit or compliance from a checklist. Never expose secrets in output. Verify current OWASP and framework guidance for the affected technology. External review plugins may transmit code diffs to a configured model provider; inspect data handling before enabling them.

References:
- https://owasp.org/www-project-cheat-sheets/
- https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet.html