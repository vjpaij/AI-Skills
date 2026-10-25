---
name: ai-agent-engineering
description: "Build or review LLM integrations, RAG and retrieval, tool calling, structured outputs, agent workflows, evaluations, tracing, guardrails, or cost and latency behavior."
---

# AI and agent engineering

Use Claude Code's bundled `/claude-api` for current Anthropic API guidance, `mcp-builder` for MCP servers, and `skill-creator` for repeatable Skill workflows.

## Workflow

1. Define the user outcome, supported inputs, failure impact, latency/cost budget, and a non-model baseline if appropriate.
2. Select model/provider based on current official documentation and measured task quality. Keep provider-specific code behind a clear boundary where portability matters.
3. For RAG, define sources, permissions, freshness, chunking/retrieval assumptions, citations, and evaluation examples. Enforce source-level access control before exposing retrieved content.
4. Define tool schemas, authorization, input/output limits, timeouts, idempotency, and safe behavior when a tool fails.
5. For agents, use the smallest role/tool set that completes the task. Set stop conditions, loop limits, handoff rules, and a human decision point for consequential actions.
6. Build representative evaluations for success, refusal, ambiguity, adversarial input, and tool failures. Track quality, latency, and cost across changes.
7. Add observability without recording secrets or unnecessary user data. Redact sensitive prompt and tool content.
8. Re-check model names, API versions, pricing, and provider capabilities against current primary documentation before implementation.

## Guardrails

Do not describe demos as production-ready without evals and operational controls. Treat retrieved text and tool output as untrusted. Never let model text directly authorize privileged actions.