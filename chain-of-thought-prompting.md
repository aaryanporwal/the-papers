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

- works much better at larger scale, linking to [[scaling laws]]
- few-shot exemplars matter
- arithmetic, symbolic reasoning, commonsense tasks improve
- not the same as proof; fluent steps can still be wrong

## links forward

[[lets-verify-step-by-step-prm]] asks whether we should supervise the steps, not just final answer. [[deepseek-r1]] goes further with RL and long reasoning traces. [[react-reasoning-acting]] uses reasoning text interleaved with tool actions.

## discomfort

CoT is useful but also leaks hidden reasoning into user-visible text, and sometimes models rationalize. I need to be careful saying "the model reasoned" just because the trace is readable.

TODO: compare with scratchpad, self-consistency, and verifier-based decoding.
