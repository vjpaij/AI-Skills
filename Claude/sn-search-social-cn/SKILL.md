---
name: sn-search-social-cn
description: "Used to search Chinese social platforms. Script entries cover Bilibili videos, Zhihu Q&A, and Douyin videos; Xiaohongshu and Weibo currently use browser-use / public web fallbacks."
---

# sn-search-social-cn - Chinese Social Media Search

## Credential Configuration

API keys, tokens, and cookies should be placed in `.env` in the repository root (see `.env.example`). The runtime or user loads them into environment variables before execution. Scripts read credentials strictly from environment variables or explicit CLI parameters; never hardcode credentials into skill payloads, reports, logs, or git commits.

The scripts search three Chinese social platforms: Bilibili, Zhihu, and Douyin. Xiaohongshu and Weibo do not currently have direct script entrypoints; if research requires these sources, use `browser-use` to inspect public search pages and explicitly note the fallback origin in results.

## Platform Stability Matrix

| Script | Platform | Stability | Authentication |
|---|---|---|---|
| `bilibili_search.py` | Bilibili | High | None required (optional cookie improves quality) |
| `zhihu_search.py` | Zhihu | Medium | Requires `ZHIHU_COOKIE` |
| `douyin_search.py` | Douyin | Lower | Requires `DOUYIN_COOKIE` |
| No script | Xiaohongshu | Low | browser-use / public web fallback |
| No script | Weibo | Low | browser-use / public web fallback |

## Dependencies

Install required libraries using the skill's manifest:

```bash
python3 -m pip install -r requirements.txt
```

Do not automatically install dependencies inside scripts. If an installation fails or a package is unavailable, halt the script and switch to browser-use.

## Cookie Acquisition Guide

1. Log into the target platform in a desktop browser.
2. Open Developer Tools (F12) -> Network tab.
3. Refresh the page and copy the `Cookie` request header.
4. Set the complete cookie string into the corresponding environment variable (`ZHIHU_COOKIE` or `DOUYIN_COOKIE`).

## CLI Parameter Reference

### bilibili_search.py
```bash
python3 scripts/bilibili_search.py <query> [options]
```
- `query`: Search keyword (required)
- `--limit`, `-n`: Number of results (default: 10)
- `--cookie`: Bilibili cookie (or `BILIBILI_COOKIE` env var)
- `--order`: Sorting: empty=comprehensive, `totalrank`=best match, `click`=views, `pubdate`=latest, `dm`=danmaku, `stow`=favorites

### zhihu_search.py
```bash
python3 scripts/zhihu_search.py <query> [options]
```
- `query`: Search keyword (required)
- `--limit`, `-n`: Number of results (default: 10)
- `--cookie`: Zhihu cookie (or `ZHIHU_COOKIE` env var, required)
- `--type`: Search type: `general`, `topic`, `people`, `zvideo`

### douyin_search.py
```bash
python3 scripts/douyin_search.py <query> [options]
```
- `query`: Search keyword (required)
- `--limit`, `-n`: Number of results (default: 10)
- `--cookie`: Douyin cookie (or `DOUYIN_COOKIE` env var, required)