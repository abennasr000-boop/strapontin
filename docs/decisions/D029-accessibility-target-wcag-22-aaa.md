# D029 · Accessibility target: WCAG 2.2 AAA where it can be met, with named exceptions

**Status:** Accepted
**Date:** 24 Nov 2026
**Raises:** D019 (which stays as the baseline: skip link, reduced motion, wheelchair filter, equal cookie buttons)

## Context
D019 set an AA-level baseline (4.5:1 contrast, visible focus). F007 rated the prototype AA and asked for AAA. AAA is not normally required of a whole site: W3C itself says some AAA criteria cannot be met for all content. So we need a rule saying what we hold ourselves to and where we stop.

## Decision
- **Rule:** every new or changed screen meets WCAG 2.2 A and AA, plus these AAA criteria:
  - 1.4.6 contrast 7:1;
  - 2.4.9 link purpose from the link text alone;
  - 2.4.13 focus appearance;
  - 2.5.5 targets of 44px.
- **Exceptions:** anything that falls short is listed below, with the reason. An exception is a decision, not an oversight.
- **Proof:** before a push that touches the interface, axe-core runs with the WCAG A/AA/AAA and best-practice rules on every page and on the open states (cookie notice, search suggestions, My list, opened poster, every booking step), in French and English, on desktop and phone widths. Method and first results are in K08.

## Current exceptions
| Where | Criterion | Why | What would lift it |
|---|---|---|---|
| Seat map in booking (26px seats) | 2.5.5 | Ten 44px seats plus aisles do not fit a 375px phone. Zooming the map would hide the screen's position, which is what people use to choose. | A seat list ("Row D, seats 4–5") as an equivalent control next to the map. |
| "Un film au hasard" in the dock, under 360px wide | 2.5.5 | Hidden there to make room. The same action stays at the end of the gallery (equivalent-control exception). | — |
| Text over poster photographs | 1.4.6 | Posters vary. We use a dark gradient, which cannot be measured automatically. | A solid band behind tile text if testing shows problems. |
| 3.1.5 reading level, 1.2.6 sign language | AAA | No video. Interface text is short. | Revisit if editorial content or trailers arrive. |

## Arguments
- F007: team instruction.
- K08: the criteria are concrete and testable on our components, and the colour changes they needed were small (D030).
- K02, K03 (judgement on our segments): a ticketing site for older regulars, students on phones and visitors reading a second language. Larger targets, stronger contrast and plain labels help all three, not only people with a disability.
- Judgement: a stated exception list keeps "AAA" honest; claiming full AAA would be false.

## Risks / what would change our mind
- Automated checks are not an audit. A test with screen-reader users (VoiceOver on iPhone first, given K02) is the real proof; until then the claim is "no automated violations at AAA".
- 7:1 contrast darkens the identity (D022, D030). If the client finds it too heavy, the fallback is AA contrast (4.5:1) with everything else kept.
- 44px targets make the header taller on phones (D033).

## Where it shows
Throughout `site/index.html`. Checks: K08.
