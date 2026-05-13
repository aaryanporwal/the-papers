# The Papers

These are my personal notes, written for myself, on breakthrough AI papers that changed the direction of the field. The organizing principle is not chronology alone. Each paper here shifted what researchers tried next, what companies invested in, or what became practical to build.

They are informal: each file captures the core idea, the mechanism worth remembering, why the paper mattered, and what questions are still unresolved.

## Wave 1 - The Architecture That Started It All

| Paper | Why it mattered |
| --- | --- |
| [Attention Is All You Need](attention-is-all-you-need.md) | Replaced recurrence and convolution with self-attention as the main sequence-mixing primitive. This became the substrate for modern language models, vision transformers, multimodal models, and reasoning systems. |
| [ViT - An Image is Worth 16x16 Words](vit-image-worth-16x16-words.md) | Showed that images could be treated as token sequences. With enough data, Transformers could compete with or beat convolutional networks, weakening CNNs as the default vision architecture. |

## Wave 2 - Scale Is All You Need

| Paper | Why it mattered |
| --- | --- |
| [GPT-3 - Language Models are Few-Shot Learners](gpt3-few-shot-learners.md) | Made scale feel like an interface breakthrough, not just a benchmark trick. Prompting became a way to adapt models without gradient updates. |
| [Scaling Laws for Neural Language Models](scaling-laws-neural-lm.md) | Turned bigger-model training from brute-force optimism into something closer to forecastable engineering. Labs could estimate returns before spending the compute. |
| [Chinchilla](chinchilla.md) | Corrected the field's scaling recipe: many large models were too parameter-heavy and too undertrained on tokens. It made data volume and compute-optimal training central. |

## Wave 3 - Making Models Actually Useful

| Paper | Why it mattered |
| --- | --- |
| [InstructGPT / RLHF](instructgpt-rlhf.md) | Bridged raw pretrained language models and assistant-like products. It showed that aligning the objective and interface could matter more than raw model size. |
| [Chain-of-Thought Prompting](chain-of-thought-prompting.md) | Showed that large models can solve harder tasks when prompted to emit intermediate reasoning steps. It made reasoning feel elicitable, not only trainable. |
| [DPO](dpo.md) | Simplified preference optimization by replacing the reward-model-plus-PPO loop with a direct objective over chosen and rejected responses. Alignment became easier for more teams to run. |

## Wave 4 - Efficiency Unlocks Everything

| Paper | Why it mattered |
| --- | --- |
| [LoRA](lora.md) | Made fine-tuning large models cheap by training low-rank adapters while freezing the base model. This helped make open-source model adaptation practical. |
| [FlashAttention](flashattention.md) | Kept the attention math the same but changed the hardware schedule. By avoiding wasteful memory traffic, it made longer contexts and faster Transformer training much more practical. |
| [Mixtral of Experts](mixtral-of-experts.md) | Pushed sparse mixture-of-experts models into the mainstream: many parameters, but only a small subset active per token. It decoupled capacity from active inference compute. |

## Wave 5 - Multimodal and Generation

| Paper | Why it mattered |
| --- | --- |
| [CLIP](clip.md) | Used internet-scale image-text contrastive learning to create a shared embedding space for vision and language. It became a foundation for zero-shot vision, retrieval, and text-image systems. |
| [Latent Diffusion / Stable Diffusion](latent-diffusion-stable-diffusion.md) | Moved diffusion into compressed latent space, making high-quality image generation cheap enough to run widely. This turned image generation from lab demo into everyday tool. |

## Wave 6 - Retrieval and Agents

| Paper | Why it mattered |
| --- | --- |
| [RAG for Knowledge-Intensive NLP](rag-knowledge-intensive-nlp.md) | Combined retrieval with generation so models could use external memory without retraining. This became the default pattern for grounding LLMs in private or changing knowledge. |
| [ReAct - Reasoning and Acting](react-reasoning-acting.md) | Interleaved reasoning traces, tool actions, and observations. It gave language models a simple loop for checking external state and acting beyond a sealed prompt. |

## Wave 7 - The Reasoning Revolution

| Paper | Why it mattered |
| --- | --- |
| [Let's Verify Step by Step / PRM](lets-verify-step-by-step-prm.md) | Shifted attention from rewarding only final answers to supervising intermediate reasoning steps. It is a key prelude to process supervision and reasoning-model training. |
| [DeepSeek-R1](deepseek-r1.md) | Made reinforcement-learning-shaped reasoning feel frontier-relevant and more open. Its central lesson is that verifiable tasks can provide enough signal to elicit long, deliberate reasoning behavior. |

## Through-Lines

- **Attention becomes infrastructure.** The Transformer starts as a translation architecture, then becomes the common substrate for language, vision, retrieval-augmented systems, multimodal generation, and reasoning models.
- **Scale changes the interface.** GPT-3 and scaling laws made prompting and in-context learning feel like product primitives, while Chinchilla forced a more disciplined view of data and compute allocation.
- **Usefulness is trained, not automatic.** InstructGPT, chain-of-thought prompting, PRMs, DPO, and DeepSeek-R1 all orbit the same question: how do we turn broad capability into reliable behavior?
- **Efficiency changes who can participate.** LoRA, FlashAttention, latent diffusion, and MoE systems made once-expensive techniques cheaper, faster, and more widely deployable.
- **External context becomes part of the model loop.** RAG and ReAct move useful AI systems beyond static weights by adding retrieval, tools, observations, and action.

## Suggested Reading Order

1. Start with [Attention Is All You Need](attention-is-all-you-need.md), then [GPT-3](gpt3-few-shot-learners.md), then [InstructGPT / RLHF](instructgpt-rlhf.md). That gives the shortest path from architecture to useful assistants.
2. Read [Scaling Laws](scaling-laws-neural-lm.md) and [Chinchilla](chinchilla.md) together. The second revises the first in an important way.
3. Pair [Chain-of-Thought Prompting](chain-of-thought-prompting.md), [Let's Verify Step by Step / PRM](lets-verify-step-by-step-prm.md), and [DeepSeek-R1](deepseek-r1.md) as the reasoning arc.
4. Pair [CLIP](clip.md) with [Latent Diffusion](latent-diffusion-stable-diffusion.md) for the multimodal generation arc.
5. Pair [RAG](rag-knowledge-intensive-nlp.md) with [ReAct](react-reasoning-acting.md) for the external-memory and agent loop.
