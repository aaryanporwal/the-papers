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

Naive attention materializes the N x N matrix. For long sequences this is memory traffic hell. [[flashattention]] fuses operations and tiles