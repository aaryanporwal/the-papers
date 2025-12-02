---
tags: [transformers, attention, architecture, sequence-modeling, foundation-models]
date: 2025-12-02
time: 14:31
---

# Attention Is All You Need

First pass notes on the [[transformers]] paper. Still feels weird that the title is so casual for the thing that ate the whole field.

## one sentence

Replace recurrence/convolution with stacked self-[[attention]] + feed-forward blocks, then let parallel hardware do the rest.

## what actually changes

- encoder/decoder stays, but the sequence mixing is all attention
- multi-head = several learned views into token-token relationships, not one giant similarity table
- positional encodings patch over the no-recurrence problem
- residuals + layer norm + FFN keep it trainable

The central move: every token can look at every other token in one step. For translation this removes the RNN bottleneck, but retrospectively it is more like the base substrate for [[gpt3-few-shot-learners]], [[vit-image-worth-16x16-words]], and honestly [[deepseek-r1]].

## retrospective reaction

The paper reads almost modestly. They report better BLEU and faster training, but the bigger point is that self-attent