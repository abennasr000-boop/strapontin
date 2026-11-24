# F007 · External accessibility review (24 Nov 2026)

Shared by the team after the F006 fixes. It was a review of the published prototype, not a test with users of assistive technology.

## What it said
**Rating: AA (standard accessibility).** Well structured and following most practice for screen readers, but short of AAA.

Strengths noted:
- Every poster image has a text alternative ("Affiche : Cléo de 5 à 7").
- Heading levels follow each other on the home page, so screen-reader users can jump between sections.
- Action links say what they do ("Vue liste", "Voir toutes les séances en liste →").

Gaps noted:
1. **Very short labels** in the header: "FR", "EN" and the list counter "0". Without hidden context ("Language: French", "Bookmarks: 0") a screen-reader user may not understand them.
2. **Custom-styled filters** in the dock ("Aujourd'hui", "Paris", "VO + VF"). If they do not show a standard keyboard focus, people who cannot use a mouse may struggle to choose an option.

## Team instruction
Implement both, and move towards AAA.

## What it changed
- D029: AAA becomes the target, with named exceptions.
- D030: colour values revised for 7:1 text contrast.
- D031: accessible names, link context, status announcements, heading structure.
- D032: focus ring and dialog behaviour.
- D033: 44px targets.
- D034: the dock filters, already rebuilt as native selects for F006, keep that structure for keyboard reasons.
