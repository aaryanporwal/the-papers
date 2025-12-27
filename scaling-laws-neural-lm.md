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

Before this, "train a bigger transformer" could sound like brute-force optimism. After this, scaling becomes a roadmap. [[gpt3-few-shot-learners]] is almost the cultural proof point.

## things I keep mixing up

- compute-limited vs data-limited regimes
- irreducible loss term vs reducible power-law part
- whether downstream abilities follow the same smoothness as pretraining loss (not exactly)

## reaction

There is a slightly dangerous vibe here: smooth loss curves seduce people into believing all progress is predictable. But capabilities can still appear abruptly from our measurement POV. The loss may be smooth while usefulness is lumpy.

Links: [[attention-is-all-you-need]], [[chinchilla]], [[mixtral-of-experts]], [[deepseek-r1]].

TODO: add equation details later; rn the conceptual takeaway matters more than exponents.
