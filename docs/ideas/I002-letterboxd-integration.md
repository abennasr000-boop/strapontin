# I002 · Letterboxd integration: watched, watchlist, friends

**Raised by:** client, F004 (14 Nov 2026) · **Status:** logged, not built, feasibility not checked

## Idea
A user links their Letterboxd account. On each poster in the gallery and on the film page, the site shows whether they have already watched the film, whether it is on their watchlist, and whether friends they follow have seen it. Filters could follow: "ma watchlist à l'affiche cette semaine", "pas encore vus".

## Why it could matter
- **Segment fit (K02):** art-house regulars and students are the kind of audience that keeps a film diary; the site would meet a habit they already have instead of asking them to rebuild a list here.
- **Internal motivation (F004):** "my watchlist is playing near me tonight" is the strongest possible prompt, and it comes from the viewer, not from us.
- **Engagement rate (K02):** a reason to open the site weekly; it also feeds alerts (D011).
- **Local discovery (K06):** connects a global wish list to a local screening, which is exactly the gap the project targets.

## Tension to resolve first
- **K03 / D010:** the brief asks to replace crowd signals with personal curation. "Friends have seen it" is a social signal. It is a signal from people the user chose, not an anonymous crowd, and should be shown quietly (names or initials, no counts, no "trending"). This needs an explicit decision before design.

## What it needs
- **Feasibility is unverified.** We have not checked what Letterboxd's API allows, who can get access, or its terms for showing watched, watchlist and friends' activity on a third-party site. Check this before any design work.
- Reliable matching between our catalogue and theirs (titles differ between French and original release).
- Explicit consent and a clear disconnect option; friends' activity is other people's data.
- A fallback for everyone without an account: the feature must add to the page, never be required.

## Risks
- Dependence on one outside company's access rules.
- Clutter: three more markers on every poster would hurt the lightness asked for in F003. Limit to one small mark per poster.
- Our own "Ma liste" (D011) overlaps with the Letterboxd watchlist; decide which is the source of truth for a linked user.
