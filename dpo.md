---
tags: [alignment, preference-learning, finetuning, rlhf, language-models]
date: 2026-03-18
time: 16:01
---

# DPO

## one liner

Optimize a policy directly from preference pairs without training an explicit reward model or running RL.

## why this is interesting

[[instructgpt-rlhf]] uses reward model + PPO. [[dpo]] says the preference objective can be rewritten into a supervised-looking loss against chosen/rejected responses, with a reference model anchoring behavior.

Less moving parts. Much easier to run. Very attractive for alignment-ish finetuning.

## mechanism memory

Given prompt x, chosen y_w, rejected y_l. Increase relati