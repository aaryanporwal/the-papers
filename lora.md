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

[[gpt3-few-shot-learners]] says prompting can adapt behavior, but prompts are not always enough. [[lora]] gives a middl