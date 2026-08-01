# Second Brain Wiki Schema

## Purpose

Maintain this vault as a persistent, compounding wiki. The human curates sources and directs the work; the agent maintains the wiki.

## Layers

- `raw/` is the inbox for unprocessed source files. After a successful ingest, move the original source file to `raw/processed/`.
- Treat source content as immutable. The only permitted change to an original YouTube source is adding or correcting its `channel` frontmatter field.
- `wiki/`, `journal/`, and `crm/` contain agent-maintained markdown. These are the only layers to create and revise.
- This file defines the rules for operating the wiki.

## Wiki conventions

- Use short, descriptive page names in title case.
- Link related pages with Obsidian wikilinks: `[[Page Name]]`.
- Keep claims grounded in one or more raw sources. Name or link the supporting source in a `## Sources` section when applicable.
- Create a page only for a distinct, reusable topic, concept, entity, or synthesis. Otherwise update the existing relevant page.
- Maintain the single root-level `index.md` whenever a source is ingested or a wiki page is created, renamed, or materially changed. Do not create an index inside `wiki/`.
- Append a dated entry to `log.md` after each ingest, query worth preserving, or lint pass.

## Index structure

`index.md` is the catalog for the entire vault. It contains two tables:

1. **Sources** — exactly one row for each ingested raw file, linking the raw source and its maintained wiki page.
2. **Concepts** — one row for each material concept extracted from an ingested source. A source can and usually should produce multiple concept rows.

On every ingest, add the source row and all material concepts from that source. Update existing concept rows when later sources strengthen, contradict, or materially revise them.
After a source is moved, the source row must link to its `raw/processed/` archive path.

## Source metadata

- Preserve original source content. Do not rewrite source files except to add or correct the YouTube `channel` frontmatter field.
- For a YouTube video clipped into `raw/`, identify the channel from the YouTube page or clip metadata and record it as `channel: "Channel Name"` in both the original source's frontmatter and the frontmatter of the wiki page created for that source.

## Journal

When a user begins a chat with `journal`, treat that chat as a journal conversation.

- Create a new file in `journal/` named `YYYY-MM-DD - Short Title.md`, using a short title inferred from the journal entry's subject.
- Record the complete visible conversation: the user's journal messages and the assistant's responses. Append each subsequent turn to that same file while the journal conversation continues.
- Keep the conversation in chronological order with clear `## User` and `## Assistant` labels. Do not summarize away the original conversation text.
- Maintain `journal/index.md` as a table with `Date`, `Title`, `Summary`, and `Entry` columns. Add one row for every journal file.
- Append a dated journal entry to the root `log.md`, including the journal title and a short summary.

### Journal responses

When responding in a journal conversation:

1. Read the root `index.md` and relevant wiki pages first.
2. Read relevant past journal entries through `journal/index.md` and relevant CRM records through `crm/index.md` when they can help.
3. Ground claims about the user's stored knowledge in those files; distinguish those claims from general LLM knowledge.
4. Offer practical advice, insight, guidance, tactics, and ideas using the available context and general reasoning. Do not invent facts about the user, their relationships, or their past entries.

## CRM

When the user says they are providing information for the CRM, create or update a person record in `crm/`.

- Each CRM record is one markdown file named after the person: `crm/Person Name.md`.
- Capture only the details the user provides, such as contact details, how or where they met, and known facts, preferences, context, or relationship notes.
- Update an existing person record rather than creating a duplicate when the person is already present.
- Maintain `crm/index.md` as an alphabetically sorted table with `Person`, `Short bio`, and `Record` columns.
- The short bio must describe only the information currently stored about that person.
- When answering CRM-related questions, read `crm/index.md` first and then the relevant person records. State uncertainty when a requested detail is not recorded.

## Operations

### Ingest

When asked to ingest a source:

1. Read the new file in `raw/` or from the provided URL/path, preserving its original content.
2. If it is a YouTube source, retrieve the channel name and add or correct it in the original source page's frontmatter and the wiki source page's frontmatter.
3. Cross-link any generated or updated wiki pages to the original source page.
4. Discuss key takeaways if the user has not already set the focus.
5. Create or update the appropriate pages in `wiki/`, including cross-links and source references.
6. Update the root `index.md` with one source row and the source's material concept rows, then append to `log.md`.
7. Move the source file from the root `raw/` directory to `raw/processed/` and ensure all source links point to the archived location.

### Query

When answering a question about the vault:

1. Read the root `index.md` first, then the relevant pages.
2. Synthesize from the wiki and identify supporting source pages/files.
3. If the answer is a durable insight, comparison, or analysis, offer to file it as a wiki page; file it when asked.

### Lint

When asked to lint the wiki, check for broken or missing links, orphan pages, duplicate pages, unsupported or contradictory claims, stale pages, and important concepts that should have their own pages. Record the result in `log.md`.
