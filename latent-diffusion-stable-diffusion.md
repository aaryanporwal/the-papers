---
tags: [diffusion, generative-vision, latent-space, text-to-image, multimodal]
date: 2026-01-28
time: 23:25
---

# Latent diffusion / Stable Diffusion

## one line

Do [[diffusion]] in a compressed latent space instead of pixel space, then condition on text to make image generation cheap enough to be practical.

## components

- autoencoder maps images to latents and back
- U-Net denoises latents over timesteps
- text conditioning steers generation
- cross-attention connects prompt tokens to image features

This is where [[attention]] shows up inside image generation, not just language.

## why latent matters

Pixel diffusion is expensive. Latent diffusion keeps perceptual structure while reducing spatial cost. That unlocks consumer-ish hardware and the whole Stable Diffusion explosion.

## reaction

The paper feels like a systems paper disguised as a generative modeling paper. The algorithmic idea is diffusion, but the practical leap is moving the expensive process into the right representation.

Links to [[clip]] 