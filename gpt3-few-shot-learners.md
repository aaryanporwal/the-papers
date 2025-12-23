---
tags: [language-models, scaling-laws, in-context-learning, prompting, transformers]
date: 2025-12-17
time: 15:55
---

# GPT-3 - language models are few-shot learners

## one line

Scale a decoder-only [[transformers]] language model enough and prompting starts to look like task adaptation without gradient updates.

## what stuck

The paper's real claim is not just "bigger is better". It is that the interface changes. You can put examples in the context window and the model imitates the task. That is [[in-context learning]], not finetuning.

This is downstream of [[attention-is-all-you-need]] and basically parallel to [[scaling-laws-neural-lm]]. GPT-3 makes the scaling curve feel like an interaction design discovery.

## few-shot / one-shot / zero-shot

The examples in the prompt become a temporary dataset. I keep wanting to call it a little program, but that is risky. It is more like pattern completion over task demonstrations.

Still, the user-facing effect is huge:

- no training loop for every task
- prompt engineering becomes a real thing, for better/worse
- benchmark evals get blurry because task descriptions matter a lot

## doubts

The paper is impressive but also pre-[[RLHF]]. Raw LM behavior is not aligned to helpful instruction following. That is why [[instructgpt-rlhf]] matters so much: same base capability, different objective at the interface.

I also want to understand how much of GPT-3's few-shot behavior is memorized task format vs genuine abstraction. afaik still unsettled.

## connections

- [[chain-of-thought-prompting]] extends the prompt interface by adding reasoning traces
- [[rag-knowledge-intensive-nlp]] handles factual gaps with external memory instead of just parametric memory
- [[lora]] later makes task adaptation cheap when prompting is not enough
- [[deepseek-r1]] shows reasoning can be pushed by RL on top of this general substrate

Personal note: this is where language models stop feeling like classifiers and start feeling like strange programmable text engines.
