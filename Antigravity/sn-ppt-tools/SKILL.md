---
name: sn-ppt-tools
description: "Auxiliary image search, web retrieval, and icon discovery tools supporting the presentation generation suite when host environment tools are unavailable."
---

# Presentation Supporting Tools

## Overview

Provides bundled fallback tools for presentation deck generation when host agent tools (native web search, image scraping, or icon retrieval) are unavailable or unconfigured.

## Capabilities

1. **Image Search (`scripts/image_search.py`)**: Retrieves high-resolution background photos, topic illustrations, and logos.
2. **Web Search (`scripts/web_search.py`)**: Queries live web sources for missing slide stats, verified quotes, and current year disclosures.
3. **Asset Normalization (`scripts/normalize_assets.py`)**: Resizes, crops, and optimizes downloaded images to standard 16:9 (1600x900 or 1280x720) aspect ratios.