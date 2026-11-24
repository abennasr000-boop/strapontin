# Changelog

What changed in the prototype, newest first. Each line points to the records that explain why. Earlier history is in the decision records (D001–D028) and in git.

## 24 Nov 2026 · Accessibility towards WCAG 2.2 AAA (PR #2, second commit)
Trigger: external accessibility review rating the prototype AA (F007).
- **Target:** AAA where it can be met, with a named exception list, checked with axe-core on every page and state (D029, K08).
- **Contrast 7:1:** darker secondary grey, award green and orangeade buttons, plus a separate darker orangeade for text. Past showtimes are no longer faded, and placeholder posters adjust their colours (D030).
- **Names and announcements:**
  - "FR – français", "EN – English", "My list, N saved item(s)";
  - bookmark, remove and unfollow buttons name their film, venue or season;
  - short links carry hidden context;
  - one status region announces filter results, suggestions and confirmations;
  - heading levels no longer skip (D031).
- **Focus:** two-tone 3px ring visible on paper and posters. My list and the film sheet keep Tab inside, close with Escape, return focus and make the page behind inert (D032).
- **Targets:** 44px minimum, with the seat map as the stated exception (D033).

## 24 Nov 2026 · First phone test fixes (PR #2, first commit)
Trigger: first phone test, search lag, odd line breaks, "Tmrw" (F006).
- **Search:** keeps its text when tapped. The dock and gallery are no longer rebuilt on scroll or keyboard resizes (D035).
- **Filters:** native 16px selects under a visible label, so iOS no longer zooms. Labels are whole words: the category at rest, the value when set, full wording in the picker (D034).
- **Keyboard:** the dock moves above it on iOS; on Android the page resizes for it (D035).
- **Lighter on phones:** no backdrop blur and no sticky hover on touch screens; posters load as 640px thumbnails in parallel (D035).
- **Layout and wording:**
  - the header fits 320px phones;
  - statistic and showtime lines break only between items;
  - one name for the agenda page ("Agenda" / "What's on");
  - English quotation marks;
  - translated cookie label (D036).

## 16–23 Nov 2026
- Microsoft Clarity (D027) and Google Analytics 4 (D028), both loaded only after cookie consent (D019).
