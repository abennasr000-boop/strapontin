# D027 · Microsoft Clarity tracking tag stays on the prototype

**Status:** Accepted for the test; **consent handling open**
**Date:** 16 Nov 2026

## Context
The prototype is published on Vercel for testing. We want session recordings and heatmaps to see how test visitors use it, so we added a Microsoft Clarity tag (project ID `zeku8v4fl1`).

## Decision
The Clarity snippet sits in the `<head>` of `site/index.html`, right after the `<title>`. It stays in every future version of the prototype pages (copy it into any new or replaced page that visitors will use), and is kept when files are archived or rebuilt.

## Arguments
- Judgement: observed behaviour complements the user tests that are still to be run.

## Risks / what would change our mind
- **Conflicts with D019.** The cookie banner promises audience measurement "with your consent", but the tag loads before the visitor chooses. Before we show the site to people outside the team, load the tag only after "Accepter", or reword the banner.
- The tag also fires on local runs (`localhost:4173`), so team testing pollutes the data. Restrict it to the Vercel domain if that matters.
- Only `site/index.html` carries it today. `identity.html` and `propositions.html` do not.

## Where it shows
`site/index.html`, `<head>`. Nothing visible in the interface.
