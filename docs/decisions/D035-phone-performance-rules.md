# D035 · Phone performance rules: what may re-render, and what is too costly

**Status:** Accepted
**Date:** 24 Nov 2026

## Context
F006: on a phone the search field could not be typed in, and scrolling or filtering glitched. The cause was that every browser `resize` event rebuilt the dock and the whole gallery. Phones fire `resize` when the address bar hides during scrolling and when the keyboard opens. Each rebuild destroyed the field being typed in and redrew every poster.

## Decision
1. **Resize rules:**
   - **A height-only resize never re-renders anything.** Only a real width change re-lays out, and the gallery is rebuilt only when its column count changes or a tile is open.
   - **The dock is never rebuilt while in use.** Its labels are updated in place (`syncDock()`); the search field and its text survive.
2. **Keyboard rules:**
   - **Android:** the viewport declares `interactive-widget=resizes-content`, so the keyboard pushes the page up instead of covering the dock.
   - **iOS:** `visualViewport` gives the keyboard height, and the dock and its suggestions move above it. This applies only while the search field has focus and the gap is keyboard-sized (over 100px). A smaller gap is browser chrome, and reacting to it made the dock jump.
3. **Touch-screen rules:**
   - **No backdrop blur** on the dock on touch screens. It is costly over scrolling images, and the dock is nearly opaque anyway.
   - **No hover effects** on screens without hover (they stick after a tap).
4. **Posters:**
   - Fetched in parallel, as 640px thumbnails when the original is larger. Originals can be several MB each.
   - The local cache key changed (`img2`), so browsers drop previously cached originals.
5. **Changing a filter returns to the results:** if the visitor has scrolled past the top of the results, the page scrolls back to it, so a shorter list never leaves them looking at empty space.

## Arguments
- F006.
- Judgement, from reproducing the faults in Chromium phone emulation: the rules remove the causes, not just the symptoms.

## Risks / what would change our mind
- Not yet confirmed on real iPhones and Android phones. The iOS keyboard offset is the part most likely to need tuning.
- The 640px thumbnail size is a guess for a two-column phone grid at 2× density; large desktop tiles may look soft.

## Where it shows
The `resize` and `visualViewport` handlers, `refreshHome()`, `loadPosters()`, and the `@media(pointer:coarse)` and `@media(hover:none)` styles in `site/index.html`.
