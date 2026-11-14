# D016 · Homepage opens on the photo gallery, finder second

**Status:** Superseded by D021 (client review F002); its test plan still applies
**Date:** 14 Nov 2026

## Context
The client chose a gallery-first opening, inspired by the mood-board videos, and asked that it be confronted with the design goals rather than kept for its looks. K04 criticised v0 precisely for reading "like a magazine rather than a booking tool".

## Decision
The homepage opens with a value statement, a wall of small instant photos and a reveal panel: hovering, focusing or tapping a photo "develops" it and shows the film, the number of venues, the next showtime with venue and price as a bookable ticket. A "Voir les séances" button and the first navigation item lead to the finder directly below.

## Arguments
- **Goal: engagement rate (K02).** Hypothesis: browsing images invites more interactions per visit (reveals, saves) than a list of times, and gives a reason to return when the wall changes.
- **Segment: art-house regulars and visitors (K02).** Hypothesis: they come to find something they did not know they wanted; the wall serves discovery, the brand keyword in F001.
- **Segment: students deciding tonight (K02).** The gallery works against them. Mitigations built in: each reveal already contains a bookable ticket with price; the finder is one click or one scroll away; "Séances" is the first, highlighted navigation item and the header is sticky.
- K07 (Baymard, as cited): no carousel, everything is visible at rest.
- Honest counter-argument: K04’s first two priorities were about answering "what, where, how much, tonight" immediately. This layout answers it one step later.

## Risks / what would change our mind
- **Test before confirming.** (1) First-click test, task "find something to see tonight near the 5e": where do people click, and how long to the first showtime? Compare gallery-first vs finder-first. (2) Five-second test: do people understand this is a booking service? (3) After launch: reveal interactions, saves and bookings per visit, by entry page.
- Revert to finder-first, with the gallery below, if time-to-first-showtime is clearly worse or if people do not understand they can book.
- On touch devices there is no hover; the wall becomes a scrolling strip and needs its own check.

## Where it shows
Homepage top section.
