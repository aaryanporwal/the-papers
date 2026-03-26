---
tags: [mixture-of-experts, sparse-compute, transformers, scaling-laws, inference]
date: 2026-03-26
time: 11:57
---

# Mixtral of Experts

## gist

Sparse [[mixture-of-experts]] transformer: many FFN experts, router selects a small subset per token, so active compute is much lower than total parameters.

## why it matters

It decouples parameter count from inference compute. You can have a big capacity model without activating all weights for every token.

This is a scaling strategy next to [[chinchilla]] and [[scaling-laws-neural-lm]], not a replacement. More params, sparse activation, routing headaches.

## mechanism notes

- MoE usually swaps dense FFN block for expert FFNs
- ro