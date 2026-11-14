# K04 · NCPI audit of the Lovable prototype (v0)

**Source:** heuristic audit provided 14 Nov 2026, structured as Navigation / Content / Presentation / Interaction.
**Reliability:** expert review, desktop only (~850 px), no mobile, no payment flow, no users. The external statistics it cites (Baymard, Stanford) are recorded in K07 and were not re-verified by us.

## Findings and what happened to each

| # | Finding | Fix in the prototype | Decision |
|---|---|---|---|
| N1 | No time or place entry point on the homepage | Finder: today / tonight / tomorrow / weekend, arrondissement, version | D006 |
| N2 | Search has no autocomplete; "varda" misses the retrospective | Accent-insensitive autocomplete over films, people, seasons, venues | D012 |
| N3 | Header not sticky | Sticky header (and a later bug fix) | D018 |
| N4 | City selector lists ten cities | "Paris" shown as a fixed label | D006 |
| C1 | Stale dates; past screenings bookable | Dates generated from today; started screenings disabled | D005 |
| C2 | Centralisation not shown | Venue count, next showtime, price on every card; special screenings from five venues | D008 |
| C3 | Reassurance buried in the footer | Strip under the header | D009 |
| P1 | 11 px grey uppercase labels | 12.5–13 px typewriter labels at ≥ 6:1 contrast | D015, D019 |
| P2 | Category badge shown twice | One badge per special screening | D007 |
| P3 | Two venues share a photo | One illustrated portrait per venue | D015 |
| P4 | Truncated credits; empty theatre column | Credits wrap; two-column theatre layout | D015 |
| I1 | Showtime boxes do not look clickable | Ticket component with price and "Réserver" | D007 |
| I2 | No engagement hooks on the homepage | Bookmark on every card, follow buttons, "Ma liste" | D011 |
| I3 | Carousel hides slide 2 | No carousel | D016 (hero) |
| I4 | No skip link | Added | D019 |

## Audit priority order
Dates first, then the time/place bar, then showtime and price on cards. All three are done.

## Tension to keep in view
The audit's main criticism was that the homepage "reads like a magazine rather than a booking tool". The v2 gallery-first hero moves back toward the magazine side. This is exactly why D016 is provisional.
