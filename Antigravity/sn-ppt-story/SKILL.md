---
name: sn-ppt-story
description: "Presentation story and outline architect. Synthesizes user queries, source documents, and research materials into a structured, editable outline.md governing page layouts, visual cues, and slide-by-slide narrative flow. Mandatory intermediate stage before deck rendering."
---

# Presentation Story & Outline Architect

## Overview

Acts as the mandatory narrative orchestrator between deck entry (`sn-ppt-entry`) and final rendering engines (`sn-ppt-standard`, `sn-ppt-dazzle`, `sn-ppt-creative`). Translates unstructured background materials and research evidence into a rigorous slide-by-slide outline (`outline.md`).

## Narrative Standards

1. **Slide-by-Slide Outline (`outline.md`)**:
   - Each slide must define: Slide Number, Title, Layout Archetype (e.g. `Hero-Metric`, `3-Column-Feature`, `Comparison-Table`, `Timeline-Flow`), Core Message, Bullet Points, and Visual Prompt.
2. **Layout Diversity**: Avoid repetitive card layouts; cycle between high-impact stat cards, structured comparisons, process arrows, and quote blocks.
3. **Evidence Anchoring**: Carry forward concrete numbers, percentages, and citations from research packs into slide body copy.
4. **No Direct Generation Bypass**: Rendering engines must strictly ingest `outline.md` rather than improvising slide layouts from raw queries.