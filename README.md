# Instant Presentation Builder

Create professional PowerPoint decks from a topic or outline using consulting-style design cues.

## What This Skill Does

`Instant Presentation Builder` helps Codex:

- Analyze reference consulting templates to extract visual direction
- Turn outline sections into a slide-by-slide blueprint
- Generate high-impact decks with consistent motif, typography, and color system
- Ensure each slide includes a visual element (not text-only)
- Run a QA pass for readability, consistency, and layout quality

## Trigger / Description

Create professional slide decks from outlines or topics. Use the PPTX skill to turn outlines into slides with high-impact design.

## Included in This Repo

- `SKILL.md` — core skill instructions and workflow
- `agents/openai.yaml` — UI metadata for skill picker/chips
- `scripts/extract_design_cues.py` — analyzes template ZIPs and outputs style cues
- `references/deck-analysis-workflow.md` — template analysis process
- `references/slide-design-checklist.md` — slide QA and design checklist
- `references/template-style-summary.md` — generated style summary
- `assets/*.zip` — consulting/pitch deck templates used as design references

## Design Rules Enforced

- 1 dominant hue (60–70% visual weight), plus support tones and a sharp accent
- One repeated visual motif across the deck
- Distinctive header font + clean body font
- Typical sizing:
  - Titles: 36–44 pt
  - Body: 14–16 pt
  - Labels/Captions: 11–13 pt
- Varied layouts: two-column, 2×2 grid, half-bleed, split comparison
- One clear message per slide + at least one visual per slide

## Quick Usage

1. Provide topic or outline, audience, and objective.
2. Analyze templates first (style extraction), then choose one lead style family.
3. Build the slide blueprint from sections/key points.
4. Generate PPTX with consistent palette, motif, and layout rhythm.
5. QA and revise.
  --assets-dir assets \
  --out references/template-style-summary.md
