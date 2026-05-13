# The Papers

These are my personal notes, written for myself, on breakthrough AI papers that changed the direction of the field. The organizing principle is not chronology alone. Each paper here shifted what researchers tried next, what companies invested in, or what became practical to build.

They are informal: each file captures the core idea, the mechanism worth remembering, why the paper mattered, and what questions are still unresolved.

## Wave 1 - The Architecture That Started It All

| Paper | Why it mattered |
| --- | --- |
| [Attention Is All You Need](attention-is-all-you-need.md) | Introduced the Transformer, the design behind most modern AI systems. It made models faster to train and much better at handling language, images, and other kinds of data. |
| [ViT - An Image is Worth 16x16 Words](vit-image-worth-16x16-words.md) | Showed that Transformers could work for images too, not just text. This helped move computer vision away from older image-specific designs. |

## Wave 2 - Scale Is All You Need

| Paper | Why it mattered |
| --- | --- |
| [GPT-3 - Language Models are Few-Shot Learners](gpt3-few-shot-learners.md) | Made it clear that very large language models could follow examples in a prompt. People could start using models for new tasks without retraining them. |
| [Scaling Laws for Neural Language Models](scaling-laws-neural-lm.md) | Gave researchers a way to predict how much better models might get as they used more data and compute. This made big training runs less of a blind gamble. |
| [Chinchilla](chinchilla.md) | Showed that many large models were trained on too little data. It pushed the field toward balancing model size with enough training text. |

## Wave 3 - Making Models Actually Useful

| Paper | Why it mattered |
| --- | --- |
| [InstructGPT / RLHF](instructgpt-rlhf.md) | Helped turn raw text predictors into helpful assistants. It showed that training models on human preferences can make them much easier to use. |
| [Chain-of-Thought Prompting](chain-of-thought-prompting.md) | Showed that models often do better when asked to work through a problem step by step. This made prompting a useful tool for harder reasoning tasks. |
| [DPO](dpo.md) | Made it simpler to train models to prefer better answers over worse ones. This lowered the barrier for teams trying to improve model behavior. |

## Wave 4 - Efficiency Unlocks Everything

| Paper | Why it mattered |
| --- | --- |
| [LoRA](lora.md) | Made it much cheaper to customize large models. Instead of retraining everything, teams could add small updates for their own use cases. |
| [FlashAttention](flashattention.md) | Made Transformers faster and more memory-efficient without changing what they compute. This helped models handle longer context windows and train more efficiently. |
| [Mixtral of Experts](mixtral-of-experts.md) | Showed a practical way to make models bigger without making every answer equally expensive. The model uses only the parts it needs for each token. |

## Wave 5 - Multimodal and Generation

| Paper | Why it mattered |
| --- | --- |
| [CLIP](clip.md) | Connected images and text in a way that models could understand together. This became important for image search, image understanding, and text-to-image systems. |
| [Latent Diffusion / Stable Diffusion](latent-diffusion-stable-diffusion.md) | Made high-quality image generation much cheaper to run. This helped image generation move from research demos into everyday creative tools. |

## Wave 6 - Retrieval and Agents

| Paper | Why it mattered |
| --- | --- |
| [RAG for Knowledge-Intensive NLP](rag-knowledge-intensive-nlp.md) | Let models look up outside information before answering. This became a common way to make AI systems use private, current, or specialized knowledge. |
| [ReAct - Reasoning and Acting](react-reasoning-acting.md) | Gave models a simple pattern for thinking, using tools, and then updating their answer. This helped lead toward more useful agent-style systems. |

## Wave 7 - The Reasoning Revolution

| Paper | Why it mattered |
| --- | --- |
| [Let's Verify Step by Step / PRM](lets-verify-step-by-step-prm.md) | Showed that checking the steps of an answer can matter as much as checking the final result. This became important for training models to reason more reliably. |
| [DeepSeek-R1](deepseek-r1.md) | Showed that strong reasoning behavior could be trained more openly and at lower cost than many expected. It highlighted the value of tasks where answers can be checked clearly. |

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
