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
- training runs n