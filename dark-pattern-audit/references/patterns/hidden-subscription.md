# Hidden Subscription

- Link: https://www.deceptive.design/types/hidden-subscription

## Definition

Enroll the user in a recurring payment or subscription without clear disclosure and explicit consent, often by tying the recurring charge to an action that appears to be one-time or unrelated.

## Audit Cues

- recurring billing created as a side effect of another action
- subscription terms absent or visually downplayed near the triggering control
- code paths that add recurring charges without a dedicated confirmation step
- invite, sharing, upgrade, or purchase flows that silently create paid seats or renewals
- billing logic relying on stored payment details without a fresh consent surface

## Generic Example

A collaboration flow lets a user grant edit access, but the underlying billing code quietly adds a recurring paid seat with little or no disclosure in the UI.
