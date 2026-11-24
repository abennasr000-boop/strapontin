# D019 · Accessibility and consent baseline

**Status:** Accepted
**Date:** 14 Nov 2026

## Context
K04 P1, I4 and the French legal context.

## Decision
Skip link, visible focus, text contrast ≥ 4.5:1, labels ≥ 12.5 px, keyboard-operable search and filters, reduced-motion support, wheelchair filter, cookie banner with equal "Refuser" and "Accepter".

## Arguments
- K04 P1, I4.
- K07: WCAG, CNIL.
- K03: consent clarity fits high uncertainty avoidance.

## Risks / what would change our mind
- Not audited with assistive technology. The seat map and the hover gallery need a screen-reader pass.

## Where it shows
Throughout.

## Update (24 Nov 2026): raised to AAA
**Status now:** Accepted; raised by D029. This record stays as the baseline: skip link, reduced motion, wheelchair filter, equal cookie buttons. The AA contrast rule here (4.5:1) is replaced by 7:1 (D030).

After the external review (F007), the target became WCAG 2.2 AAA with named exceptions (D029). Detail, one record per choice:
- D030: colour values for 7:1 text contrast;
- D031: accessible names, link context, status announcements, heading structure;
- D032: focus ring and dialog behaviour;
- D033: 44px targets;
- D034: dock filters as native selects.

Criteria, measurements and test method: K08. The "Not audited with assistive technology" risk above still holds.
