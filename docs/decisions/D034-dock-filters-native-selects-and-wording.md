# D034 · Dock filters: native selects under a visible label, and how they are worded

**Status:** Accepted
**Date:** 24 Nov 2026
**Refines:** D025 (the floating dock)

## Context
- **F006 (first phone test):**
  - iOS zoomed the page whenever a dock filter was tapped, because its text was under 16px;
  - the filter labels were abbreviations ("Tmrw", "Auj.") or jargon for English readers ("VO+VF");
  - "7 jours" in the filter did not match "cette semaine" in the title.
- **F007 (accessibility review):** custom-styled filters may be hard to use with a keyboard.

## Decision
- **Structure:** each filter is a `<label>` showing a short text, with the native `<select>` stretched over it, transparent, at 16px.
  - The tap or click lands on the real select, so the platform's own picker, keyboard handling and screen-reader behaviour are used.
  - Because the select is 16px, iOS does not zoom.
  - The visible text can be smaller without affecting any of that.
- **Wording rules:**
  1. **Whole words only.** No "Tmrw", "Auj.", "VO+VF".
  2. **At rest, a filter shows its category:** "Paris", "Version". When set, it shows its value and turns ink ("Demain", "20e", "English").
  3. **Full wording in the picker:** the visible label may be short, but the options are always fully worded ("VO sous-titrée français", "20e · Ménilmontant", "English-friendly (in English or with English subtitles)").
  4. **Same words in the title:** the filter and the page title use the same words ("7 jours" and "sur 7 jours"; "This weekend").
  5. **English readers see no French jargon:** "VO" and "VF" become "Original" and "French" in English.
- **Phone layout:** the dock spans the screen width. It holds the search icon, three filters, then "Un film au hasard" (hidden under 360px; see D033). Neutral words were chosen so all three filters fit without being cut at 320px.
- **Day names:** day labels everywhere (tiles, day picker, My list) are whole and capitalised: "Aujourd'hui", "Demain", "Mer.", "Today", "Tomorrow".

## Arguments
- F006, F007 gap 2.
- K08: 2.5.3 (the select's name is its category, e.g. "Quand", and its value is announced), 3.2.2.
- K02: many visitors read the site in their second language, and abbreviations are the first thing lost.
- Judgement: a native select beats a custom list box for reliability across phones and assistive technology, at the cost of less control over how the picker looks.

## Risks / what would change our mind
- "English" on a phone is shorter than "English-friendly" and could be read as "English-language films only"; the picker explains it. Watch in tests.
- The native picker looks different on each platform (already noted in D025).

## Where it shows
`dockOpts()`, `dockSel()`, `syncDock()`, `renderDock()` and the `.dsel` styles in `site/index.html`.
