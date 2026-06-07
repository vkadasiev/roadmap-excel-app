# TASKS

## Current State

- The UI refresh has been published to `index.html` on `main`.
- `index-ui-preview.html` still exists as a review/reference copy.
- Live site: `https://vkadasiev.github.io/roadmap-excel-app/`
- Preview/reference page: `https://vkadasiev.github.io/roadmap-excel-app/index-ui-preview.html`

## Latest Design Decisions

- Minimal white UI based on the provided ChatGPT-like design guide.
- Product logos remain colored.
- Roadmap cards keep colored vertical accent stripes.
- Card accent stripe is implemented with `.item::before`, not `border-left`, to avoid diagonal/internal corner artifacts.
- Product header cell (`Продукт`) has white background and typography aligned with month headers.
- Info button:
  - light gray background restored;
  - no text glyph `i`;
  - icon is drawn with CSS pseudo-elements;
  - equal top/right inset;
  - radius is derived from card radius/inset.
- Latest grid tokens:
  - `--line: #cfcfcf`
  - `--soft-line: #dddddd`
- Single-date roadmap cards use a tighter desktop width calculation (`maxSingleWidth: 300`, title wrap divisor `3.6`) so long tasks no longer leave a large empty area inside the card; the short-card minimum was rolled back.
- Cards on white roadmap lanes use the same `--panel` gray as alternate lane bands; cards on gray lanes remain white for contrast.
- Reason modal was restyled: no `<pre>` monospace block; reason text now renders as paragraphs/list items inside a quiet gray body with a neutral left rule and CSS-drawn close icon.

## Sub-Agent Review

- Independent review score: `7/10`.
- Main critique: good direction, but continue watching consistency so the UI feels like one system, not a series of local tweaks.
- Accepted review points already addressed:
  - no heavy shadows/gradients;
  - lighter card borders;
  - unified focus-visible treatment;
  - CSS-only info icon retained;
  - table lines adjusted to be readable but not too heavy.

## Next Work Order

1. Verify the live site visually after GitHub Pages finishes building.
2. Verify core behavior:
   - Google Sheet auto-load;
   - Excel upload;
   - sample button;
   - print/PDF;
   - reason modal from info buttons.
3. If live version is approved, decide whether to keep or remove `index-ui-preview.html`.
4. Close or ignore obsolete PR `#1` if it no longer matches the direct-main publication workflow.
5. Continue future UI tweaks directly in `index.html`; mirror to `index-ui-preview.html` only if a separate preview is needed again.

## Guardrails

- Do not create another parallel demo app.
- Do not change Excel/Google Sheet parsing unless explicitly requested.
- Do not remove product colors unless explicitly requested.
- Avoid heavy shadows, gradients, pill radii, and overly saturated full-card fills.
- Prefer small CSS-only refinements over large rewrites.
