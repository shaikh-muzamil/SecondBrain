# LLM Wiki

An LLM wiki is a persistent knowledge base that an agent incrementally maintains from a collection of immutable sources. Unlike retrieval-only workflows, knowledge is synthesized once into linked pages and improved as new sources arrive.

## Core model

- **Raw sources** are the immutable source of truth.
- **The wiki** is the maintained layer of summaries, concepts, entities, and syntheses.
- **The schema** directs the agent's conventions and workflows.

The wiki is intended to compound: new sources update existing pages, make connections explicit, and surface conflicts or gaps instead of requiring the agent to reconstruct the same synthesis for every question.

## Operating loop

1. **Ingest** a source: extract its useful knowledge, update relevant wiki pages, then update the index and log.
2. **Query** the wiki: use the index to locate relevant pages and synthesize an answer with source support. Preserve durable answers as new pages when useful.
3. **Lint** the wiki periodically: find broken or missing links, orphan pages, contradictions, stale claims, and knowledge gaps.

## Design choices for this vault

This vault uses the source's minimal architecture: `raw/` is read-only, `wiki/` is agent-maintained, and `AGENTS.md` is the schema. Search tooling, plugins, and other extensions are deferred until the wiki needs them.

[[Self-Improving AI Wiki]] describes an optional extension: scheduled agents can fetch new material from human-approved sources before the usual ingest process.

## Sources

- [[raw/processed/llm-wiki|llm-wiki]] — Karpathy's LLM Wiki pattern.
