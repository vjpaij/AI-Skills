---
name: sn-search-finance
description: "Used to search financial markets, securities, company fundamentals, prices, candlestick charts, regulatory filings, financial news, A-share data, HK stocks, or global tickers via yfinance, mootdx, API scripts, or browser-use."
---

# Financial & Market Search

## Credential Configuration

API keys, tokens, and cookies should be placed in `.env` in the repository root (see `.env.example`). The runtime or user loads them into environment variables before execution. Scripts read credentials strictly from environment variables or explicit CLI parameters; never hardcode credentials into skill payloads, reports, logs, or git commits.

Used to retrieve securities, indices, mutual funds, financial statements, market depth, K-line candlestick charts, disclosure filings, financial news, and company fundamentals. API scripts and `browser-use` can be combined based on task needs without rigid hierarchy.

## Workflow

1. **Identify Market and Asset**: Confirm exchange (A-shares / HK stocks / US stocks / global tickers), company name, security ticker symbol, time window, and required reporting standards.
2. **Retrieve Structured Data with `scripts/finance_search.py`**:
   - `yfinance`: Queries global tickers, market quotes, balance sheets, news, and SEC filings.
   - `mootdx`: Queries TongDaXin / mainland China A-share quotes, candlestick series, and financial packs.
3. **Verify Supporting Documents**: When full-text news, interactive screeners, visual chart verification, or filing attachments are needed, use `browser-use` on Yahoo Finance, stock exchanges, investor relations portals, and disclosure pages.
4. **Preserve Exact Identifiers**: Retain ticker symbol, security code, exchange, time interval, metric methodology, and source URL in all outputs. Do not present raw script outputs as personalized financial advice.
5. **Encountering Paywalls**: If hitting a login wall, captcha, or paid subscription, halt and use alternative free, official public data sources.

## Scripts & CLI

```bash
python3 scripts/finance_search.py <query_or_ticker> [options]
```
- `--market`: Market identifier (`US`, `HK`, `CN`, `GLOBAL`)
- `--period`: Historical timeframe (`1mo`, `3mo`, `1y`, `5y`, `max`)
- `--interval`: Candlestick granularity (`1d`, `1wk`, `1mo`)
- `--type`: Data type (`quote`, `financials`, `news`, `filings`)