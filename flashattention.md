---
tags: [attention, efficient-attention, systems, memory-io, long-context]
date: 2026-02-24
time: 18:39
---

# FlashAttention

Short note because the idea is crisp.

## gist

Same exact [[attention]] result, but compute it with IO-aware tiling so the bottleneck is not constantly reading/writing huge attention matrices to HBM.

## why it matters

Naive attention materializes the N x N matrix. For long sequences this is memory traffic hell. [[flashattention]] fuses operations and tiles through SRAM, keeping numerically stable softmax online.

This is downstream of [[attention-is-all-you-need]] but feels like a hardware reality check: asymptotic FLOPs are not the whole story.

## takeaway

Memory movement is the enemy. The algorithmic math did not change; the schedule did.

Links: [[transformers]], [[scaling laws]], [[vit-image-worth-16x16-words]].

Question: revisit FlashAttention-2 later. Also I should learn the online softmax derivation instead of handwaving it.
