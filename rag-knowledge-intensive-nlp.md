---
tags: [retrieval, external-memory, generation, knowledge-intensive-nlp, grounding]
date: 2026-02-04
time: 20:18
---

# RAG for knowledge-intensive NLP

## gist

Combine parametric generation with non-parametric [[retrieval]]: fetch relevant documents, then generate conditioned on them.

## why

LMs memorize a lot but not enough, and their knowledge goes stale. [[rag-knowledge-intensive-nlp]] says: let the model look things up.

This is a different path from just scaling [[gpt3-few-shot-learners]]. External memory can be updated without retraining.

## mechanism

Retriever finds passages from a corpus, generator consumes query + passages. The paper variants differ in whether retrieved docs are fixed per sequence or per token.

Dense Passage Retrieval is the retrieval side I need to revisit. The generator is BART in the original paper, not a modern chat model, but the pattern is everywhere now.

## reactions

RAG is conceptually simple and operationally annoying. Chunking, embeddings, stale indexes, eval, citations, context packing... all the boring stuff becomes the product.

Still, the central distinction is useful:

- parametric memory = inside weights
- non-parametric memory = retrieve from corpus

## links

[[retrieval]], [[attention]], [[react-reasoning-acting]], [[gpt3-few-shot-learners]].

TODO: make a note on when RAG fails: bad recall, distractor docs, synthesis errors, and false confidence.
