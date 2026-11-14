# D021 · The home page is a filterable poster gallery, with a list view

**Status:** Accepted as the product goal; untested with users
**Date:** 14 Nov 2026

## Context
F002: the v2 home had an opening statement, a photo wall, a reveal panel and then the finder, which read as cluttered. The client restated the main goal as playful discovery of films across venues, mostly on phones, with clear information and quick filters.

## Decision
The home page opens directly on a grid of posters for everything showing under the current filters, in a random order per visit. Filters (when, area, version, type) sit in a bar that stays under the header while scrolling. Each cell shows title, director, and the next showtime with venue and price. Tapping a poster opens a detail sheet with award, synopsis and bookable tickets. A Gallery/List switch and a "Voir toutes les séances en liste" button lead to the classic list of showtimes. "Un film au hasard" opens a random film. Special screenings, seasons and venues moved to their own pages. On phones, navigation is a bottom bar.

## Arguments
- F002 points 1, 2, 6, 7, 9: the client’s explicit goal and layout.
- K02: students decide late on a phone → filters stay visible, default is "ce soir", price is on every cell.
- K03: time, venue and price on every poster keeps uncertainty low while browsing.
- K04: the audit wanted "what, where, how much, tonight" answered on the home page. Here the gallery itself answers it, which resolves the tension recorded in D016.
- K06 (CNC, as cited): area filter for proximity.
- Judgement: random order supports discovery and avoids implying a ranking (K03, no "trending").
- Judgement: a bottom tab bar on phones keeps the top of the screen for filters.

## Risks / what would change our mind
- Still no user evidence. The D016 test plan applies unchanged: first-click and time-to-first-showtime, gallery vs list as the default view.
- Random order makes the page different on each visit; returning users may not find a film where they left it. Search and "Ma liste" mitigate; watch for complaints.
- Sticky header plus filter bar plus bottom bar take about 200 px on a small phone.
- With many more films the grid needs paging or lazy loading.

## Where it shows
Home page; `homeBody()`, `sheetHTML()` in `site/index.html`.
