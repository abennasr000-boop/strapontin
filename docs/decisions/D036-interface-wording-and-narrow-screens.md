# D036 · Interface wording: one name per place, whole words, each language's own typography; header on narrow phones

**Status:** Accepted
**Date:** 24 Nov 2026

## Context
The F006 audit found:
- **The agenda page had three names:** "Rendez-vous"/"Events" in the desktop menu, "Agenda" on phones, and "Les rendez-vous"/"What's on" as its title.
- **Lines broke in illogical places:** "ALL-/IN PRICES" in the line under the home title; "+17 showtimes · 2 / venues" on tiles.
- **Wrong typography and translation:** French quotation marks « » in the English text, and an untranslated cookie-banner label.
- **The header was too wide:** it needed 371px, so on 320px phones the whole site rendered zoomed out.

## Decision
- **One name per place, the same in the menu, on phones, in the page title and in the breadcrumb:** "Agenda" in French, "What's on" in English. The other pages were already consistent.
- **Statistic and showtime lines break only between items:** each item ("15 titres", "152 séances", "4 salles") stays together. A district stays with its venue, and a price stays whole.
- **Each language uses its own typography:** « » with spaces in French, “ ” in English. Every label is translated, including the ones only screen readers hear.
- **Narrow phones (under 420px):** the language control shows only the language you can switch to ("EN" while reading French). The navigation spacing tightens below 420px and again below 350px. The page fits 320px with no horizontal scroll.

## Arguments
- F006.
- K04 (as in D019): consistent naming lowers uncertainty (K03).
- Judgement: a page known by three names looks like three pages.

## Risks / what would change our mind
- Showing only the other language hides which language is active. The active one is still announced to screen readers (D031), and the page text makes it obvious. Revert if testers look for "FR".
- "Agenda" replaces "Rendez-vous", which the client may prefer as the more distinctive word.

## Where it shows
`renderChrome()`, `agenda()`, `cycle()`, the `.stats` and `.nw` rules, and the narrow-screen media queries in `site/index.html`.
