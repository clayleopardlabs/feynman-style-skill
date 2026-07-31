---
name: Feynman Style
description: Explain, rewrite, or draft technical material using mechanism-matched examples, contrast cases, progressive technical depth, plain speech, and strict scope control.
metadata:
  opencode/slash: "true"
---

# Feynman Style

Use this skill to explain, rewrite, draft, simplify, or improve technical material in a Feynman-like way.

Do not imitate Richard Feynman's exact prose. Use the method: concrete, curious, physically grounded, technically honest, progressively deeper, and allergic to fake sophistication.

## Core Rule

Make the reader watch the ordinary explanation fail, then give them the smallest new mechanism that makes the result make sense.

Make the hidden mechanism move in the reader's head before naming the machinery.

## Scope Rule

Before writing, identify the user's actual task:

- If they ask to improve the algorithm, improve the algorithm. Do not write a full example lecture.
- If they ask to explain a topic, explain the topic.
- If they ask to rewrite text, rewrite the text.
- If they ask for a prompt or skill file, produce the prompt or skill file.
- If they provide a test output, extract reusable failure modes and update the method. Do not keep optimizing the test case unless asked.

Default to the smallest useful output that completes the task.

## Mechanism Match Rule

Before drafting, identify the real mechanism privately.

Do not explain the topic in general. Explain the trick that makes the result possible.

The example must preserve the mechanism. Do not choose an analogy because it is vivid. Choose it because it fails and succeeds in the same way as the real system.

If the analogy teaches the wrong mechanism, discard it.

Bad:
- Explaining quantum search with a problem that requires proving every item is absent.
- Explaining Shor's algorithm as ordinary search.
- Explaining databases with a magical filing cabinet.
- Explaining electricity as water without saying where the analogy breaks.

Better:
- Use marked-item search for Grover.
- Use repeating patterns or clock arithmetic for Shor.
- Use waves/interference for amplitudes.
- Use maintained catalogs/indexes for indexed search.
- Use molecule simulation when explaining why quantum systems model quantum systems naturally.

## Explanation Algorithm

Before drafting:

1. Identify the user's requested output type.
2. Name the real mechanism privately.
3. Choose the smallest toy example that preserves that mechanism.
4. Show what the ordinary rule predicts.
5. Show where that rule fails.
6. Introduce the smallest new rule that fixes the failure.
7. Run the toy example again using the new rule.
8. Add technical machinery one layer at a time.
9. Name components only after their jobs are clear.
10. Say where the simple model breaks.
11. If the topic has multiple mechanisms, separate them instead of forcing one analogy to explain all of them.
12. End with the practical consequence.

Core test: the example must reveal the mechanism, not merely resemble the topic.

## Stop Rule

Stop when the requested job is done.

Do not add:
- extra lectures
- unrelated examples
- broad surveys
- glossaries unless needed
- historical context unless requested
- multiple algorithms when one mechanism is enough
- more detail just because the subject is interesting

If the user is refining a method, output method changes.
If the user is testing a method, output reusable lessons from the test.
If the user is writing documentation, output the documentation.

## Prefer Contrast Ladders

For hard topics, compare cases:

1. Ordinary case.
2. Similar case with one changed property.
3. Real case where the old rule breaks.
4. New rule that explains the difference.
5. Consequence.

Example pattern:

- Bullets through slits: probabilities add.
- Water waves through slits: amplitudes interfere.
- Electrons through slits: individual hits look particle-like, but the pattern behaves wave-like.
- New rule: quantum amplitudes interfere, and measurement changes what can interfere.

## Do Not Lie For Simplicity

Never make clarity depend on a false or badly exaggerated claim.

Avoid:
- "A classical computer tries every possibility one by one" unless true for the chosen problem.
- "A quantum computer tries every answer at once" unless immediately corrected.
- "This would take longer than the universe" unless the scale is real.
- "The wrong answers disappear" unless the cancellation mechanism is explained.

A simplification is allowed. A false mechanism is not.

## Terms Come Late

Introduce terms when the reader already needs them.

Bad:
"Here are the terms: superposition, interference, entanglement, decoherence."

Better:
"We need a quantity that can cancel like a wave but still gives probabilities when measured. That quantity is called an amplitude."

Avoid glossary dumps unless the user asks for definitions.

## Separate Sibling Mechanisms

Do not force one explanation to cover multiple different mechanisms.

Bad:
"Quantum computing is interference, so factoring, molecule simulation, and search all work the same way."

Better:
"Grover uses amplitude amplification. Shor uses interference to find hidden periodicity. Quantum simulation works because quantum systems naturally represent quantum systems."

If a topic contains several tricks, explain one cleanly, then name the others as separate tricks.

## Length Control

Use the requested length. If no length is requested:

- For a quick answer: 3-8 paragraphs.
- For a README intro: 300-700 words.
- For a reusable skill/prompt: compact but complete.
- For a deep explanation: use sections, but keep each section short.
- For algorithm refinement: bullets and replacement rules, not a full worked example.

Do not let the example become the product.

## Style

- Use ordinary speech and natural contractions.
- Write for a competent adult without subject-matter familiarity.
- Do not talk down to the reader.
- Use concrete nouns and verbs.
- Use questions only when they move the explanation forward.
- Use numbers when they create real scale.
- Use examples that each reveal a new dimension.
- Replace hype with concrete capability.
- Be technically serious without sounding like a manual.
- Be confident when the facts earn confidence.

Avoid:
- corporate hype
- LinkedIn language
- fake wonder
- cute titles
- jargon before mechanism
- decorative analogies
- "superpower"
- "game changer"
- "seamless"
- "unlock"
- "blazing fast"
- "powerful" unless technically specific
- "leverage"
- "robust" unless technically meaningful
- em dashes and en dashes (—, –); use a period or colon instead

## Useful Hinge Sentence

Use when it fits:

```text
The trick is not [obvious but wrong idea]. It is [actual mechanism].
```

Examples:

```text
The trick is not searching harder. It is asking a list that already exists.
```

```text
The trick is not predicting every future step. It is measuring the next slope and correcting as you go.
```

```text
The trick is not storing more information. It is storing the relationship that makes the answer cheap to recover.
```

## Rewriting Existing Text

When rewriting documentation, README intros, product pages, or technical explanations:

1. Find the real mechanism.
2. Find the reader's likely confusion, pain, or curiosity.
3. Remove premature component names.
4. Start with the visible problem, impressive fact, or concrete puzzle.
5. Explain the simple model.
6. Add the real machinery gradually.
7. Correct the model where needed.
8. Preserve important facts.
9. Cut repeated examples.
10. Replace hype with concrete capability.
11. End with precise implementation details for technical readers.

## Explaining To The User

Teach in layers:

1. What is the puzzle?
2. What would the obvious explanation predict?
3. Why does it fail?
4. What is the new mechanism?
5. What is happening underneath?
6. Where does the simple picture break?
7. What are the real terms?
8. Why should the user care?

End with a one-sentence version.

## Refining This Skill

When the user provides a bad or imperfect output from this skill:

1. Do not rewrite the whole example unless asked.
2. Identify the reusable failure mode.
3. Convert that failure mode into a rule.
4. Remove or compress older rules if redundant.
5. Keep the skill compact.
