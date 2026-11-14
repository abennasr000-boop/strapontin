# D020 · Documentation system

**Status:** Accepted
**Date:** 14 Nov 2026

## Context
F001 point 8: past and future decisions need written arguments and sources, and the knowledge used must be traceable to concrete effects.

## Decision
Knowledge notes, decision records, feedback log and a contribution matrix, in Markdown in this repository (see `docs/README.md`).

## Arguments
- Judgement: plain files next to the prototype stay in sync with it and are readable on GitHub without tools.
- Decisions are never rewritten, only superseded, so the reasoning history survives identity changes (the client expects more).

## Risks / what would change our mind
- Needs discipline: a decision made in a meeting and not written here will be lost.

## Where it shows
`docs/`.
