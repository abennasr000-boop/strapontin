# D023 · Real film posters in the internal mockup

**Status:** Accepted for internal review only
**Date:** 14 Nov 2026

## Context
F002 point 5: the client needs a real view with real, critic-awarded art-house films and their posters, for the mockup only.

## Decision
The catalogue now lists fifteen real films (title, director, year, running time, one factual award or selection each) and two fictional plays. Posters are looked up on Wikipedia at view time by the browser and cached in the browser; no image file is stored in this repository. Venues, showtimes, prices and special events remain fictional. Invented critics’ quotes were removed.

## Arguments
- F002 point 5.
- Judgement: hot-linking for an internal design review avoids copying copyrighted files into the project.
- Judgement: with real films, fabricated press quotes or fictional guest appearances by real people would be misleading, so they were removed or replaced by fictional hosts (ciné-club, debates).

## Risks / what would change our mind
- **Rights are not cleared.** Do not publish this mockup publicly or present the posters as licensed.
- The published review page (claude.ai artifact) blocks outside images, so it shows typographic tiles; the real posters are visible when the site is run locally.
- Wikipedia poster files are about 250 px wide and look soft at large sizes.
- Film facts were written from memory and should be checked before any external use.
- Depends on an outside service at view time; offline, tiles fall back to typography.

## Where it shows
`W` data and `loadPosters()` in `site/index.html`.
