---
name: sn-team-harness
description: Multi-agent team harness and collaborative workspace. Coordinates shared goals, task boards, automated deliverables, and human-in-the-loop approvals across specialized agents.
---

# SenseNova Collaborative Team Harness

## Overview

A self-hosted team collaboration hub where multiple specialized AI agents and human contributors work together on complex projects with shared task boards, discussion threads, and deliverable verification.

## Architecture

1. **Shared Workspace**: Coordinates goals, backlogs, active tasks, and verified deliverables in a unified project space.
2. **Agent Role Orchestration**: Delegates discrete subtasks to specialized personas (Researcher, Architect, Coder, Reviewer, Documenter) with clear handoff contracts.
3. **Human Approval Gates**: Enforces review and sign-off on consequential operations (deletions, deployments, public releases).
4. **Persistent State**: Maintains team history, decisions, and artifacts across sessions.
