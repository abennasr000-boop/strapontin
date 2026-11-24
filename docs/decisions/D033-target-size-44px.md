# D033 · Touch and click targets of at least 44 × 44 px

**Status:** Accepted
**Date:** 24 Nov 2026

## Context
D029 adopts 2.5.5 (target size, enhanced). Before, the language buttons were about 20 × 30px, the bookmark circles 34px, close buttons 36px, dock buttons 38–40px, and filter chips about 37px high. The site is mostly used on phones (K02, D021).

## Decision
- These are at least 44px high, and at least 44px wide where they are not text-wide:
  - navigation links, language buttons, "Ma liste";
  - every dock button and filter;
  - version and time-of-day chips, the day picker, booking steps and quantity steppers;
  - the accessibility checkbox, payment options;
  - breadcrumb, footer and "+N" links.
- **Small circles keep their size:** the bookmark (34px) and close (40px) buttons keep their visual size but get an invisible hit area that reaches 44px.
- **Exceptions:** listed in D029. The seat map (26px) and "Un film au hasard" in the dock under 360px wide (equivalent at the end of the gallery). Links inside running text are exempt by the criterion itself.

## Arguments
- K08 (2.5.5); K02: phone-first, often one-handed and on the move.
- Judgement: invisible hit areas give the larger target without making the poster gallery heavier.

## Risks / what would change our mind
- The header and dock are a few pixels taller on phones (dock about 54px instead of 50px), and they cover a little more of the gallery.
- On 320px phones the header only fits because of D034's narrow-screen rules; adding a header item would break it.

## Where it shows
The "target size" block near the end of the `<style>` in `site/index.html`.
