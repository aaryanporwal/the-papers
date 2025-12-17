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

- no training loop for every 