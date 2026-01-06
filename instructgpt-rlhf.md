---
tags: [alignment, rlhf, instruction-tuning, preference-learning, language-models]
date: 2026-01-07
time: 01:01
---

# InstructGPT / RLHF

## gist

Take a pretrained LM and optimize it to follow human instructions using supervised demonstrations + reward modeling + PPO. [[RLHF]] turns capability into something closer to a helpful assistant.

## pipeline

1. collect human-written demonstrations
2. finetune model supervised on those demos
3. collect preference comparisons between outputs
4. train reward model
5. optimize policy against reward model

The model gets smaller than GPT-3 but feels more useful. That is the whole point: objective/interface alignment beats raw scale for many user tasks.

## reaction

This is the bridge from [[gpt3-few-shot-learners]] to ChatGPT-style products. Raw next-token prediction is not enou