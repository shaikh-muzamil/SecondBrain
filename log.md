# Wiki Log

## [2026-07-31] setup | Initial LLM Wiki

Created the raw-source layer, maintained wiki layer, index, and operating schema.

## [2026-08-01] ingest | llm-wiki

Created [[LLM Wiki]] and linked it from [[Overview]]. The source establishes the vault's three-layer architecture and ingest, query, and lint workflows.

## [2026-08-01] ingest | Discipline video

Created [[Discipline by Design]] from the Erin Meryl YouTube video, recording the channel in the page frontmatter.

## [2026-08-01] ingest | hormozi-skills

Created [[Hormozi Skills]] from the alexsmedile GitHub repository.

## [2026-08-01] maintenance | Log consolidation

Merged the wiki log into this root-level log and removed the redundant wiki log. Removed the no-longer-needed Overview page; the root `index.md` is now the entry point for maintained knowledge.

## [2026-08-01] maintenance | Index consolidation

Merged the two indexes into the root-level `index.md`. It now catalogs every ingested source and the material concepts extracted from each source; future ingests must update both tables.

## [2026-08-01] ingest | Simplicity in Business

Created [[Simplicity in Business]] from the Varun Mayya YouTube video and added its source and concepts to `index.md`.

## [2026-08-01] ingest | Git and GitHub Tutorial

Created [[Git and GitHub Fundamentals]] from the CodeWithHarry YouTube course and added its source and concepts to `index.md`.

## [2026-08-01] ingest | Self-Improving AI Wiki

Created [[Self-Improving AI Wiki]] from the Bradley Bonanno YouTube video, linked it to [[LLM Wiki]], and added its source and concepts to `index.md`.

## [2026-08-01] setup | Journal and CRM

Added the `journal/` and `crm/` indexes and updated `AGENTS.md` with the workflows for journal conversations and person records.

## [2026-08-01] ingest | Raw collection reprocessing

Re-read and verified all six raw sources. Each has one maintained wiki page, one source row in the root index, and multiple concept rows; YouTube pages retain channel metadata. No duplicate pages or index rows were added.

## [2026-08-01] maintenance | Source archive reprocessing

Moved all six already-ingested source files from the root `raw/` inbox into `raw/processed/`. Updated the root `index.md` and all wiki source references to point at the archived source paths. Added or confirmed YouTube `channel` frontmatter in the original processed source files and the corresponding wiki pages.
