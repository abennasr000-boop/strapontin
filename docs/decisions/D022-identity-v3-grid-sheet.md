# D022 · Identity v3: the grid sheet

**Status:** Accepted (direction)
**Date:** 14 Nov 2026

## Context
F002: v2 was too textured and its type felt weak. The client pointed to one mood-board pin (K05, pin 6) as the model for fonts and overall design.

## Decision
Sage paper #D8D9CC, near-black wine ink, visible hairline grid, no grain, no frames, no shadows on content. Playfair Display capitals for titles, Instrument Serif italic for one word per title and for names, Archivo (normal and extended) for all information. Orangeade only for booking. The seat sketch sits in a rounded square like the monogram on the reference. This also closes D017: the palette mood is neither Faded print nor Dusk.

## Arguments
- F002 points 1, 3, 4, 8 and the attached reference.
- K05 pin 6: wide high-contrast serif capitals, narrow italic inside the title, small extended sans labels, hairline cells.
- Judgement on fonts: the reference face is commercial; Playfair Display + Instrument Serif are the closest open-licence pair we found. A licensed face could replace them later.
- Judgement: one sans for every fact (times, prices, labels) is clearer than v2’s typewriter face.
- K07: contrast computed from hex values: ink/paper 12:1, muted text 5.6:1, Orangeade/paper 4.7:1.

## Risks / what would change our mind
- The earlier keywords "dreamy, bohemian, film grain" (F001) are now carried only by the italic, the paper tone and the posters. If the client misses them, reintroduce one element at a time.
- Uppercase long French titles wrap to three lines in two-column phone cells.
- The logo drawing remains a sketch.

## Where it shows
`site/index.html`, `site/identity.html`.
