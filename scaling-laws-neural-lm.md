---
tags: [scaling-laws, language-models, compute-optimality, forecasting, pretraining]
date: 2025-12-25
time: 09:44
---

# Scaling laws for neural language models

## core claim

LM loss follows smooth power laws with model size, data, and compute. Bigger systems are not random bets; they are somewhat forecastable.

This is the paper that makes [[scaling laws]] feel like engineering rather than folklore.

## what they measured

They vary parameters, dataset size, and compute, then fit predictable loss curves. The practical output is: if you have more compute, you can estimate where to spend it.

But this note needs the [[chinchilla]] correction: the original direction overfavored bigger models trained on too few tokens. Chinchilla says the compute-optimal frontier wants more data relative to params.

## why it matters

Be