# D030 · Colour values revised for 7:1 text contrast

**Status:** Accepted
**Date:** 24 Nov 2026
**Changes:** colour values of D022 (identity v3); the identity's direction is unchanged

## Context
Under D029, text must reach 7:1 (1.4.6). Measured in K08, three identity colours used for small text did not: the secondary grey (5.87:1 on paper), the orangeade used as text (4.78:1) and the award green (5.99:1). Cream text on orangeade buttons was 6.39:1, and the button hover 5.03:1.

## Decision
| Token | Before | After | Used for |
|---|---|---|---|
| `--ink-2` | #574B49 | **#403736** | Secondary text, labels, metadata |
| `--accent` | #A82F0C | **#9C2B0B** | Booking buttons, active bookmark, selected seat (surfaces, with cream text) |
| `--accent-2` (hover) | #C23A12 (lighter) | **#7E2309** (darker) | Button hover. Hover now darkens instead of lightening. |
| `--accent-t` (new) | — | **#6B1E07** | Orangeade used as *text*: "Réserver" on tickets, list counter, search match highlight |
| `--green` | #5E4A05 | **#473803** | Award line |

- **Accent split in two:** the orangeade keeps its role in D022 ("orangeade only for booking"). It now has two values: one for surfaces, and a darker one when it is text on paper.
- **Past showtimes:** no longer faded to 45% opacity. They keep full-contrast grey text with a dashed border, struck-through time and "Séance passée".
- **Placeholder posters:** when a real poster cannot load, the title takes ink or white, whichever contrasts more. If neither reaches 7:1 (mid-tones such as the orangeade poster colour), the placeholder colour is darkened until white text does.

## Arguments
- K08: every new value reaches at least 7:1 on all three paper tones (lowest 7.09:1, award green on paper-3).
- D022: hues are kept; only lightness moves, so the palette still reads as sage paper, wine ink and orangeade.
- Judgement: a separate text token avoids darkening the large orange surfaces more than needed.

## Risks / what would change our mind
- The page is a little darker and heavier; the orangeade "Réserver" text reads brown-red. Client to confirm.
- Hover now darkens, which is the opposite of before; check it still reads as a response.

## Where it shows
`:root` tokens at the top of the `<style>` in `site/index.html`. `.tk.past`; `phCol()` for placeholder posters.
