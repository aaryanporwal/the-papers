---
tags: [reasoning, chain-of-thought, prompting, in-context-learning, language-models]
date: 2026-01-16
time: 18:46
---

# Chain-of-thought prompting

## one sentence

For large enough LMs, showing intermediate reasoning steps in the prompt improves multi-step problem solving.

This is a prompting paper, but it hints at something deeper about [[reasoning]] representations inside [[transformers]].

## mechanism guess

CoT gives the model a pattern for decomposing a problem. Instead of jumping straight to the answer token, it emits intermediate text that can carry state. Maybe the text trace becomes a scratchpad. Maybe it just biases toward distributions where correct solutions live. both?

## notes

- works much better at 