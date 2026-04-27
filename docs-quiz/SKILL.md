---
name: docs-quiz
description: Run an interactive documentation-based quiz for a user-selected technology and topic area. Use when the user wants to practice a framework, library, API, language feature, or other technical docs by choosing the correct snippet from two short examples.
disable-model-invocation: true
---

# Docs Quiz

Run a short, looping quiz based on current documentation for the technology and area the user names.

## Setup

1. Identify the technology and topic area from the user's request.
2. Read authoritative, current docs for that technology before the first question.
3. If the technology or topic area is missing, ask one concise clarification question.
4. Keep all questions focused on the requested area unless the user asks to change scope.

## Quiz Loop

For each round:

1. Pick one docs concept.
2. Create two short code snippets:
   - one correct
   - one incorrect
3. Randomize which snippet is correct.
4. Show only:
   - `1`
   - first snippet
   - `2`
   - second snippet
5. Wait for the user to answer `1` or `2`.
6. Tell the user whether they were correct or incorrect and why.
7. Continue with the next round in the same format.

## Answer Feedback

- Start with `Correct.` or `Incorrect.`
- Keep the explanation under 240 characters.
- Mention the specific rule or docs concept that decides the answer.
- Then immediately provide the next pair of snippets.

## Snippet Rules

- Keep snippets short and focused on one concept.
- Avoid trick questions based on formatting, naming, or unrelated style.
- Make the incorrect snippet plausibly wrong for the chosen concept.
- Add comments only when needed to make the contrast clear.
- Do not reveal which snippet is correct before the user answers.

## Documentation Rules

- Prefer official docs, API references, language specifications, or repository docs.
- For fast-moving technologies, verify current docs before generating questions.
- If docs are unavailable, say so and use the best authoritative source you can find.
