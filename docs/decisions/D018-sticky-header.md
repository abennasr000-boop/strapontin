# D018 · Sticky header

**Status:** Accepted
**Date:** 14 Nov 2026

## Context
K04 N3 asked for a sticky header. In v1 it was coded as sticky but did not stick (F001).

## Decision
The header stays visible while scrolling.

## Arguments
- K04 N3: search and navigation must stay reachable on a long page.
- Cause of the v1 bug, for the record: the header sat inside a wrapper only as tall as the header, so it had no room to stick. The wrapper is now layout-transparent.

## Risks / what would change our mind
- Takes vertical space on small phones; the reassurance strip is therefore not sticky.

## Where it shows
Header.
