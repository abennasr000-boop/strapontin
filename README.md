# Strapontin

Discovery and booking for the independent cinemas and pocket theatres of Paris. UX course project (EMLV). Private repository, shared with the project team only.

| What | Where |
|---|---|
| Clickable prototype (current, v3) | `site/index.html` · published: https://claude.ai/artifact/PonDzd9ciVRLD6E3mTyGti |
| Brand identity guide (current, v3) | `site/identity.html` · published: https://claude.ai/artifact/P9mTAtbzP8mSTFsCnnUL5U |
| Earlier versions | `site/archive/` |
| Original Lovable prototype (v0) | https://pocket-stage-passport.lovable.app/ |
| Why things are the way they are | `docs/` (start with `docs/README.md`) |

The published pages are private; the owner shares them from each page's Share menu.

## Run locally

```bash
python3 -m http.server 4173 --directory site
```

Then open http://localhost:4173. Both pages are single self-contained HTML files (fonts load from Google Fonts).

## Status (14 November 2026)

- v3: the home page is a filterable poster gallery with a list view (D021); identity follows the grid-sheet reference (D022).
- The mockup shows real film posters looked up on Wikipedia when you run it locally. They are for internal review only, are not stored here, and their rights are not cleared (D023). The published page shows typographic tiles instead.
- Venues, showtimes and prices are fictional. Payment is simulated. Nothing has been tested with users yet.
