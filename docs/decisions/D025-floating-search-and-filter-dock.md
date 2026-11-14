# D025 · Search and filters live in a floating dock at the bottom centre

**Status:** Accepted (client direction); untested with users
**Date:** 14 Nov 2026

## Context
F004: with filters in a line under the header and search in the header, the client did not reach for them. The stated principle is visual navigation first, deliberate filtering second, with a control that is obvious when wanted.

## Decision
A dark, pill-shaped dock floats at the bottom centre of the screen on every page except booking. It holds search (with suggestions opening upward), then on the home page: when, area, version, a gallery/list switch and "un film au hasard". Active filters are highlighted inside the dock. On phones the dock spans the width, search collapses to an icon that expands over the filters, labels are shortened, and the gallery/list switch moves to the title line. The header keeps only the logo, three navigation links, language and "Ma liste"; the phone bottom tab bar is removed. The page title line states the current filters in words ("À l'affiche aujourd'hui · 5e").

## Arguments
- F004 points 1 and 2 (client).
- K02, phones first: the bottom centre is the thumb zone; the top of the screen is the hardest place to reach on a large phone. (General ergonomics claim, not sourced in our knowledge base.)
- K02 segments, client's framing: film lovers looking for something local arrive with their own motivation; the gallery feeds discovery, the dock serves the moment they know what they want (a date, a neighbourhood, a title).
- K06 (CNC, as cited): proximity matters to 75% → area sits in the dock, one tap away, and is echoed in the title.
- K03: the title line restating active filters keeps the state of the page unambiguous.
- Judgement: one dark object on a light page is found without being read; it replaces three separate places (header search, filter line, tab bar).

## Risks / what would change our mind
- The dock covers the bottom 70 px of content while scrolling.
- Native select menus inside the dock look different on each platform.
- The type filter (cinema / theatre) is gone for now (see D026).
- Cookie notice moved to a card under the header to free the bottom edge; "Refuser" and "Accepter" remain equal.
- Test: do first-time users find area and date filters without prompting? Compare with the top filter line (kept in git history).

## Where it shows
`renderDock()` and the `.dock` styles in `site/index.html`.
