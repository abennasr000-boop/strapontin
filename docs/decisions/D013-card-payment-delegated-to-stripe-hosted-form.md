# D013 · Card payment delegated to Stripe hosted form

**Status:** Accepted
**Date:** 14 Nov 2026

## Context
K02 constraint: card numbers must not be stored.

## Decision
The payment step offers methods and hands card entry to the provider’s hosted form. The prototype has no card fields and states that payment is simulated.

## Arguments
- K02 constraint.
- K07: card data should not touch our page.
- K03: stating this openly supports trust.

## Risks / what would change our mind
- Pass Culture and carnet payment are shown but their real integration is unknown.

## Where it shows
Booking step 4.
