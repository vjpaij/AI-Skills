---
name: sn-search-social-media
description: "Used to search social communities, breaking news trends, encyclopedic knowledge, developer ecosystems, and public technical discussions across multiple social networks."
---

# Unified Social Media and Trends Search

## Credential Configuration

API keys, tokens, and cookies should be placed in `.env` in the repository root (see `.env.example`). The runtime or user loads them into environment variables before execution. Scripts read credentials strictly from environment variables or explicit CLI parameters; never hardcode credentials into skill payloads, reports, logs, or git commits.

## Workflow

1. **Multi-Platform Query Decomposition**: Deconstruct research topics into platform-specific search terms, hashtags, and entity names.
2. **Cross-Platform Aggregation**: Combine Reddit discussions, technical forums, X/Twitter commentary, and video tutorials to evaluate sentiment, emerging consensus, and counter-arguments.
3. **Evidence Verification**: Cross-reference social media claims against primary sources, official documentation, and verified benchmark suites before including them in synthesized reports.
4. **Output Synthesis**: Present discussion summaries with platform citations, upvote/engagement context, publication timestamps, and direct reference links.