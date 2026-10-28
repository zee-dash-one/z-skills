---
name: prompt-builder
description: >-
  Use when writing, refining or testing a prompt or system prompt for another
  LLM or agent to use (not media generation).
---
# Prompt builder

Output: the prompt in English, structured in Markdown. Keep it short; every line must change the model's behavior.

## Steps
1. Clarify only what is missing: target model/agent, goal, input it will receive, expected output, acceptance criteria.
2. Write the prompt with these blocks, in this order:
   - `## Context`: facts the model needs (domain, audience, constraints of the environment). No filler.
   - `## Goal`: what done looks like, in 1-3 sentences.
   - `## Approach`: how to work, in broad strokes (steps, tools, reasoning style). Prefer "research and compare options" over dictating a single solution when the best path is unknown.
   - `## Don't`: explicit anti-goals and forbidden actions.
   - `## Output format`: exact shape (schema, headings, length, language).
   - `## Validation`: how the model (or reviewer) checks the result before returning.
3. Add 1-2 short examples only if the format is ambiguous.
4. Self-check before delivering:
   - Each instruction is testable and not contradicted elsewhere.
   - No vague words ("good", "appropriate") without a criterion.
   - Secrets, personal data and tool-specific internals are not embedded.
5. If asked to test: write 3-5 test inputs (normal, edge, adversarial) with the expected behavior for each; for an A/B, change one variable at a time.
6. Deliver: the prompt in a code block plus 1-3 lines on what to watch when it runs. Save long prompts to a file and send the path.
