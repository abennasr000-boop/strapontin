# D028 · Google Analytics 4 tag on the prototype, behind cookie consent

**Status:** Accepted for the test
**Date:** 24 Nov 2026

## Context
Clarity (D027) gives recordings and heatmaps. We also want audience numbers (visits, pages, sources) in a GA4 property.

## Decision
The GA4 `gtag.js` snippet sits in the same `<script>` block as Clarity in the `<head>` of `site/index.html`, wrapped in `loadGA4()`. It uses exactly the same gating as Clarity (D019):
- Nothing from Google loads before a choice is made.
- "Accepter" (or a stored "Accepter" on a later visit) calls `loadGA4()`, which loads `gtag.js` with analytics storage granted and all ad signals denied.
- "Refuser" never loads it; a later refusal calls `revokeGA4()`, which sets `ga-disable-<ID>` and updates consent to denied.
- The measurement ID is the `GA4_ID` constant: `G-437TB35RBD`.

Keep it in every version of the prototype pages, like Clarity.

## Risks / what would change our mind
- Not legally reviewed. GA4 data retention and Google signals are set in the GA4 admin, not here.
- Local runs (`localhost:4173`) also send hits after "Accepter"; filter them in GA4 or restrict to the Vercel domain.
- Only `site/index.html` carries it, as with Clarity.

## Where it shows
`site/index.html`, `<head>`. Nothing visible in the interface.
