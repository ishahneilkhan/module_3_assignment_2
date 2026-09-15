---
created: 2026-09-14
type: reference
status: complete
class: 6
tags: [edubridge, class-6, tasks]
project: EduBridge Bangladesh
---

# EduBridge BD: Booking Summary — Task Breakdown

**What this file is for:** the brief and the IA map broken into buildable
tasks, so `/frontend-design` runs on one task, not the whole product.

## In scope for this class

Only the **Booking Summary** screen from `ia-map.md` (item 4).

## Task list

1. **Structure the layout** — header (back button, title), tutor card,
   session-detail card, price-breakdown card, trust note, sticky CTA
   footer. Mobile width, ~390px.

2. **Wire every value to a token** — colors, spacing, radius, and type all
   pull from `tokens.md`. No hard-coded hex or px.

3. **Build the price breakdown** — session fee, platform fee, total — all
   visible on this screen, none deferred to a later step (contract:
   "no fee changes late in a flow").

4. **Write the trust note** — one line confirming bKash/Nagad payment and
   that the shown price is final, not a partial quote.

5. **Label the CTA for the real outcome** — "পেমেন্টে যান," not "Continue"
   — and make it touch-target sized (`--touch-min`, 48px).

6. **Build three extra states nobody asked for** — loading (session
   confirming, may be slow on 3G), error (slot taken before confirmation),
   edge case (tutor/student name long enough to test text wrapping).

## Explicitly not in this task

- Payment method selection screen (next stop on the map, separate task)
- bKash/Nagad sub-flow screens (separate task, `engagement.md` scope)
- Tutor Profile or Slot Selection screens (earlier stops, not touched here)

Keeping this task to one screen is what let `/frontend-design` run once,
against a locked token file, instead of guessing at five screens' worth of
undefined values at the same time.
