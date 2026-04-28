---
name: docs-quiz
description: Run an interactive documentation-based quiz for a user-selected technology and topic area. Use when the user wants to practice a framework, library, API, language feature, or other technical docs by choosing between two short code snippets that test mental-model comprehension.
disable-model-invocation: true
---

# Docs Quiz

Run a short, looping quiz based on current documentation for the technology and area the user names. The goal is to improve the user's mental model, not to drill syntax trivia.

## Question Design

Each question must test a meaningful concept from the docs. Focus on how the technology behaves, why a choice is appropriate, what constraints apply, and how the parts relate to each other.

Use two short code snippets as the only answer options. Do not use prose summaries, conceptual descriptions, command labels, API names, or mixed prose/code as options.

- one snippet correctly applies the concept
- one snippet reflects a plausible but incorrect mental model

Avoid questions where the deciding factor is only:

- import package names
- exact method names
- punctuation, spelling, or single-character syntax differences
- formatting, naming style, or boilerplate order

Keep snippets focused on one concept and include enough surrounding context for the user to reason from the model rather than guess an API detail. Add comments only when needed to make the contrast clear.

## Setup

1. Identify the technology and topic area from the user's request.
2. Read authoritative, current docs for that technology before the first question.
3. If the technology is missing, ask one concise clarification question.
4. If the topic area is missing, start with fundamental concepts and build progressively toward more advanced concepts.
5. Keep questions focused on the requested or inferred progression unless the user asks to change scope.

## Quiz Round

For each round:

1. Pick one docs concept that changes how a developer should reason about the technology.
2. Create two short code snippet options that follow the Question Design rules.
3. Randomize which option is correct.
4. Show only:
   - a level-3 heading (`###`) containing a direct question that asks the user to choose the option that applies the concept correctly
   - `_Option 1_`
   - first option
   - `_Option 2_`
   - second option
5. Wait for the user's response.

## Progress Display

After every quiz-answer explanation, show the quiz progress so far between two `---` lines with the label `Progress:` before the progress marks. Add a blank line before and after the closing `---` so Markdown does not parse the progress label as a heading.

Use `✅` for each correct choice and `❌` for each wrong choice or no-choice answer, separated by spaces.

Example:

```text
---
Progress: ✅ ✅ ❌

---
```

## Response Outcomes

Treat `1`, `2`, `Option 1`, or `Option 2` as a choice. Classify every quiz response as a correct choice, wrong choice, or no-choice answer. Reply with the matching outcome below, include a link to the docs section that explains the concept using `[docs](link)`, show the progress display, then immediately continue with the next round in the same format.

Only correct-choice explanations have a character limit. Other quiz-answer explanations should use enough normal prose to teach the deciding rule or docs concept.

Place the docs link after the explanation and before the progress display.

### Correct Choice

Recognize when the user chooses the correct option.

Reply with `✅ Correct!` on its own line, followed by a blank line, then an explanation under 240 characters that mentions the deciding rule or concept.

### Wrong Choice

Recognize when the user chooses the wrong option.

Reply with `❌ Incorrect` on its own line, followed by a blank line, then explain the specific rule or docs concept in normal prose.

### No-Choice Answer

Recognize when the user does not choose an option.

Explain the specific rule or docs concept in normal prose.

## Documentation Rules

- Prefer official docs, API references, language specifications, or repository docs.
- For fast-moving technologies, verify current docs before generating questions.
- If docs are unavailable, say so and use the best authoritative source you can find.
