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

The fragile bit is data. ViT underperforms convnets at smaller data regimes b/c the model has weaker built-in locality/translation priors. But on huge datasets it catches up or wins. So it is really a [[scaling laws]] note as mu