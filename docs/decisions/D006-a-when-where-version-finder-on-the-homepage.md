# D006 · A when / where / version finder on the homepage

**Status:** Accepted
**Date:** 14 Nov 2026

## Context
K04 N1: the homepage did not answer "what can I see tonight, where, for how much".

## Decision
A finder with Today / Tonight / Tomorrow / This weekend, arrondissement, and version, listing bookable showtimes. It defaults to tonight, or tomorrow once tonight is over. Other cities are removed.

## Arguments
- K04: second audit priority.
- K06 (CNC, as cited): 75.1% consider proximity.
- K02: students decide late; K03: version is a core filter.

## Risks / what would change our mind
- Since v2 the finder sits *below* the gallery (see D016).
- Arrondissement is a coarse proxy for proximity; a map or "near me" was not built.

## Where it shows
Homepage section "Séances".
