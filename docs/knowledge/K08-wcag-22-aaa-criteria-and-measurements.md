# K08 · WCAG 2.2 AAA: the criteria we apply, and what we measured

**Source:** W3C, Web Content Accessibility Guidelines 2.2 (our reading of the success criteria named below), plus measurements we made ourselves on the prototype on 24 Nov 2026. The contrast ratios are computed with the WCAG relative-luminance formula from our own hex values. The automated results come from axe-core 4.10.2 running in Chromium through Playwright.

**Reliability:** the criteria are a published standard. The measurements are reproducible, but automated tools find only part of the problems. axe cannot judge whether a label makes sense, whether focus order is logical, or how a real screen reader speaks the page. Nothing here comes from a person with a disability using the site.

## Criteria we use beyond AA, and what each means for us
| Criterion | Level | What it requires | How it applies here |
|---|---|---|---|
| 1.4.6 Contrast (enhanced) | AAA | Text at least 7:1 against its background (4.5:1 for large text, 24px or 18.66px bold) | Almost all our text is small (labels 11.5px, tickets 12.5–13.5px), so 7:1 applies nearly everywhere |
| 1.4.11 Non-text contrast | AA | Controls and focus indicators at least 3:1 | Ticket borders, dock, focus ring |
| 2.4.9 Link purpose (link only) | AAA | A link's text alone says where it goes | "Séances →", "+3 →" needed hidden context |
| 2.4.13 Focus appearance | AAA | Focus indicator at least 2px thick around the control, 3:1 between focused and unfocused states | Our old 2px accent ring had too little contrast on dark posters |
| 2.5.3 Label in name | A | The accessible name contains the visible text | Why "FR" is read "FR – français" rather than only "Français" |
| 2.5.5 Target size (enhanced) | AAA | Targets at least 44 × 44 CSS px, unless an equivalent control meets it, the target is inline in text, or the size is essential | Header, dock, chips, steppers, close and bookmark buttons |
| 3.2.2 On input | A | Changing a setting does not change context unexpectedly | Re-filtering the gallery when a filter changes is a content update, not a change of context |
| 4.1.3 Status messages | AA | Results and confirmations are announced without moving focus | Why we use one permanent `role="status"` region |
| 3.1.5 Reading level, 1.2.6 Sign language | AAA | Plain-language alternative; sign-language video | Not applicable to the prototype today (no video; short UI text) |

## Contrast measured on our colours
Backgrounds: paper #D8D9CC, paper-2 #E5E6DB (tickets, panels), paper-3 #CBCDBE (hover rows).

| Role | Before | Ratio on paper / paper-2 / paper-3 | After | Ratio on paper / paper-2 / paper-3 |
|---|---|---|---|---|
| Secondary text (`--ink-2`) | #574B49 | 5.87 / 6.65 / 5.19 | #403736 | 8.10 / 9.17 / 7.16 |
| Accent used as text ("Réserver", list count, search highlight) | #A82F0C | 4.78 / 5.42 / 4.23 | #6B1E07 (`--accent-t`) | 8.11 / 9.19 / 7.18 |
| Award line (`--green`) | #5E4A05 | 5.99 / 6.78 / 5.30 | #473803 | 8.02 / 9.09 / 7.09 |
| Cream text on accent buttons | on #A82F0C: 6.39 | | on #9C2B0B: 7.11 | |
| Cream text on button hover | on #C23A12: 5.03 | | on #7E2309: 9.23 | |
| Main ink #231417 | 12.43 on paper | | unchanged | |

Other measurements:
- **Focus ring:** ink against paper is 12.43. The light halo #F6F6EF against the darkest posters is 16.34.
- **Accent as a non-text colour:** #9C2B0B against paper is 5.32 (3:1 needed).
- **Past showtimes:** these used to be faded to 45% opacity, which fell below 4.5:1 (axe failure).

## Automated results (24 Nov 2026)
- **Before the changes:** axe with the WCAG A, AA, AAA and best-practice rules reported these violations:
  - colour contrast on past showtimes;
  - enhanced contrast on placeholder posters;
  - heading levels skipped on the Venues, venue, season and booking pages;
  - an `aside` carrying `role="dialog"`.
- **After:** no violations on the home, agenda, venues, film, venue and season pages; nor with the cookie notice, the search suggestions, the open My list panel or an opened poster; nor on any booking step. That holds in French and English, at 1280px and in iPhone 13 mini emulation.
- **Keyboard script:**
  - the filters can be reached with Tab and changed with the arrow keys, and focus stays on them;
  - the new result is announced;
  - in the My list panel, Tab stays inside, Escape closes it, and focus returns to the "Ma liste" button.

## Limits
- No test with VoiceOver, TalkBack or NVDA, and no test on real devices.
- The seat map (26px seats) does not meet 2.5.5; see D033.
- Contrast of text over poster photographs cannot be measured automatically. The dark gradient behind tile text is our judgement, not a measurement.

## Used by
D029, D030, D031, D032, D033.
