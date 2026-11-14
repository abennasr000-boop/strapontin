# D001 · Standalone prototype instead of editing Lovable

**Status:** Accepted
**Date:** 14 Nov 2026

## Context
The existing prototype lives in a Lovable project we cannot edit from here.

## Decision
Rebuild the site as one self-contained HTML file (vanilla JS, no build step), versioned in this repository and published as a private page.

## Arguments
- Judgement: the team can open, read and change one file without tooling.
- Judgement: design is expected to change again (client brief), so low cost of change matters more than production architecture.

## Risks / what would change our mind
- Not production code: no backend, no real data. If the project moves to implementation, port the design tokens and components rather than this file.

## Where it shows
`site/index.html`
