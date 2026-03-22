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

Given prompt x, chosen y_w, rejected y_l. Increase relative logprob of chosen over rejected, controlled by beta and compared to reference policy. That is my plain-English version, check math later.

## reaction

DPO feels like one of those papers that wins because it turns a brittle pipeline into something ordinary engineers can use. Not necessarily better in every regime, but simpler enough to spread.

## links

[[RLHF]], [[lora]], [[deepseek-r1]], [[lets-verify-step-by-step-prm]].

## questions

- Does DPO overfit preference style quickly?
- How sensitive is beta?
- What kinds of preference data break the implicit reward assumption?

TODO: compare with IPO/KTO someday. too many acronyms.
