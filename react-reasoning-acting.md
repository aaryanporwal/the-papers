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

It is almost embarrassingly simple, but it gives the LM a loop. [[retrieval]] can be an action; web search can be an action; database lookup ca