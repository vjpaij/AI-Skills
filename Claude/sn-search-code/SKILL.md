---
name: sn-search-code
description: "Used to search for code examples, open-source repositories, GitHub Issues, technical Q&A, developer discussions, and HuggingFace models/datasets/Spaces."
---

# Code and Technical Search

## Credential Configuration

API keys, tokens, and cookies should be placed in `.env` in the repository root (see `.env.example`). The runtime or user loads them into environment variables before execution. Scripts read credentials strictly from environment variables or explicit CLI parameters; never hardcode credentials into skill payloads, reports, logs, or git commits.

## Core Capabilities

1. **GitHub Repositories and Issues**: Searches repositories, pull requests, release notes, and technical discussions using GitHub API and public search.
2. **Developer Communities**: Searches technical discussions and solution threads on StackOverflow, developer forums, and official docs.
3. **HuggingFace Models and Datasets**: Queries model cards, benchmark leaderboards, dataset configurations, and Spaces via `huggingface_hub`.
4. **Code Snippets and Examples**: Locates minimal reproducible implementations, API usage patterns, and configuration templates.

## CLI Usage

```bash
python3 scripts/code_search.py <query> [options]
```
- `--source`: Platform filter (`github`, `stackoverflow`, `huggingface`, `all`)
- `--language`: Programming language filter (e.g. `python`, `typescript`, `rust`, `go`)
- `--limit`: Result count (default: 10)