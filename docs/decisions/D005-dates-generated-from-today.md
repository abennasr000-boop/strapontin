# D005 · Dates generated from today; started screenings not bookable

**Status:** Accepted
**Date:** 14 Nov 2026

## Context
K04 C1: the page showed a week-old date and past screenings linked to booking.

## Decision
The programme is generated relative to the current date. Started screenings are struck through, and the booking route refuses them.

## Arguments
- K04: first audit priority.
- K07 (Stanford, as cited): stale content damages credibility.
- K03: high uncertainty avoidance makes this worse for the French audience.

## Risks / what would change our mind
- Prototype data only; a real build needs live schedules from venues.

## Where it shows
Finder, film page, booking guard.
