# Strapontin

Discovery and booking for the independent cinemas and pocket theatres of Paris. UX course project (EMLV). Private repository, shared with the project team only.

| What | Where |
|---|---|
| Clickable prototype (current, v2) | `site/index.html` · published: https://claude.ai/artifact/PonDzd9ciVRLD6E3mTyGti |
| Brand identity guide (current, v2) | `site/identity.html` · published: https://claude.ai/artifact/P9mTAtbzP8mSTFsCnnUL5U |
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

- Functional fixes from the NCPI audit: done in the prototype (see `docs/knowledge/K04-ncpi-audit.md`).
- Identity: v2 direction applied after the client review of v1. Two decisions are open: palette mood (D017) and the gallery-first homepage (D016).
- Programme, venues and prices are fictional. Payment is simulated. Nothing has been tested with users yet.
