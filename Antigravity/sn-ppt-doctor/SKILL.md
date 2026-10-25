---
name: sn-ppt-doctor
description: "Diagnostic and troubleshooting assistant for presentation deck generation pipelines, Playwright/Chromium rendering, HTML-to-PPTX exporters, and local Workbench servers."
---

# Presentation Tool Diagnostics (sn-ppt-doctor)

## Overview

Runs automated diagnostic checks on local dependencies, headless browser environments, and rendering pipelines required by the SenseNova PPT suite.

## Health Checks

1. **Browser Runtime**: Verifies Playwright and Chromium installations for high-res slide rendering:
   ```bash
   python3 scripts/doctor.py --check-browser
   ```
2. **Export Dependencies**: Validates python-pptx, Pillow, and LibreOffice/Soffice configurations for PPTX compilation.
3. **Workbench Connectivity**: Checks local port availability (default 18888) for live preview servers.
4. **Asset Directory Health**: Verifies read/write permissions on deck cache directories and template repositories.