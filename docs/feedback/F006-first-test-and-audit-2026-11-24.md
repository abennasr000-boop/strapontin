# F006 · First test on phone, and full audit (24 Nov 2026)

## What the tester reported
- The search bar lagged: typing was sometimes impossible, and scrolling or filtering glitched.
- The line under "À l'affiche / Now showing" wrapped onto two lines in an illogical place ("ALL-/IN PRICES").
- Some filter labels were not proper words ("Tmrw", "Auj.").

## What the audit found (causes, not symptoms)
1. **Search wiped itself.** Any click outside an element called `.search` cleared the query; the dock has no such element, so tapping inside the search field cleared what had been typed.
2. **Resize rebuilt the page.** Phones fire `resize` when the address bar hides on scroll and when the keyboard opens. Each one rebuilt the whole dock (destroying the field being typed in and closing the keyboard) and redrew the whole gallery mid-scroll.
3. **iOS zoomed on the filters.** Native selects below 16px make iOS Safari zoom the page on tap, which then fights the fixed dock.
4. **Page wider than small phones.** The header row needed 371px, so on 320px phones the whole site rendered zoomed out.
5. Smaller issues: hover lifts sticking on touch screens; a backdrop blur over scrolling posters (costly on phones); full-size poster originals (several MB each) fetched one by one; mosaic offsets that read as misalignment on two columns; showtime lines in tiles breaking between a venue and its district or price; "7 days" in the filter but "this week" in the title; French « » quotes in the English text; untranslated cookie-banner label; "Rendez-vous"/"Events" on desktop but "Agenda" on phones for the same page.

## What it changed
- Dock filters are a visible label with the native select laid over it at 16px. The resting state names the category ("Paris", "Version"), the active state names the value and turns ink, and the picker keeps the full wording. (D025 update)
- Resize only re-lays out on a real width change; the keyboard offsets the dock on iOS via `visualViewport`; Android resizes content (`interactive-widget`).
- Statistic lines and showtime lines only break between items. Day labels are whole words ("Demain", "Tomorrow"), capitalised.
- On phones narrower than 420px the language control shows only the other language.
- Agenda page: one name everywhere, "Agenda" in French and "What's on" in English.
- Posters: 640px thumbnails fetched in parallel.

## Not tested yet
Real iOS and Android devices. Everything above was checked in Chromium with phone emulation at 320, 360, 375, 390 and 414px and on desktop.
