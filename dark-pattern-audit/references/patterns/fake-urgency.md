# Fake Urgency

- Link: https://www.deceptive.design/types/fake-urgency

## Definition

Push the user to act quickly by showing a deadline, countdown, or expiring offer that is misleading, automatically reset, or not tied to a real time limit.

## Audit Cues

- countdown timers that restart automatically
- sale-end copy without evidence of a real campaign end condition
- urgency banners driven by client-side timers alone
- reusable countdown widgets with looping or evergreen behavior
- offers that claim expiration while logic keeps them continuously available

## Generic Example

A sale banner counts down to zero, but the implementation resets the timer and relaunches the same campaign instead of ending the offer.
