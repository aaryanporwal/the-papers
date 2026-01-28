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

T