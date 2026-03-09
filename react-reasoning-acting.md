---
tags: [agents, tool-use, reasoning, chain-of-thought, retrieval]
date: 2026-03-03
time: 15:37
---

# ReAct - reasoning and acting

## gist

Interleave reasoning traces with actions against an environment/tool. The model thinks, acts, observes, then continues.

This bridges [[chain-of-thought-prompting]] and tool use. Instead of reasoning in a sealed text box, the model can query external state.

## pattern

Thought -> Action -> Observation -> Thought -> ... -> Answer.

It is almost embarrassingly simple, but it gives the LM a loop. [[retrieval]] can be an action; web search can be an action; database lookup can be an action.

## why useful

- reduces hallucination by letting model check facts
- makes trajectories inspectable
- handles tasks where info is not in weights
- gives a framework for agents before the word got overloaded

## concern

Readable traces are not guaranteed faithful. Also tool errors can poison the next reasoning step. Need evals for the loop, not just final answer.

Links: [[rag-knowledge-intensive-nlp]], [[reasoning]], [[deepseek-r1]], [[lets-verify-step-by-step-prm]].

personal note: this is basically the seed of a lot of agent scaffolding. More important as a pattern than as a benchmark result.
