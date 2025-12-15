---
tags: [transformers, vision, attention, representation-learning, scaling-laws]
date: 2025-12-09
time: 22:13
---

# ViT - image is worth 16x16 words

## gist

Treat image patches like tokens and feed them to a mostly standard [[transformers]] encoder. The surprising part is how little image-specific inductive bias is needed once scale is high enough.

Patchify image -> linear projection -> add position embeddings -> class token -> transformer encoder -> classifier.

## reaction

This paper is one of those "wait, can we just..." papers. It leans heavily on the success of [[attention-is-all-you-need]] but asks whether convolutions are required for vision. Answer: not always, if you have enough pretraining data.

The fragile bit is data. ViT underperforms convnets at smaller data regimes b/c the model has weaker built-in locality/translation priors. But on huge datasets it catches up or wins. So it is really a [[scaling laws]] note as much as a vision note.

## mechanism notes

- 16x16 patches become the visual vocabulary
- absolute positions are needed since patch order is otherwise not in the content
- the class token feels borrowed from BERT and slightly arbitrary but works
- attention lets distant patches interact early, unlike deep conv stacks

## questions

Why 16? It is a compute/sequence-length compromise, not a sacred number. Smaller patches = more tokens = quadratic attention pain. This links forward to [[flashattention]] and efficient attention variants.

Also: I should compare this with [[clip]] because CLIP uses visual encoders but the product-level magic is cross-modal contrastive learning, not patch tokenization alone.

## takeaway

Vision can be language-shaped if you choose the right tokenization. That sounds too broad, but the paper made it feel plausible.

TODO: revisit DeiT and data-efficient training, since this note is too pretraining-centric atm.
