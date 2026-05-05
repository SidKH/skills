---
name: understand-diff
description: Run a short active-recall dialogue that helps the user understand their current unstaged code changes. Use when the user wants to understand, review, quiz themselves on, or explain a local diff before accepting, committing, merging, or shipping it.
disable-model-invocation: true
---

# Understand Diff

Help the user understand their current unstaged changes with the least friction possible. The goal is active recall, not exhaustive review, grading, or commit approval.

## Workflow

1. Inspect the unstaged diff with `git diff`.
2. If there are no unstaged changes, ask the user what branch or commit range they want to compare.
3. Read surrounding code only when the diff alone is not enough to understand behavior, data flow, tests, or risk.
4. Identify the highest-leverage thing the user should be able to explain.
5. Ask one open-ended question immediately.
6. Wait for the user's answer.
7. Give brief feedback, then either ask one useful follow-up or finish with a short summary.

## Question Style

- Ask the fewest questions that can produce real understanding.
- Prefer behavior, intent, data flow, risk, and tests over line-by-line trivia.
- Use open-ended prompts that require the user to explain in their own words.
- Do not use multiple choice unless the user is stuck and needs scaffolding.
- Do not announce a quiz plan, concept list, file count, or full diff summary before the first question.
- Do not reveal the answer before the user has attempted an explanation.

## Feedback

After each answer:

- say what the user got right
- point out the most important missing or incorrect part
- ask a sharper follow-up only if it would materially improve understanding
- give a small hint before giving a full explanation when the user is stuck

## Completion

Finish as soon as the user has shown enough understanding of the main changed behavior, reason for the change, and relevant risk or test implication.

End with a concise summary of:

- what the user demonstrated
- any important unresolved risk
- any useful verification step

Do not say the change is ready to commit. Say only what the user demonstrated about their understanding.
