---
tags: [finetuning, parameter-efficient, adapters, transformers, alignment]
date: 2026-02-18
time: 14:13
---

# LoRA

## one sentence

Freeze the base model and train low-rank update matrices for selected weights, making adaptation cheap.

## idea

Instead of updating W directly, learn a low-rank delta: BA. The rank is small, so parameter count and optimizer state drop massively. At inference, the update can be merged into the base weight.

This is very practical [[finetuning]] tech for [[transformers]].

## why I care

[[gpt3-few-shot-learners]] says prompting can adapt behavior, but prompts are not always enough. [[lora]] gives a middle path: specialize without full finetuning cost.

## notes

- often applied to attention projection matrices
- rank controls capacity/cost
- storage becomes tiny adapters instead of full model copies
- works b/c task-specific updates seem low intrinsic-rank

## questions

Why does low-rank adaptation work so well across so many tasks? Is it about pretrained representations already having most directions available? Need a mechanistic note.

Connects to [[dpo]] and [[RLHF]] when preference tuning needs to be parameter-efficient.

Small reaction: this is one of those papers whose importance is measured by how many repos quietly depend on it.
