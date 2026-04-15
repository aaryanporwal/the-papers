---
tags: [reasoning, process-supervision, reward-models, chain-of-thought, alignment]
date: 2026-04-06
time: 23:53
---

# Let's verify step by step / PRM

## gist

For math reasoning, train process reward models to judge intermediate steps, not just final answers. Supervise the path.

This connects directly to [[chain-of-thought-prompting]]: if the model emits steps, maybe we can evaluate those steps.

## outcome vs process

Outcome supervision: final answer correct? Process supervision: is each reasoning step valid?

The paper argues process supervision can be more effective and more aligned for complex reasoning. It gives denser feedback and catches lucky wrong solutions.

## reaction

This makes intuitive sense. If a student guesses the final number, we do not want to reward the proof. Same for models. But labeling steps is expensive and subjective in messy domains.

## links

[[reasoning]], [[RLHF]], [[deepseek-r1]], [[dpo]], [[chain-of-thought-prompting]].

## questions

- How scalable is step labeling outside math?
- Can a PRM be gamed by plausible-looking steps?
- Does process supervision improve hidden reasoning or just visible traces?

TODO: revisit verifier-guided search. This paper seems like a key prelude to later reasoning models.
