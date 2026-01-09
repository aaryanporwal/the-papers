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

This is the bridge from [[gpt3-few-shot-learners]] to ChatGPT-style products. Raw next-token prediction is not enough b/c the user wants help, not a plausible continuation of internet text.

But [[RLHF]] also introduces weirdness: reward hacking, over-politeness, refusal style, hidden preference biases. It makes models usable and also shapes their personality.

## links

- [[dpo]] simplifies preference optimization later, removing explicit RL loop
- [[lets-verify-step-by-step-prm]] uses process-level feedback for reasoning tasks
- [[deepseek-r1]] pushes RL more directly for reasoning behavior
- [[chain-of-thought-prompting]] changes what users ask the model to emit

## questions

How much does the SFT stage matter vs reward optimization? Need better intuition. Also PPO details are still fuzzy to me, esp KL penalty against the reference model.

Personal shorthand: pretraining gives broad competence; RLHF changes the affordance surface.
