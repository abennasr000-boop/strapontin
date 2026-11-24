# D032 · Keyboard focus ring and dialog behaviour

**Status:** Accepted
**Date:** 24 Nov 2026

## Context
F007 gap 2: custom-styled filters might not show standard keyboard focus. D019 asked for "visible focus" and used a 2px orangeade outline. On dark posters it was nearly invisible. The filters' native selects are transparent (D034), so the select's own focus ring could not be seen. Panels (My list, the film sheet) let Tab wander into the page behind and did not return focus on close.

## Decision
- **One focus style everywhere:** a 3px ink outline 2px outside the control, with a 2px light halo (#F6F6EF) between control and outline.
  - The ink shows on paper (12.43:1) and the halo shows on dark posters (16.34:1), so the ring is visible on any background (2.4.13).
  - It appears only for keyboard focus (`:focus-visible`).
- **Filters:** when the hidden select has keyboard focus, the visible filter pill shows the ring (`:has(select:focus-visible)`). Browsers without `:has` fall back to `:focus-within`.
- **Gallery tiles:** the whole tile gets the ring when its title button is focused, not the small title.
- **Panels (My list, film sheet):**
  - they are `role="dialog"` with `aria-modal`;
  - focus moves into the panel when it opens;
  - Tab and Shift+Tab cycle inside it;
  - Escape closes it;
  - focus returns to the button that opened it;
  - the header, page, footer and dock are `inert` while it is open.
- **Keyboard-changed filters keep focus:** they announce their result through D031's status region and never move focus.

## Arguments
- F007 gap 2; K08 (2.4.13, 3.2.2, 1.4.11).
- Judgement: one ring with two tones avoids per-background focus styles that drift apart over time.

## Risks / what would change our mind
- The halo is a `box-shadow`, so it can be clipped by a parent with `overflow:hidden`. Watch new components.
- `inert` is recent in Safari (15.5+); older browsers still get the Tab cycle.

## Where it shows
`:focus-visible` rules, `.dsel:has(select:focus-visible)`, `.t:has(.sc h3 button:focus-visible)`, the Tab handler, `restoreFocus()` and `layer()` in `site/index.html`.
