---
tags: [vision-language, contrastive-learning, multimodal, zero-shot, retrieval]
date: 2026-01-19
time: 23:11
---

# CLIP

## gist

Train image and text encoders with a contrastive objective over huge noisy image-caption pairs. The result is a shared embedding space where text can classify images zero-shot.

## why this matters

[[clip]] feels like the internet-scale version of supervision. Instead of labeled classes, use natural language captions. It turns classification into retrieval/matching.

Connections: [[vit-image-worth-16x16-words]] for transformer vision, [[retrieval]] for embedding search, and [[latent-diffusion-stable-diffusion]] because text-image generation leans on CLIP-ish alignment ideas.

## mechanism

Batch of image/text pairs. Pull matching pairs together, push non-matching pairs apart. The simple contrastive setup is doing a lot.

Zero-shot classification trick: write prompts like "a photo of a {label}" and compare image embedding to text embeddings. Very clean, almost suspiciously clean.

## reactions

The data is noisy, but scale wins. Also the model inherits internet bias in a very direct way. Text supervision is flexible, but it drags culture with it.

Question: how much prompt wording affects reported zero-shot numbers? Probably a lot. prompt ensembling is a quiet hack.

## note to self

Read more about alignment between embedding geometry and generative guidance. I keep mixing CLIP as a model with CLIP as a cultural shorthand for vision-language grounding.
