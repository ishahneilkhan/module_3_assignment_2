---
created: 2026-09-14
type: reference
status: complete
class: 6
tags: [edubridge, class-6, build-notes]
project: EduBridge Bangladesh
---

# EduBridge BD: Build Notes — Booking Summary Screen

## Two directed fixes

**Fix 1 — CTA padding.**
Changed the CTA button's vertical padding from an initial 12px to
`--space-md` (16px), bringing the total tap height to `--touch-min` (48px).
Reason: 48px is the thumb-reachable minimum on the mid-range Android floor
this project is built against — not a visual preference, a token the
project already committed to in `tokens.md`.

**Fix 2 — Fee breakdown made explicit, not summarized.**
The first draft showed a single "Total: ৳850" line. Changed it to three
rows — session fee, platform fee, total — each visible before payment.
Reason: `claude-contract.md` names late fee reveals as a hard blocker, and
a single summarized total hides which part is the platform's cut, which is
exactly the kind of thing a first-time bKash/Nagad user screenshots and
questions.

## The line this screen answers

From `brief-v3-interrogated.md`:

> "The brief measures success by tutor signups, but the parent is the one
> who books and pays."

This screen is the direct design response to that finding. Because the
parent — not the tutor — is the primary user of this screen, every element
on it is ordered for a parent's trust and cost concerns: the full price
breakdown is shown before payment (not summarized, not deferred), the
verification badge names what was actually checked, and the CTA is labeled
for the outcome a parent cares about ("পেমেন্টে যান") rather than a generic
"Continue." If this screen had been built against the brief's original
metric (tutor signups), it would have optimized for getting the tutor's
profile seen, not for a parent finishing a booking with full cost
information in hand.

## Before / after

- **Before:** `critique-before.html` — the first, uncritiqued draft
  (centered hero, purple gradient CTA, price in small grey text, no fee
  breakdown).
- **After:** `my-booking-screen.html` — the shipped screen, tokens traced,
  price breakdown explicit, CTA sized to the touch-target token.
