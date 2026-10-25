---
name: sn-da-non-spreadsheet-analysis
description: "Document parsing and data analysis engine for Word (.docx/.doc), PDF (.pdf), and PowerPoint (.pptx/.ppt) files. Covers full text extraction, table digitization, visual chart understanding, formatting checks, and cross-document comparison."
---

# Non-Spreadsheet Document Analysis (Word / PDF / PPT)

## Overview

High-precision parsing and analytical engine for unstructured document formats. Extracts tabular numbers, text hierarchies, embedded figures, and structural metadata across business proposals, contracts, academic papers, and pitch decks.

## Capabilities

1. **Word Documents (.docx / .doc)**: Extracts headings, paragraphs, formatted tables, revision history, callout boxes, and font/color formatting.
2. **PDF Documents (.pdf)**: High-fidelity layout parsing, OCR digitization of scanned pages, multi-column reading, table boundary detection, and cross-page table reconstruction.
3. **PowerPoint Decks (.pptx / .ppt)**: Slide-by-slide text extraction, shape hierarchy, embedded tables, speaker notes, and graphic asset indexing.
4. **Cross-Document Comparative Analysis**: Aligns clauses, financial tables, and key performance metrics across multiple documents to identify discrepancies, updates, and omissions.

## Usage

```bash
python3 scripts/document_analysis.py --file <path_to_document> [options]
```
- `--output`: Export format (`json`, `markdown`, `csv`)
- `--extract-tables`: Output tables as individual CSV / DataFrames
- `--extract-images`: Extract embedded graphics and charts to an assets directory