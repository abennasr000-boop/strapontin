# D024 · Home gallery layout: mosaic, drift or accordion

**Status:** Decided: A · Mosaïque (client, 14 Nov 2026), built into `site/index.html`
**Date:** 14 Nov 2026

## Context
F003: the v3 gallery (D021) works but its even, ruled grid feels rigid. The client wants a lighter, full-screen, unevenly proportioned gallery with text on the images, implied rather than drawn lines, and a click that enlarges a film in the middle while the others shrink.

## Options (all in `site/propositions.html`, 11 real films showing "today")
| | A · Mosaïque | B · Dérive | C · Accordéon |
|---|---|---|---|
| Idea | Full-bleed asymmetric grid, softened Mondrian; thin paper gaps are the only lines; text lies on the image | Uncropped posters staggered on the paper with a lot of air; captions aligned to edges draw the lines | Vertical slices of posters; the chosen one opens in the middle, the others fold |
| On click | The film takes the centre with award, synopsis, showtimes and booking; the others shrink and re-pack around it | The film comes forward large in the middle; the wall recedes and fades | The slice widens to half the screen with all details |
| Strength | Closest to the brief; dense discovery; strong on phones (2-up with big tiles) | Lightest and calmest; posters shown whole; most "gallery" | Most playful and distinctive; great on desktop |
| Weakness | Posters are cropped; text needs a dark gradient behind it for contrast; needs high-resolution artwork | Shows fewer films per screen; text is under, not on, the image | Titles read vertically; slices show little of each poster; weakest on phones |

## Arguments to weigh
- K02 / F002: the goal is playful discovery on phones with clear facts. A and B both keep time, venue and price visible on every film; C hides venue and price until opened.
- K03: uncertainty avoidance favours A and B for the same reason.
- K07 accessibility: text over images (A, C) must keep 4.5:1 contrast; the gradient does this but costs some lightness. B has no such issue.
- Judgement: A matches the client's description most closely; B best matches "lightness and space". A hybrid (A's uneven sizes and click behaviour with B's air and uncropped posters) is possible.

## Next
Client chooses; the choice is then built into `site/index.html` with the existing filters, list view and booking flow, and D021 is updated.

## Outcome (F004, 14 Nov 2026)
The client chose A and asked for: larger, slightly uneven margins; an opened film that adapts to the screen and stays fully visible; shading behind the text on posters; and a clear place for filters, search and buttons.

Built: uneven tile sizes with wider, slightly varied gaps; a dark gradient and soft text shadow behind poster text; the opened film sized from the viewport and scrolled just under the filter line (side by side on desktop, stacked on phones) while the others shrink to small tiles; filters as a single text line (underlined active state, no drawn boxes) with Galerie / Liste at the right.

Still open: the type filter is hidden on phones for lack of room; the mockup clock is held at 16h00 in the evening so "today" stays full; poster files are low resolution; nothing is user-tested.
