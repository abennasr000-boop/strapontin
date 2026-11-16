# Project documentation

This folder is the project's memory. It answers two questions for anyone on the team:

1. **What do we know, and where does it come from?** → `knowledge/`
2. **What did we decide, on what grounds, and is it still valid?** → `decisions/`

Client and team reviews are logged in `feedback/`. Ideas raised but not built live in `ideas/`. The `contribution-matrix.md` file links the two: for each piece of knowledge, the concrete things it changed in the product.

## How the system works

**Knowledge notes (`knowledge/Kxx-*.md`)** hold one source or body of evidence each: what it says, how reliable it is, its limits, and which decisions rely on it. A claim we could not verify ourselves is marked as such.

**Decision records (`decisions/Dxxx-*.md`)** hold one decision each, always with the same fields:

- **Status**: Accepted · Provisional (accepted but must be tested) · Open · Superseded
- **Context**: the problem
- **Decision**: what we do
- **Arguments**: why, each tied to a knowledge note (`K..`), a feedback entry (`F..`) or stated as our own judgement
- **Risks / what would change our mind**
- **Where it shows** in the prototype

**Rules**

- Never edit a decision to change its meaning. Write a new one and mark the old one `Superseded by Dxxx`.
- Every design choice that costs more than an hour to reverse gets a record.
- An argument without a source is allowed, but must be labelled "judgement".
- When new evidence arrives (a user test, a client review), add it to `knowledge/` or `feedback/` first, then update the decisions it touches.

## Index of decisions

| ID | Decision | Status |
|---|---|---|
| D001 | Build a standalone prototype instead of editing the Lovable project | Accepted |
| D002 | Cover the full journey: home, film, venue, booking | Accepted |
| D003 | French by default, English toggle, "English-friendly" filter | Accepted |
| D004 | Keep the name Strapontin | Accepted |
| D005 | Programme dates generated from today; started screenings not bookable | Accepted |
| D006 | A when / where / version finder on the homepage | Accepted |
| D007 | Every showtime is a ticket showing price and "Réserver" | Accepted |
| D008 | Film cards show venue count, next showtime, lowest price | Accepted |
| D009 | All-in pricing and reassurance strip under the header | Accepted |
| D010 | No urgency or crowd signals; legitimacy through critics and programmers | Accepted |
| D011 | Engagement hooks: bookmark, follow, list without account, carnet | Accepted |
| D012 | Search with autocomplete across films, people, seasons, venues | Accepted |
| D013 | Card payment delegated to Stripe's hosted form | Accepted |
| D014 | Identity v1: bold Didone, geometric posters, circled word, seat mark | Superseded by D015 |
| D015 | Identity v2: film grain, hazy stills, light serif + typewriter, lines only on actions | Superseded by D022 |
| D016 | Homepage opens on the photo gallery, finder second | Superseded by D021 |
| D017 | Palette mood: Faded print or Dusk | Closed by D022 |
| D018 | Sticky header | Accepted |
| D019 | Accessibility and consent baseline | Accepted |
| D020 | This documentation system | Accepted |
| D021 | Home page is a filterable poster gallery, with a list view | Accepted as goal; **untested** |
| D022 | Identity v3: the grid sheet | Accepted (direction) |
| D023 | Real film posters in the internal mockup | Internal review only; **rights not cleared** |
| D024 | Home gallery layout: mosaic, drift or accordion | Decided: Mosaïque, built |
| D025 | Search and filters in a floating dock at the bottom centre | Accepted; **untested** |
| D026 | Test catalogue is films only, every title with a poster | Accepted for the test; theatre to return |
| D027 | Microsoft Clarity tracking tag kept on the prototype | Accepted for the test; **consent handling open** |
