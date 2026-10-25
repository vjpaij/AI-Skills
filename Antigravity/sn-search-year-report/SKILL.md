---
name: sn-search-year-report
description: "Used to search free, official corporate annual reports, periodic financial statements, listed company disclosure filings, bond issuer reports, and overseas company statutory annual filings."
---

# Annual Report and Periodic Disclosures Search

## Credential Configuration

API keys, tokens, and cookies should be placed in `.env` in the repository root (see `.env.example`). The runtime or user loads them into environment variables before execution. Scripts read credentials strictly from environment variables or explicit CLI parameters; never hardcode credentials into skill payloads, reports, logs, or git commits.

Exclusively uses free, official, publicly accessible annual reports, financial audits, and regulatory disclosure sources. If commercial subscription databases, trial limits, paywalls, or login barriers are encountered, immediately discard that source and proceed with official regulatory exchange portals.

Always preserve company name, security ticker, reporting period, disclosure date, PDF/page URL, and regulatory authority name in outputs.

## Workflow

1. **Determine Issuer Entity**: Categorize issuer by jurisdiction (Mainland China A-share, HKEX, SEC / US listed, UK Companies House, Japan FSA, Canada SEDAR, Singapore SGX, Australia ASX).
2. **Combine `scripts/year_report_api.py` and Browser Access**:
   - Scripts are optimized for structured queries and bulk lookup.
   - `browser-use` is utilized for on-site category navigation, verification, and downloading public PDF filings.
3. **Official Exchange Repositories**:
   - US: SEC EDGAR (`10-K`, `10-Q`, `20-F`)
   - HK: HKEXnews (`Annual Report`, `Interim Report`)
   - China: Cninfo official disclosure portal
   - UK: Companies House service