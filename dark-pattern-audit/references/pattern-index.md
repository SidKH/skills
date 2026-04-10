# Dark Pattern Catalog

Read this file first. Use it to identify candidate patterns, then open only the matching detailed files in `references/patterns/`.

Each detailed file contains:
- a neutral definition
- practical audit cues for static code and copy review
- a generic example with no company names
- the official reference link

## Patterns

- [comparison-prevention.md](./patterns/comparison-prevention.md): complex plan comparison, fragmented pricing, feature bundles that are hard to evaluate
- [confirmshaming.md](./patterns/confirmshaming.md): opt-out labels that shame or guilt the user
- [disguised-ads.md](./patterns/disguised-ads.md): ads styled like native UI or content
- [fake-scarcity.md](./patterns/fake-scarcity.md): misleading low-stock or high-demand messages
- [fake-social-proof.md](./patterns/fake-social-proof.md): fabricated reviews, testimonials, or activity notices
- [fake-urgency.md](./patterns/fake-urgency.md): misleading countdowns or time-limited pressure
- [forced-action.md](./patterns/forced-action.md): users must do something unrelated or undesirable to continue
- [hard-to-cancel.md](./patterns/hard-to-cancel.md): signup is easy but cancellation is obstructed
- [hidden-costs.md](./patterns/hidden-costs.md): fees appear late after user commitment
- [hidden-subscription.md](./patterns/hidden-subscription.md): recurring charges are created without clear disclosure and explicit consent
- [nagging.md](./patterns/nagging.md): repeated interruptions pushing the user toward a provider-preferred action
- [obstruction.md](./patterns/obstruction.md): extra hurdles are placed in the path of a disfavored action
- [preselection.md](./patterns/preselection.md): defaults are already chosen to steer the user
- [sneaking.md](./patterns/sneaking.md): unwanted items or consequences are quietly introduced
- [trick-wording.md](./patterns/trick-wording.md): ambiguous or misleading language causes mistaken actions
- [visual-interference.md](./patterns/visual-interference.md): information is hidden, obscured, or visually downplayed

## Confidence Reminder

- Report only `likely` or `possible` findings.
- Use `insufficient evidence` internally and omit those sections from the final report.
- Static code review can identify cues, copy, and logic, but cannot prove every runtime experience.
