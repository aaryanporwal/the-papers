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

Retriever finds passages from a corpus, generator consumes query + passages. The paper variants differ in whether retrieved docs are fixed pe