---
name: sn-prepare-citations
description: Used when the final draft is complete and footnotes require post-processing: deduplicates [^key] references, converts them to [N] numbered citations, inserts L0/TOC, and appends the bibliography.
---

# sn-prepare-citations (Citation Rendering)

Processes `stitched.md` produced by `sn-deep-research`: collects `sources[]` from `evidence.json`, transforms `[^source_id]` in the main text into `[N]` numbered citations, inserts the L0 summary layer and Table of Contents (TOC), and appends the final bibliography.

## Recommended Usage (sn-deep-research v2)

```bash
python3 scripts/prepare_citations.py \
  --report <report_dir>/stitched.md \
  --evidence <report_dir>/sub_reports/d1.evidence.json <report_dir>/sub_reports/d2.evidence.json \
  --outline <report_dir>/outline.json \
  --output <report_dir>/report.md
```

## Parameters

| Parameter | Description |
|---|---|
| `--report` | Input markdown file. Usually `stitched.md` in sn-deep-research |
| `--evidence` | All `d*.evidence.json` files, used to collect source metadata and resolve claim-id leakage |
| `--outline` | Optional but recommended. Supplies L0, TOC, and header hierarchy metadata |
| `--output` | Output markdown file. Usually `report.md` in sn-deep-research |
| `--no-l0` | Disables L0 summary layer rendering |
| `--no-toc` | Disables Table of Contents (TOC) rendering |

## Processing Pipeline

1. Collects citation metadata from the `sources[]` arrays across all `evidence.json` files.
2. Normalizes and deduplicates URLs, consolidating sources sharing the same URL into a single citation number.
3. Detects `[^dN.cM]` claim-id leakage; replaces them with the corresponding `source_id` when mapped, or reports unresolved warnings if unmapped.
4. Scans for `[^source_id]` occurrences in the body, assigning numbers based on first appearance.
5. Replaces `[^source_id]` with `[N]` and removes raw footnote definition lines.
6. Inserts or aligns the L0 executive summary and TOC according to the outline.
7. Appends the formatted `## References` section.
8. Writes `report.md` and `citations.json` to the target directory.
9. Outputs structured JSON to stdout containing orphan citations, claim-id leakage, TOC, and L0 status.

## Controller Requirements

- If `orphan_citations` is non-empty: Do not deliver. Return to writer/stitcher to fix citations or remove unsupported claims.
- If `claim_id_leakage.unresolved` is non-empty: Do not deliver. Return to writer to fix `[^dN.cM]`.
- If `claim_id_leakage.resolved` is non-empty but unresolved is empty: Proceed with warning; ensure future writer outputs emit `[^source_id]`.
