---
name: sn-ppt-creative
description: "Use when a prepared PPT task with a current outline.md should be generated as an image-first presentation with one 16:9 image per slide and optional PPTX packaging."
metadata:
  project: SenseNova-Skills
  tier: 1
  category: scene
  user_visible: false
  triggers:
    - "sn-ppt-creative"
---

# sn-ppt-creative (Visual Presentation Deck)

Translates public Story outlines into a suite of 16:9 full-page visual slides. `Creative` is responsible for visual styling and slide rendering, not research or outline generation (which are handled by `sn-ppt-entry` and `sn-ppt-story`).

## Prerequisites and Directory Boundaries

The following files must exist:
- `<DECK_DIR>/task_pack.json`
- `<DECK_DIR>/info_pack.json`
- `<DECK_DIR>/outline.md`
- `task_pack.choices.output == "creative"` (or legacy `ppt_mode == "creative"`)

`DECK_DIR` must use the absolute path from `task_pack.deck_dir`. Never write generated files to the user's home directory or workspace root.

## Execution Workflow

1. **Verify Story Outline**: Read `<DECK_DIR>/outline.md`. Ensure slide count, titles, copy, and layout directives are complete.
2. **Setup Image Tools**: Verify `scripts/image_search.py` and `scripts/generate_images.py`.
3. **Generate Visual Slides**: For each slide in `outline.md`:
   - Generate visual asset adhering to the 16:9 aspect ratio.
   - Compose slide layout with overlay typography.
   - Save rendered slide to `<DECK_DIR>/slides/slide_{i}.png`.
4. **Compile Presentation**:
   - Produce standalone `present.html` embedding high-res visual slides.
   - If PPTX output is requested (`task_pack.choices.static_postprocess` contains `pptx`), export the final PPTX deck via `scripts/export_pptx.py`.
5. **Output Verification**: Confirm all slide images, `present.html`, and PPTX packages are written to `DECK_DIR`.