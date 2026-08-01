---
source_type: youtube
channel: "Bradley Bonanno"
source_url: "https://www.youtube.com/watch?v=nilNHl4uZcU"
---
# Self-Improving AI Wiki

This source extends the [[LLM Wiki]] pattern with automated collection. Its proposed solution is a *context farmer*: an agent that retrieves new material from sources the human has already chosen, then feeds it into the normal ingest process.

## Core model

- **Curation remains human** — selecting trustworthy channels, workspaces, or other sources is a judgment call.
- **Fetching can be automated** — once a source is approved, scheduled agents can retrieve new videos, transcripts, messages, or research.
- **Ingestion compounds** — new material updates existing pages and links instead of starting the wiki over.
- **MCP connectors widen the source layer** — services such as YouTube, Slack, meeting transcripts, and research feeds can become sources.
- **Cloud scheduling supports continuity** — a shared Git repository and scheduled agents can keep the source flow active when a local computer is offline.

## Implication for this vault

The current vault stays deliberately manual. Automated collection is a later option if the value of continuously updated sources outweighs the added setup and review burden.

## Sources

- [[raw/processed/Build Your Own Self Improving AI Wiki in 11 Minutes (Free Skill)|Build Your Own Self Improving AI Wiki in 11 Minutes]] — YouTube video by Bradley Bonanno.
