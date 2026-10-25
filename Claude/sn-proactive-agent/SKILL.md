---
name: sn-proactive-agent
description: Installs, starts, and runs the Proactive Agent, recording project progress and proactively suggesting next actions at appropriate milestones.
---

# Proactive Agent

Monitors project execution, tracks ongoing tasks and milestones, and surfaces actionable recommendations when decisions or next steps are needed.

## Quick Start

```bash
python3 scripts/proactive_agent.py --status
python3 scripts/proactive_agent.py --suggest --project-dir <path>
```

## Core Workflows

1. **Progress Monitoring**: Regularly evaluates deliverables against project goals, task boards, and dependency graphs.
2. **Milestone Detection**: Triggers proactive notifications when key phases (research, design, implementation, verification) complete.
3. **Action Recommendation**: Suggests high-priority follow-up steps, missing tests, uncommitted changes, or pending reviews.
4. **Context Preservation**: Persists state across sessions in `.proactive/state.json` without cluttering codebase tracked files.
