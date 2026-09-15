---
created: 2026-09-14
type: reference
status: complete
class: 6
tags: [edubridge, class-6, information-architecture]
project: EduBridge Bangladesh
---

# EduBridge BD: Information Architecture

**What this file is for:** which screens exist, what each is for, and how a
parent moves between them — mapped before any screen was built.

## Screens

1. **Home / Discovery** — Parent browses or searches tutors by subject,
   grade level, and location. Purpose: entry point, first trust signals
   (ratings, price range visible from the list).

2. **Tutor Profile** — Full detail on one tutor: qualifications, reviews,
   availability, price. Purpose: the decision point before committing to a
   booking.

3. **Slot Selection** — Parent picks a date/time from the tutor's open
   slots. Purpose: commits to one specific session.

4. **Booking Summary** *(the screen this class builds)* — Shows student,
   tutor, session time, subject, and total price with no fee hidden for
   later. Purpose: final review before payment, the highest-trust screen in
   the flow.

5. **Payment Method Selection** — bKash/Nagad shown first, card kept as the
   existing fallback. Purpose: matches local payment expectation.

6. **bKash/Nagad Flow (3–4 sub-screens)** — App-switch, PIN, OTP, hand-typed
   transaction ID, async verification wait. Purpose: handles the external
   payment gateway hand-off named in `engagement.md`.

7. **Confirmation / Receipt** — Booking confirmed, receipt shown. Purpose:
   the screen parents screenshot before they trust the booking is real.

8. **My Bookings (Parent Dashboard)** — Upcoming and past sessions.
   Purpose: reduces "did it go through?" support questions, drives repeat
   bookings.

## Movement between screens

```
Home → Tutor Profile → Slot Selection → Booking Summary → Payment Method
     → bKash/Nagad sub-flow → Confirmation → My Bookings (loop to Home)
```

## Where this class's screen sits

**Booking Summary** — one stop on this map, positioned right before payment.

- **Screen before it:** Slot Selection
- **Screen after it:** Payment Method Selection

This position is why the screen carries the full price breakdown and the
verified badge: it is the last screen before the parent commits to a
payment method, and the contract treats any fee revealed later than this
point as a hard blocker.
