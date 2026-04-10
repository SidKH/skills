# Nagging

- Link: https://www.deceptive.design/types/nagging

## Definition

Repeatedly interrupt the user with prompts for a provider-preferred action, especially when rejection is temporary and the prompt keeps returning.

## Audit Cues

- repeated permission prompts with only `Not now` or similarly temporary dismissals
- reminder modals triggered by frequency counters, session counts, or recurring timers
- state that suppresses a prompt briefly but never records a durable opt-out
- onboarding or marketing prompts reappearing across screens after dismissal
- code designed to exhaust the user into consenting or upgrading

## Generic Example

A mobile app repeatedly asks the user to enable notifications. Dismissal only delays the prompt until later, and there is no persistent `never ask again` path.
