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

The paper argues process supervision can be more effective and more aligned for complex reasoning. It gives 