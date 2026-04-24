---
tags: [reasoning, reinforcement-learning, rlhf, distillation, language-models]
date: 2026-04-19
time: 09:17
---

# DeepSeek-R1

Release-week chaos notes. Leaving these messy on purpose b/c that was the vibe.

## first reaction

Wait, this is open-ish and reasoning looks this strong? The disbelief is partly model quality, partly cost story, partly geopolitical Twitter noise. Need separate facts from hype.

## core thing

Use RL to elicit long [[reasoning]] behavior, with variants around cold-start data and distillation. The headline for me: strong reasoning can emerge from reinforcement learning pressure, not only from hand-written CoT demos.

Links screaming in the background: [[chain-of-thought-prompting]], [[lets-verify-step-by-step-prm]], [[RLHF]], [[dpo]], [[attention-is-all-you-need]].

## mechanisms I think I understand

- start from a strong base model
- RL rewards correctness / verifiable answers
- model learns to allocate more tokens to thinking
- distill reasoning behavior into smaller models

GRPO detail: group-based relative optimization instead of a full critic? I need to read this carefully. rn the optimizer math is fuzzzy.

## speculation / caution

Maybe the big lesson is not "RL solves reasoning" but "verifiable domains provide enough signal for RL to shape behavior." Math/code are special because answers can be checked. Open-ended tasks are harder.

Also there is a weird loop: [[chain-of-thought-pro