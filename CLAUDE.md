# Strapontin: notes for Claude

- Read `docs/README.md` first; decisions live in `docs/decisions/`.
- **Keep the Microsoft Clarity tag (D027) in every version of the prototype.** It is the `<script>` block with project ID `zeku8v4fl1` in the `<head>` of `site/index.html`, right after `<title>`, wrapped in `loadClarity()`, which is called only after the visitor accepts cookies (D019). Never make it load unconditionally. When you rebuild, replace or add a prototype page, carry it over; do not remove it unless the user says so.
- Run locally with `python3 -m http.server 4173 --directory site`.
- **Keep the Google Analytics 4 tag (D028) too.** It is `loadGA4()` / `revokeGA4()` in the same `<head>` script block as Clarity, with the measurement ID in `GA4_ID`. Same consent gating: never load it unconditionally.
- **Accessibility target is WCAG 2.2 AAA with named exceptions (D029).** Use the colour tokens from D030 (never the old #574B49 / #A82F0C for text), keep 44px targets (D033), the focus ring and dialog behaviour (D032), and names/announcements via `say()` (D031). Before pushing interface changes, run axe-core with the WCAG A/AA/AAA rules on every page and open state, as described in `docs/knowledge/K08-*`. Log changes in `docs/changelog.md`.
