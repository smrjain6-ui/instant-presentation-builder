---
name: instant-presentation-builder
description: Create professional slide decks from outlines or topics. Use the PPTX skill to turn outlines into slides with high-impact design.
---

# Instant Presentation Builder

## Overview

Create polished business presentations from a topic or text outline.
Start from reference consulting decks, extract design cues, and apply those cues consistently to generated slides.

## Workflow
1. Intake input.
2. Analyze reference decks to extract style cues.
3. Build slide blueprint from the outline.
4. Generate the deck with consistent design language.
5. Run QA and revise.

## 1) Intake Input
- Ask for either:
  - a topic, audience, and objective, or
  - a sectioned outline with key points.
- Confirm target slide count and speaking context (internal strategy readout, investor pitch, client workshop, board update).
- If the user does not provide slide count, default to 10-12 slides.

## 2) Analyze Reference Decks First
- Use the PPTX editing workflow mindset:
  - inspect visual structure from reference files
  - unpack the presentation internals when needed
  - edit content while preserving layout system
  - clean up and repack a valid output deck
- Use deck templates in `assets/` as primary design references.
- Run `scripts/extract_design_cues.py` to get a baseline report for available template decks.
- Extract and commit to:
  - color palette (dominant + support + accent),
  - font pairing (header + body),
  - slide rhythm (title slides, section breaks, data slides),
  - recurring visual motif (shape treatment, icon framing, image masking style).
- If cues conflict across templates, choose one lead template and one backup template, then document the decision in your working notes.

## 3) Convert Outline to Slide Blueprint
- Parse the outline into sections and key points.
- Map sections into slide intents such as:
  - context/problem,
  - analysis/framework,
  - recommendation/options,
  - roadmap/next steps.
- Ensure each slide has one core message.
- Assign a visual type to every slide before authoring:
  - chart,
  - icon cluster,
  - timeline,
  - process diagram,
  - comparison table,
  - image-led layout.

## 4) Apply Design Rules While Generating
- Use a bold, topic-appropriate palette:
  - 1 dominant hue for 60-70% of visual weight,
  - 1-2 supporting tones,
  - 1 sharp accent for emphasis.
- Use one consistent visual motif across slides (for example rounded image frames or icons in colored circles).
- Include a visual element on every slide. Avoid text-only slides.
- Vary composition with layouts like:
  - two-column,
  - 2x2 grid,
  - half-bleed image,
  - left text + right diagram.
- Use a distinctive header font paired with a clean body font.
- Default typography sizes:
  - title: 36-44 pt,
  - body: 14-16 pt,
  - supporting labels/captions: 11-13 pt.
- Keep text concise:
  - title + subtitle + 3-5 bullets maximum for text-heavy slides,
  - prefer short labels attached to visuals instead of paragraphs.

## 5) QA and Revision
- Review the generated PPTX slide-by-slide for:
  - consistent palette usage,
  - consistent font pairing and sizes,
  - alignment and spacing,
  - visual presence on every slide,
  - contrast/readability,
  - layout variety.
- Fix issues immediately, then re-check the full deck once more before final delivery.
- If there is visual drift from reference style, tighten the motif and color distribution first.

## Examples

### Example Input 1
User input outline:
- Title: AI Copilot Rollout for Enterprise Support
- Audience: VP Support + Ops Directors
- Sections:
  - Current pain points and ticket backlog trend
  - Opportunity sizing and ROI
  - Rollout phases and owners
  - Risks and mitigations
  - 90-day action plan

Expected output:
- 11-slide consulting-style deck
- Visual mix: trend chart, ROI waterfall, phased timeline, RACI-style ownership grid, risk heatmap
- Dominant cool tone with high-contrast accent for decisions and KPIs

### Example Input 2
User input outline:
- Topic: Market Entry Strategy for SMB Payroll SaaS
- Audience: Executive leadership
- Sections:
  - Market landscape and segmentation
  - Competitor comparison
  - Positioning options
  - Go-to-market plan by quarter
  - Investment ask and milestones

Expected output:
- 12-slide strategy deck
- Visual mix: TAM/SAM/SOM sizing graphic, competitor matrix, positioning map, quarterly roadmap, milestone dashboard
- Bold motif repeated across slides with clear section transitions

## Assets and Dependencies

### Assets
- Keep consulting template ZIPs in `assets/` and treat them as style references.
- Unzip templates locally when needed for structure inspection or slide reuse.

### Suggested dependencies
- JavaScript:
  - `pptxgenjs` for programmatic deck generation
- Python (optional, for analysis/prep workflows):
  - `python-pptx`
  - `lxml`
  - `Pillow`
  - `pandas`

## Reference Files
- Read `references/deck-analysis-workflow.md` for cue extraction and template triage.
- Read `references/slide-design-checklist.md` for per-slide quality and consistency checks.
