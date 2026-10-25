---
name: sn-search-social-en
description: "Used to search English social platforms, including Reddit discussions, Twitter/X posts, and YouTube videos."
---

# sn-search-social-en - English Social Media Search

## Credential Configuration

API keys, tokens, and cookies should be placed in `.env` in the repository root (see `.env.example`). The runtime or user loads them into environment variables before execution. Scripts read credentials strictly from environment variables or explicit CLI parameters; never hardcode credentials into skill payloads, reports, logs, or git commits.

Searches three major English social platforms: Reddit, Twitter/X, and YouTube.

## Available Scripts

| Script | Platform | Purpose | API Key / Token |
|---|---|---|---|
| `reddit_search.py` | Reddit | Posts and thread discussions | None required |
| `twitter_search.py` | Twitter/X | Tweet search | Requires `TIKHUB_TOKEN` |
| `youtube_search.py` | YouTube | Video tutorials and search | Requires `YOUTUBE_API_KEY` |

## Dependencies

```bash
python3 -m pip install -r requirements.txt
```

## CLI Reference

### reddit_search.py
```bash
python3 scripts/reddit_search.py <query> [options]
```
- `query`: Search keyword (required)
- `--limit`, `-n`: Number of results (default: 10)
- `--subreddit`, `-r`: Filter by subreddit (e.g. `python`, `machinelearning`)
- `--sort`: Sorting mode: `relevance`, `hot`, `top`, `new`, `comments`
- `--time`, `-t`: Time filter: `hour`, `day`, `week`, `month`, `year`, `all`

### twitter_search.py
```bash
python3 scripts/twitter_search.py <query> [options]
```
- `query`: Search keyword (required)
- `--limit`, `-n`: Number of results (default: 10)
- `--token`: TikHub Token (or `TIKHUB_TOKEN` env var, required)

### youtube_search.py
```bash
python3 scripts/youtube_search.py <query> [options]
```
- `query`: Search keyword (required)
- `--limit`, `-n`: Number of results (default: 10)
- `--api-key`: YouTube API Key (or `YOUTUBE_API_KEY` env var, required)