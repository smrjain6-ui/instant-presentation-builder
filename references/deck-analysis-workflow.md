# Deck Analysis Workflow

## Goal
Extract usable style signals from reference consulting decks before generating new slides.

## Inputs
- Template ZIP files in `assets/`
- User outline/topic

## Procedure
1. Run `scripts/extract_design_cues.py --assets-dir assets --out references/template-style-summary.md`.
2. Read the generated summary and shortlist 1-2 lead templates.
3. For each shortlisted template, capture:
   - primary + secondary + accent colors,
   - header and body typeface candidates,
   - typical slide count and layout density,
   - recurring visual pattern (icons, circles, framed images, geometric separators).
4. Pick one motif and keep it fixed across the whole generated deck.
5. Build a slide blueprint that mirrors consulting deck pacing:
   - opening framing slide,
   - analytical middle section,
   - recommendation and roadmap close.

## Decision Rules
- Prefer legibility over decorative complexity.
- Reject palettes with low text contrast on backgrounds.
- If multiple template families conflict, preserve one family end-to-end instead of blending many styles.
- Use accent color only for emphasis (key numbers, decisions, calls to action).

## Output
Before generating slides, write a brief style plan with:
- chosen template family,
- palette,
- font pair,
- motif choice,
- layout mix target (for example: 3 two-column, 2 image-led, 2 matrix/grid, 1 timeline).
