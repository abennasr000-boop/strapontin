# D019 · Accessibility and consent baseline

**Status:** Accepted
**Date:** 14 Nov 2026

## Context
K04 P1, I4 and the French legal context.

## Decision
Skip link, visible focus, text contrast ≥ 4.5:1, labels ≥ 12.5 px, keyboard-operable search and filters, reduced-motion support, wheelchair filter, cookie banner with equal "Refuser" and "Accepter".

## Arguments
- K04 P1, I4.
- K07: WCAG, CNIL.
- K03: consent clarity fits high uncertainty avoidance.

## Risks / what would change our mind
- Not audited with assistive technology. The seat map and the hover gallery need a screen-reader pass.

## Where it shows
Throughout.

## Update (24 Nov 2026): towards WCAG 2.2 AAA
An external accessibility review rated the prototype AA and named two gaps: header controls with very short names ("FR", "EN", "0") and custom-styled filters whose keyboard focus was unclear. Changes:
- **Names:** language buttons read "FR – français" / "EN – English"; the list button reads "My list, N saved item(s)" also on phones, where the words are hidden visually. Bookmark and remove buttons name the film, venue or season they act on. "Showtimes →" and "+N →" links say what they lead to.
- **Filters:** native selects under the visible label, so keyboard and screen-reader behaviour is the browser's own. Changing a filter announces the new title and counts through one permanent status region (also used for list confirmations, search suggestion counts and film page filters).
- **Focus:** a two-tone ring (3px ink outside, light halo inside) visible on light paper and on dark posters (2.4.13). Panels keep Tab inside, close with Escape, return focus to the control that opened them, and make the page behind inert.
- **Contrast 7:1 (1.4.6):** secondary text #403736, text in accent #6B1E07, award green #473803, buttons on #9C2B0B. Past showtimes are no longer faded; they are dashed, struck through and labelled. Placeholder posters pick or darken their colour until the title reaches 7:1.
- **Target size 44px (2.5.5):** navigation, language, list, dock buttons and filters, chips, day picker, steppers, close and bookmark buttons. On phones narrower than 360px the dock hides "Un film au hasard", which stays available at the end of the gallery (equivalent control exception).
- **Structure:** heading levels no longer skip (venues, venue page, season page, booking summary); search suggestions are grouped options, not headings inside a list box; panels are dialogs on a neutral element.

**Checked:** axe-core 4.10 with the WCAG A, AA, AAA and best-practice rules reports no violations on home, agenda, venues, a film, a venue, a season, the cookie notice, search suggestions, My list, an opened poster and every booking step, in French and English, on desktop and phone emulation. Keyboard: the filters change with arrow keys and keep focus.

**Not done / not checkable automatically:** the seat map buttons stay 26px (a 10-seat row does not fit 44px seats on a phone); reading level (3.1.5) and sign language (1.2.6) do not apply to the prototype as is; real screen readers (VoiceOver, TalkBack, NVDA) have not been tried.
