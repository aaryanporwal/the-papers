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

The paper reads almost modestly. They report better BLEU and faster training, but the bigger point is that self-attention is a general-purpose differentiable routing layer. A token forms a query, compares against keys, and pulls values. That is the mental model I want to keep.

Important: scaling this naively is quadratic in sequence length. At the time, maybe fine. Later [[flashattention]] makes the same math viable by treating memory movement as the bottleneck. So the long arc is:

[[attention]] idea -> [[scaling laws]] pressure -> hardware bottlenecks -> IO-aware kernels -> giant context windows.

## architecture bits I should remember

### scaled dot-product attention

QK^T / sqrt(d_k), softmax, times V. The sqrt is not decorative; it keeps logits from blowing up as dimensions grow. I always forget this and then wonder why temperature shows up everywhere later.

### multi-head attention

Instead of one huge attention op, split into heads. My current interpretation: heads can specialize in syntax-ish, locality-ish, copying-ish, etc. Not guaranteed, but a useful lens. Need to avoid overclaiming mechanistic interpretability from this.

### positional encoding

Sine/cosine positions are elegant but also slightly magical. Learned positions became common later. The important part is not the exact encoding, it is that [[attention]] itself is permutation invariant unless we inject order.

## links outward

- [[gpt3-few-shot-learners]]: decoder-only scaling + in-context learning makes transformers feel like a product surface
- [[flashattention]]: same equation, different system story
- [[vit-image-worth-16x16-words]]: patches become tokens, image modeling becomes sequence modeling
- [[chain-of-thought-prompting]] and [[deepseek-r1]]: reasoning traces riding on the transformer substrate
- [[mixtral-of-experts]]: sparse FFN experts inside the same block pattern

## doubts / TODO

- Need to re-read the exact masking setup in decoder self-attention.
- Is there a clean note somewhere on why additive attention lost to dot-product attention? come back later.
- The paper's training details matter less to me rn, but label smoothing probably deserves a separate [[optimization]] note.

Tiny personal takeaway: this is not just "attention good". It is "remove sequential dependency, expose compute, and use attention as soft content-addressed memory." That phrase is maybe too neat but useful.
