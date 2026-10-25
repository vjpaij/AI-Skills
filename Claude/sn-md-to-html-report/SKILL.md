---
name: sn-md-to-html-report
description: Restructures and designs Markdown reports, research notes, industry analyses, strategy memos, and whitepapers into publication-ready, self-contained standalone HTML thematic pages with responsive navigation, elegant typography, and evidence charts.
---

# Markdown to Thematic HTML Report

## Overview

Transforms technical, financial, and strategic Markdown deliverables into polished, executive-ready HTML presentation pages. Designed for high readability, visual hierarchy, and effortless sharing.

## Core Rules

1. **Plan Before Authoring**: Always produce a preliminary structural outline (`plan.md`) mapping out sections, visual callouts, KPI summary cards, and chart placements before rendering the final HTML.
2. **Preserve Fact Strength**: Retain all factual claims, numerical precision, methodology caveats, and source citations from the original Markdown source without dilution.
3. **Self-Contained Architecture**: Embed CSS, SVG icons, and typography within a single standalone HTML file requiring zero external CDN dependencies for offline viewing.
4. **Responsive Layout**: Provide sticky sidebar navigation, interactive Table of Contents, dark/light contrast support, and mobile-friendly viewports.

## Workflow

```bash
python3 scripts/md_to_html.py --input <path_to_report.md> --output <path_to_output.html> --theme corporate
```
