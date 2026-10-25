---
name: sn-search-market-cn
description: "Use when researching China market, industry, macro, trade, procurement, listed-company disclosure, regulation, IP, healthcare, logistics, energy, environment, or industrial-operation information using free official sources with no registration, no API key, and no cryptocurrency data."
---

# China Market and Business Search

## Credential Configuration

API keys, tokens, and cookies should be placed in `.env` in the repository root (see `.env.example`). The runtime or user loads them into environment variables before execution. Scripts read credentials strictly from environment variables or explicit CLI parameters; never hardcode credentials into skill payloads, reports, logs, or git commits.

Exclusively uses official Chinese public and governmental portals. Do not access unauthorized commercial databases. If registration gates, captchas, API keys, or paywalls are encountered, immediately abandon that source and use public government portals.

## Workflow

1. **Define Research Target**: Specify industry, enterprise, administrative region, time period, metric definition, and required evidence type.
2. **Regulatory & Disclosure Filings**: Retrieve A-share announcements, annual reports, and regulatory inquiry letters via API scripts and official Cninfo exchange portals.
3. **Macroeconomic & Industrial Metrics**: Utilize `browser-use` to access official statistics (National Bureau of Statistics, Ministry of Commerce, General Administration of Customs, Ministry of Industry and Information Technology).
4. **Procurement & Government Bidding**: Check public tender and government procurement databases for contract awards, bidder registries, and supply chain pricing.
5. **Retain Full Traceability**: Include official source URLs, statistical indicator scopes, reporting periods, and agency names in all conclusions.