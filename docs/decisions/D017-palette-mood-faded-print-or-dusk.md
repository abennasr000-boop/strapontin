# D017 · Palette mood: Faded print or Dusk

**Status:** Open
**Date:** 14 Nov 2026

## Context
F001: the v1 palette usage was not convincing. The six colours stay; the dose and temperature are in question.

## Decision
Not decided. Both moods are implemented as a token switch (bottom-left control in the prototype and identity guide) so the client can compare on the real page.

## Arguments
- **Faded print:** warm washed cream; closest to the beige grid-sheet pin (K05); reads as paper and daylight.
- **Dusk:** cool grey-blue paper with a Blue Heaven gallery wall; reads as "l’heure bleue", the time people go out; more distinctive.
- Fixed in both: Orangeade only for booking; Raspberry and Golden Green as text accents; wine ink.

## Risks / what would change our mind
- Faded can turn flat and sepia. Dusk is cooler and less paper-like, and orange text must stay off the blue wall for contrast (3.2:1 measured).
- A third option, using Dusk only for the gallery wall on a Faded page, has not been drawn.

## Where it shows
Switch at bottom left; `:root` and `:root[data-mood="dusk"]` tokens.
