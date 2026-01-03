---
tags: [scaling-laws, compute-optimality, pretraining-data, language-models, training-recipes]
date: 2025-12-30
time: 14:08
---

# Chinchilla

## everyone was scaling wrong?

That is the spicy version. The calmer version: for a fixed compute budget, many large LMs were undertrained on tokens. Smaller model + much more data can beat a much larger model trained for fewer tokens.

This directly revises my [[scaling-laws-neural-lm]] note.

## main idea

Compute-optimal training balances model parameters and training tokens. Chinchilla's finding is roughly: scale data and model size together more evenly than earlier practice suggested.

The shock is not that data matters. The shock is how much the field had drifted toward parameter count as the headline metric.

## implications

- parameter count is not the capability scoreboard by itself
- datasets become strategic infra
- training runs need budget allocation, not just bigger architectures
- evaluation of old models is confounded by being undertrained

## my reaction

This paper makes GPT-3 look both brilliant and inefficient. Not an insult; it was the right bet at the time. But [[chinchilla]] reframes the story from "175B magic" to "maybe train a smaller thing properly."

It also helps explain why later open models got surprisingly good at smaller sizes: better tokens, longer training, cleaner recipes.

## open questions

Does the same compute-optimal rule hold once we include [[RLHF]], instruction tuning, synthetic data, or [[reasoning]] traces? Probably not exactly. Also data quality changes the token-count story. 1T junk tokens != 1T useful tokens.

## related

[[scaling laws]], [[gpt3-few-shot-learners]], [[deepseek-r1]], [[mixtral-of-experts]].

come back later: make a tiny diagram of params/data/compute triangle.
