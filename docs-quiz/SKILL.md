---
name: docs-quiz
description: Run an interactive documentation-based quiz for a user-selected technology and topic area. Use when the user wants to practice a framework, library, API, language feature, or other technical docs by choosing between two short examples that test mental-model comprehension.
disable-model-invocation: true
---

# Docs Quiz

Run a short, looping quiz based on current documentation for the technology and area the user names. The goal is to improve the user's mental model, not to drill syntax trivia.

## Question Design

Each question must test a meaningful concept from the docs. Focus on how the technology behaves, why a choice is appropriate, what constraints apply, and how the parts relate to each other.

Use two short options as evidence for the concept:

- one option correctly applies the concept
- one option reflects a plausible but incorrect mental model

Avoid questions where the deciding factor is only:

- import package names
- exact method names
- punctuation, spelling, or single-character syntax differences
- formatting, naming style, or boilerplate order

Keep options focused on one concept and include enough surrounding context for the user to reason from the model rather than guess an API detail. Add comments only when needed to make the contrast clear.

## Setup

1. Identify the technology and topic area from the user's request.
2. Read authoritative, current docs for that technology before the first question.
3. If the technology is missing, ask one concise clarification question.
4. If the topic area is missing, start with fundamental concepts and build progressively toward more advanced concepts.
5. Keep questions focused on the requested or inferred progression unless the user asks to change scope.

## Quiz Loop

For each round:

1. Pick one docs concept that changes how a developer should reason about the technology.
2. Create two short options that follow the Question Design rules.
3. Randomize which option is correct.
4. Show only:
   - a direct question that asks the user to choose the option that applies the concept correctly
   - `Option 1`
   - first option
   - `Option 2`
   - second option
5. Wait for the user to answer `1`, `2`, `Option 1`, or `Option 2`.
6. If the user answers correctly, follow the correct-answer feedback rules, then immediately continue with the next round in the same format.
7. If the user answers incorrectly, says they do not know, or gives an uncertain answer, follow the incorrect-answer feedback rules and stop the quiz.
8. If the next user message is exactly `continue`, continue the quiz with the next round.
9. If the next user message is anything else, answer it normally and do not continue the quiz.

## Answer Feedback

- Start with `Correct.` for correct answers and `Incorrect.` for wrong choices. Do not use `Incorrect.` when the user says they do not know, asks to learn, or gives another non-answer.
- For correct answers, keep the explanation under 240 characters, mention the rule or concept that decides the answer, add a blank line followed by `---` on its own line, then immediately provide the next pair of options.
- For wrong choices, unknown replies, learning requests, or uncertain answers, explain the specific rule or docs concept in normal prose without the 240-character limit.
- After explaining a wrong choice, unknown reply, learning request, or uncertain answer, end with: `To continue the quiz, send "continue".`

## Documentation Rules

- Prefer official docs, API references, language specifications, or repository docs.
- For fast-moving technologies, verify current docs before generating questions.
- If docs are unavailable, say so and use the best authoritative source you can find.
