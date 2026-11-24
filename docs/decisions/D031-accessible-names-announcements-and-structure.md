# D031 · Accessible names, link context, status announcements and heading structure

**Status:** Accepted
**Date:** 24 Nov 2026

## Context
F007: header controls had names too short to understand ("FR", "EN", "0"). The audit for D029 found more:
- repeated buttons with identical names (every bookmark was "Ajouter à ma liste");
- links that make sense only visually ("Séances →", "+3 →");
- result counts placed in live regions that were re-created on every change, which screen readers often miss;
- headings that skipped levels;
- headings placed inside the search suggestion list box.

## Decision
- **Names include the visible text, then add context (2.5.3):**
  - Language buttons are read "FR – français" and "EN – English", and keep `aria-pressed`.
  - The list button is read "Ma liste, 3 élément(s) enregistré(s)". On phones the words "Ma liste" are visually hidden, not removed.
- **Buttons name their object:**
  - Bookmark: "Garder *Perfect Days* dans ma liste", with the on/off state given by `aria-pressed`.
  - In My list: "Retirer *Perfect Days* de ma liste" and "Ne plus suivre *L'Éden Ménilmontant*".
- **Links carry their context as visually hidden text:**
  - "Séances · *Regards d'Asie* →"
  - "+3 autres séances pour *Parasite* →"
- **One permanent status region** (`#status`, `role="status"`, polite) announces:
  - filter results ("À l'affiche ce soir. 6 titres · 8 séances · 4 salles"), on the home page and on film pages;
  - the number of search suggestions, 600ms after typing stops;
  - list and booking confirmations.
  The visual toast stays, hidden from screen readers so nothing is read twice.
- **Headings never skip a level:**
  - Venue cards and venue info blocks are `h2`.
  - The season page and the booking summary each gain an `h2` before their `h3`s.
- **Search suggestions** are options in labelled groups ("Films", "Salles"), with no headings inside the list box.
- **Hidden text is anchored to its control** (the control is `position:relative`). Inside a scrolling row it otherwise widened the page; that happened once.

## Arguments
- F007 gap 1.
- K08: 2.4.9, 2.5.3, 4.1.3; the axe results (heading order, list box roles).
- Judgement: one permanent region is the most reliable way to announce changes across screen readers. Regions created on the fly often stay silent.

## Risks / what would change our mind
- Wording of hidden text is our judgement; only a screen-reader test can say if it is too long or repetitive.
- Search suggestion counts could be chatty; the 600ms delay is a guess.

## Where it shows
`renderChrome()`, `bm()`, `layer()`, `say()`, `announceHome()`, `ac()`, `salles()`, `venue()`, `cycle()`, `booking()` in `site/index.html`.
