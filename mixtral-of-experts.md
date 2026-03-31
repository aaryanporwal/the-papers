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
- router chooses top-k experts per token
- load balancing matters or experts collapse / get uneven traffic
- communication can dominate in distributed setups

## reaction

The model feels like a committee where each token gets routed to specialists. Nice story, but I should avoid anthropomorphizing. Router is just learned gating.

Links: [[attention-is-all-you-need]], [[transformers]], [[scaling laws]], [[deepseek-r1]].

## questions

How much specialization do experts actually learn? Are they topic experts, syntax experts, random capacity partitions? Need interpretability evidence.

Also MoE makes deployment less straightforward. Sparse compute sounds cheap until systems details arrive.
