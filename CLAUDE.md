# Strapontin: notes for Claude

- Read `docs/README.md` first; decisions live in `docs/decisions/`.
- **Keep the Microsoft Clarity tag (D027) in every version of the prototype.** It is the `<script>` block with project ID `zeku8v4fl1` in the `<head>` of `site/index.html`, right after `<title>`. When you rebuild, replace or add a prototype page, carry it over; do not remove it unless the user says so.
- Run locally with `python3 -m http.server 4173 --directory site`.
