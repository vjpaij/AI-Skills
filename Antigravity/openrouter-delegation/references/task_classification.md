# Task Classification Reference -- Real Examples from Ladder Project

This document provides 48 real-world examples from the Ladder project's changelog, classified into TIER 1 (premium) and TIER 2 (free model). Use these as training examples for accurate task classification.

---

## TIER 1 Examples (Antigravity Premium -- 17 tasks)

| # | Version | Task Description | Classification Reason |
|:---:|:---:|:---|:---|
| 1 | v1.0.0 | Initial production release with multi-view architecture, live price engine, FX conversion, animations, Database Studio | Full-stack greenfield architecture |
| 2 | v1.1.0 | Supabase Cloud PostgreSQL integration with DDL, RLS, triggers, audit log | Database architecture + security policies |
| 3 | v1.3.0 | Universal CSV template + batch ingestion loader (376 holdings, 5,459 transactions) | Complex data pipeline with business rules |
| 4 | v1.5.0 | HoldingDetailModal (7 KPI cards, FIFO P&L, XIRR cashflows, chart timeline) | Financial algorithm design (FIFO, XIRR) |
| 5 | v1.5.1 | Trial ingestion with custom business rules (Sell All, Dividend Reinvest, Split, BONUS) | Complex financial domain logic |
| 6 | v1.6.0 | Full batch ingestion for 331 Indian Stock symbols from Excel | Large-scale data pipeline orchestration |
| 7 | v1.7.0 | US Stocks ingestion + dual currency INR/USD P&L logic | Cross-currency financial computation |
| 8 | v1.8.0 | NPS integration (14 schemes, 330 transactions, live NAV API, new view) | New asset class architecture + API integration |
| 9 | v1.8.1 | NPS NAV engine (Protean scraper + ZIP extraction + fallback strategy) | Complex scraping + error resilience |
| 10 | v1.9.0 | Bank/EPF/Liabilities overhaul (6,890 EOD records, custom chart timeline) | Multi-entity data model + computation |
| 11 | v1.9.4 | TopNavbar overhaul (theme system, avatar dropdown, toast notifications) | Multi-component cross-cutting redesign |
| 12 | v1.9.9 | Deep theme differentiation (per-theme palettes, dynamic nav highlights) | Complex CSS architecture, 6 variants |
| 13 | v2.2.0 | Dashboard upgrade (Realized P&L, USD Invested fix, FX rate fix) | Multi-endpoint financial computation |
| 14 | v2.3.0 | XIRR bug fix (78% error, category exclusion, dividend cashflows) | Complex algorithm debugging |
| 15 | v2.5.0 | Net Worth date tracking (historical portfolio valuation computation) | Time-series computation engine |
| 16 | v2.7.0 | Calendar overhaul (6,890+ records, preset pills, month filters) | Large-scale visualization architecture |
| 17 | v2.9.0 | Calendar drill-down modal (itemized asset/liability deltas) | Multi-entity delta computation |

---

## TIER 2 Examples (OpenRouter Free Model -- 31 tasks)

| # | Version | Task Description | Classification Category |
|:---:|:---:|:---|:---|
| 1 | v1.0.1 | Created master LADDER.MD context document | Documentation |
| 2 | v1.0.2 | Configured .agents/AGENTS.md workspace rules | Config file creation |
| 3 | v1.1.1 | Added columns to transactions and holdings tables | Mechanical DDL |
| 4 | v1.1.2 | Simplified transactions table (removed tax breakdown columns) | Mechanical DDL |
| 5 | v1.1.3 | Updated Supabase endpoint URL in .env | Config edit |
| 6 | v1.1.4 | Updated AGENTS.md with Git release rules | Documentation |
| 7 | v1.2.0 | Security audit + README/CHANGELOG sync + git push | Documentation + Git ops |
| 8 | v1.2.1 | Updated AGENTS.md to preserve branches | Documentation |
| 9 | v1.3.1 | Cleared sample JSON files + restart server | File operations |
| 10 | v1.4.0 | Added Status Filter Tabs + default sort across 3 views | Pattern replication |
| 11 | v1.4.1 | Purged data from Supabase tables | Mechanical SQL |
| 12 | v1.4.2 | Added symbol/name columns + backfill via JOIN | Mechanical DDL |
| 13 | v1.7.1 | Dual currency toggle in HoldingDetailModal | Pattern extension |
| 14 | v1.7.2 | Removed redundant column + added FX rate badge | Simple component edit |
| 15 | v1.8.2 | Historical NAV charting (followed existing chart pattern) | Pattern replication |
| 16 | v1.9.1 | Simplified HoldingDetailModal for Bank/EPF/Liabilities | Label/column removal |
| 17 | v1.9.2 | Updated Sidebar branding (icon CSS + text styling) | CSS/Styling |
| 18 | v1.9.3 | Search autocomplete dropdown | Simple component edit |
| 19 | v1.9.5 | Clean Light mode CSS overrides | CSS/Styling |
| 20 | v1.9.6 | Light mode subcard contrast fixes + button move | CSS/Styling |
| 21 | v1.9.7 | Navigation cleanup (rename labels, change colors) | Text/Label changes |
| 22 | v1.9.8 | Add/remove themes (Warm Sand, Sage Mint) | Pattern replication |
| 23 | v2.0.0 | Standardize light mode navbar buttons across themes | CSS/Styling |
| 24 | v2.1.0 | Floating card layout + collapsible sidebar | Simple component edit |
| 25 | v2.4.0 | Calendar date range picker + Y-axis auto-scaling | Pattern replication |
| 26 | v2.6.0 | Chart precision (2 decimal, linear segments, pie interactions) | Formatting/Precision |
| 27 | v2.8.0 | Calendar UI cleanup (remove clutter, format dates) | Text/Label changes |
| 28 | v3.0.0 | Calendar polish (padding, date format, theme matching) | CSS/Styling |
| 29 | v3.2.0 | Decimal alignment + Portal modal fix | Simple bug fix |
| 30 | v3.3.0 | Calendar accordion + formatting fixes | Simple component edit |
| 31 | v3.4.0 | Revert accordion + spacing/theme polish | CSS/Styling |

---

## Classification Decision Tree

```
Is the task...

1. Creating something entirely new (new component, new API, new schema)?
   YES -> TIER 1
   
2. Involving complex algorithms (XIRR, FIFO, currency math)?
   YES -> TIER 1
   
3. Spanning 3+ interdependent files?
   YES -> TIER 1
   
4. Requiring debugging with unclear root cause?
   YES -> TIER 1
   
5. Modifying database triggers, RLS policies, or auth logic?
   YES -> TIER 1

6. Involving only 1-2 files with clear, well-scoped changes?
   YES -> TIER 2
   
7. Following an existing pattern already in the codebase?
   YES -> TIER 2
   
8. Purely CSS/styling with no logic changes?
   YES -> TIER 2

9. Text/label/icon swap with no logic changes?
   YES -> TIER 2
   
10. Documentation or config file edit?
    YES -> TIER 2

AMBIGUOUS -> Default to TIER 1 (premium handles it)
```
