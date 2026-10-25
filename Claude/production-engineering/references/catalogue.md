# Production and agentic engineering catalogue

Audit date: 2026-10-23 (Asia/Calcutta).

This catalogue separates **installed Skills** from **optional plugins** and from **capabilities that still need project-specific tools or workflows**. It does not claim that every capability needs a standalone Skill.

## Existing global collection

The existing 36 `sn-*` packages (496 files) are an exact copy of the current `OpenSenseNova/SenseNova-Skills` `main` tree at audit time (`7838651111ef2dc3ac0293f08008730f1a022694`, 2026-10-09). They cover spreadsheet and document analysis, research/search, image generation, presentations, reporting, and agent harness/update workflows. They do not provide a full software-delivery lifecycle.

No existing files were overwritten. Four official Skills were copied from Anthropic's Agent Skills repository at commit `dbd4588f9e1033efb41dad4bef2f7947c8993d44` (2026-10-09). The upstream repository identifies these skill bundles with Apache-2.0 license files; each `LICENSE.txt` is retained in its package. Ten local domain Skills and the `production-engineering` entry Skill were authored for this installation; they are not vendor-maintained packages.

| Capability | Installed skill | Coverage |
|---|---|---|
| Frontend and interface design | `frontend-design` | Design direction, responsive UI, accessibility, and visual critique. |
| Browser-based web app checks | `webapp-testing` | Playwright interaction, rendered-state inspection, browser logs, and helper scripts. The helper is not run automatically. |
| MCP server creation | `mcp-builder` | Python/TypeScript MCP server design, evaluation patterns, and reference material. |
| Skill authoring and evaluation | `skill-creator` | Skill structure, description tuning, evaluation, and packaging. It complements Claude Code's bundled `/claude-api` and skill workflows; it does not replace codebase testing. |
| End-to-end lifecycle routing | `production-engineering` | Local workflow index added with this audit; authored for this installation, not an upstream package. |

Static source review only: upstream scripts were not executed, and no project-specific compatibility tests were run. `webapp-testing`, `mcp-builder`, and `skill-creator` include scripts/examples that run only when explicitly used. Review their help and source before invoking them in a project.

## Coverage tracker: 62 capabilities across 10 domains

Every capability in the linked catalogue is now mapped to a dedicated workflow Skill. This is **instruction coverage**, not a claim that all integrations, tests, infrastructure, or deployments are installed or verified for a specific project.

| Domain | Skill | Mapped capabilities |
|---|---|---|
| Requirements and planning | `requirements-planning` | Requirements analysis and ambiguity detection; PRD and functional specifications; user stories and acceptance criteria; task breakdown and prioritization; dependency mapping and implementation plans; risk and change-impact analysis. |
| Architecture and design | `architecture-design` | System architecture and component diagrams; SOLID and design patterns; database schemas and migrations; API contracts and versioning; Architecture Decision Records; scalability, caching, and performance planning. |
| Frontend and UI/UX | `frontend-engineering`, `frontend-design` | Design systems and reusable components; responsive web/mobile layouts; accessibility and WCAG checks; frontend state and data fetching; visual regression and browser testing; usability, loading, empty, and error states. |
| Backend and integrations | `backend-integrations`, `mcp-builder` | REST/GraphQL APIs; authentication and authorization; input validation and secure data handling; background jobs and queues; third-party API integrations; retries, idempotency, and rate limits. |
| Testing and quality | `testing-quality`, `webapp-testing`, built-in `/code-review` where available | Unit/integration tests; end-to-end browser tests; TDD; regression and bug reproduction; coverage and mutation strategy; code review, refactoring, and static analysis. |
| Security and privacy | `security-privacy` | Threat modeling and secure design; OWASP-aligned checks; secrets and credentials; dependency and license review; prompt injection and AI-agent security; privacy, data retention, and access controls. |
| DevOps and production | `devops-reliability` | Git branching and PR workflows; CI/CD; Docker and environment config; deployment, rollback, and feature flags; logs, metrics, and distributed traces; backups, disaster recovery, and restore drills. |
| AI and agent engineering | `ai-agent-engineering`, `mcp-builder`, `skill-creator`, built-in `/claude-api` where available | LLM provider/model integration; RAG and retrieval evaluation; tool calling and structured outputs; agent workflows and orchestration; LLM evaluation, tracing, and guardrails; cost, latency, and context optimization. |
| Claude Code ecosystem | `claude-code-operations`, `skill-creator` | `CLAUDE.md` and scoped rules; Skills and reusable workflows; custom subagents; hooks and lifecycle automation; plugins and marketplaces; MCP servers and tool integrations; permissions, sandboxing, and settings; CLI automation and non-interactive use. |
| Documentation and maintenance | `documentation-maintenance` | README and setup guides; architecture/API documentation; changelogs and release notes; troubleshooting and FAQs; technical debt and dependency upgrades; incident response and postmortems. |

### Status and limits

- **Installed official packages:** `frontend-design`, `webapp-testing`, `mcp-builder`, and `skill-creator`, copied from Anthropic Agent Skills commit `dbd4588f9e1033efb41dad4bef2f7947c8993d44` with their Apache-2.0 `LICENSE.txt` files.
- **Installed local workflows:** the ten domain Skills in the table, plus `production-engineering` as the entry point. These were authored for this global installation; they are not vendor-maintained packages.
- **Existing library:** the 36 `sn-*` packages remain unchanged and cover SenseNova data, research, media, reporting, and agent-harness tasks.
- **Not installed:** the official plugin options listed below. They may add agents, commands, hooks, or MCP servers and need separate review.
- **Not verified:** no evals or project-specific tests were run for the newly authored guidance; no browser, backend, CI, deployment, monitoring, backup, or restore action was executed.

Use the repository's own code, test scripts, cloud/provider documentation, and operating runbooks to turn these workflows into concrete implementation and checks. For web accessibility, consult the W3C WCAG 2.2 Recommendation; for application security, OWASP Cheat Sheets; for telemetry, OpenTelemetry's signals docs. Verify stack-specific commands against their current primary documentation.

### Windows note

The upstream `webapp-testing` examples use Unix-style temporary paths and shell continuation. On native Windows, adapt paths and commands to PowerShell and the installed Python launcher (`py` when available), or use the project's WSL/Git Bash environment. Confirm Playwright and browser dependencies in that environment before use; installation did not start a server or helper.
## Official plugin candidates (not installed)

These appear in Anthropic's official Claude Code plugin marketplace. They are plugins, which may package commands, agents, hooks, MCP servers, and Skills together. This installation has not enabled them.

| Candidate | Use | Install command |
|---|---|---|
| `feature-dev` | Explore a codebase, plan and implement a feature, then review it | `/plugin install feature-dev@claude-plugins-official` |
| `code-review` | Review pull requests with confidence-based findings | `/plugin install code-review@claude-plugins-official` |
| `pr-review-toolkit` | Specialized review for tests, errors, types, comments, and simplification | `/plugin install pr-review-toolkit@claude-plugins-official` |
| `security-guidance` | Security reminders and automated code review hooks | `/plugin install security-guidance@claude-plugins-official` |
| `commit-commands` | Git commit and pull request commands | `/plugin install commit-commands@claude-plugins-official` |

Anthropic's plugin docs explain that enabled plugins can load their components in every session, run hooks/MCP servers as the user, and consume context. Inspect each plugin before installation. In particular, `security-guidance` sends diffs and related code to the configured model endpoint for review; check its current README and your provider's data terms before enabling it.

`plugin-dev` is an additional Claude Code skills/agents/hooks toolkit in the `anthropics/claude-code` repository. Its repo-level `LICENSE.md` says use is subject to Anthropic Commercial Terms. It was not copied into this folder. If desired, install through Claude Code's official marketplace rather than treating the skill files as Apache-licensed:

```text
/plugin install plugin-dev@claude-code-marketplace
```

## Sources and update tracking

- Anthropic Agent Skills: <https://github.com/anthropics/skills>
  - revision copied: `dbd4588f9e1033efb41dad4bef2f7947c8993d44`
  - bundles installed: `frontend-design`, `webapp-testing`, `mcp-builder`, `skill-creator`
  - license files retained per bundle: `LICENSE.txt` (Apache-2.0)
- Anthropic Claude Code plugins: <https://github.com/anthropics/claude-plugins-official>
  - reviewed at revision: `465f09344424225c25d438f2e052732c3d688d2f`
  - repo license: Apache-2.0; review each plugin's code, dependencies, hooks, MCP configuration, and data handling separately.
- Claude Code plugin-dev source: <https://github.com/anthropics/claude-code/tree/main/plugins/plugin-dev>
  - reviewed at revision: `30fa83c68c77d2e3a7a42f1407831ec252511130`
  - not copied due to the repository's Commercial Terms notice.
- Claude Code skills documentation: <https://code.claude.com/docs/en/skills>
- Claude Code plugins documentation: <https://code.claude.com/docs/en/plugins>

To update these additions later, compare each installed bundle to its source subdirectory, review the new diff and license, preserve the selected subset, record the new commit, and check for skill-name conflicts before copying. Do not bulk-install community collections without that review.


