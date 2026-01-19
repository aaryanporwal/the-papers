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

Batch of image/text pai