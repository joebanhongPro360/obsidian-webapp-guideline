# AGENTS.md

This file defines how AI agents should initialize and maintain this Obsidian LLM wiki.

The human-facing introduction is in `README.md`. The source design document is `LLM-wiki.md`. Always read `LLM-wiki.md` before making major structural decisions.

## Core Principle

This vault is not a one-time collection of static notes. It is a persistent, AI-maintained wiki.

The agent's job is to transform raw sources and user questions into a maintained markdown knowledge base:

- Preserve raw sources as the source of truth.
- Build and update wiki pages as synthesized knowledge.
- Maintain links, indexes, logs, and page consistency over time.
- Treat useful answers as knowledge that can be filed back into the wiki.
- Update this `AGENTS.md` when the operating rules evolve.

## Vault Configuration

- Purpose and domain: web-app guideline.
- Scope: development and maintenance practices, version control, deployment workflows, project terminology, and durable operational guidelines for web applications.
- Preferred wiki language: Traditional Chinese (`zh-TW`), while preserving source titles, code terms, product names, and proper nouns when appropriate.
- Expected source types: development notes, maintenance notes, version-control documentation, deployment process notes, project terminology, web clips, articles, PDFs, meeting notes, and personal notes.
- Ingest review mode: for every ingest, first produce a source summary and proposed wiki updates for user confirmation. Only write or update wiki pages after the user confirms.
- Naming and folders: use the recommended vault structure unless the user explicitly changes it.

## Required Startup Behavior

When asked to initialize or substantially reorganize this vault:

1. Read `LLM-wiki.md`.
2. Read this `AGENTS.md`.
3. Inspect the existing file tree before editing.
4. Ask the user for missing domain context before choosing a final structure.
5. Keep changes scoped to the wiki system unless the user asks for broader edits.

Ask for these details when they are not already known:

- Wiki purpose and domain.
- Expected source types, such as articles, PDFs, books, web clips, meeting notes, or personal notes.
- Preferred language for wiki pages.
- Desired level of user review during ingest.
- Any naming or folder preferences.

## Recommended Vault Structure

Use this structure unless the user chooses a different one:

```text
raw/
  sources/
  assets/
wiki/
  index.md
  log.md
  topics/
  entities/
  sources/
  syntheses/
templates/
README.md
LLM-wiki.md
AGENTS.md
```

Directory roles:

- `raw/sources/`: immutable or minimally edited source files.
- `raw/assets/`: downloaded images, attachments, and media referenced by sources.
- `wiki/index.md`: content-oriented catalog of wiki pages.
- `wiki/log.md`: chronological record of ingests, queries, lint passes, and structural changes.
- `wiki/topics/`: concept and topic pages.
- `wiki/entities/`: people, organizations, products, places, projects, or other named entities.
- `wiki/sources/`: AI-written source summaries.
- `wiki/syntheses/`: cross-source analysis, comparisons, briefs, and durable answers.
- `templates/`: page templates used by the agent.

If the vault is small, fewer folders are acceptable. Prefer a simple structure that the user can understand.

## Markdown and Obsidian Conventions

- Use standard markdown.
- Use Obsidian wiki links for internal links, such as `[[Page Name]]`.
- Prefer descriptive page names over opaque IDs.
- Keep page names stable after creation unless there is a clear reason to rename.
- Use YAML frontmatter when useful for indexing, but do not overcomplicate small wikis.
- Avoid duplicating entire source texts inside wiki pages.
- Cite or reference source pages when making claims derived from sources.
- Write in the user's preferred language unless source titles or proper nouns require otherwise.

## Source Handling

Raw sources are the source of truth.

Agents may:

- Read raw sources.
- Summarize raw sources into `wiki/sources/`.
- Extract concepts, entities, claims, dates, contradictions, and open questions.
- Link raw-source summaries to topic, entity, and synthesis pages.

Agents should not:

- Rewrite raw sources casually.
- Delete sources unless the user explicitly asks.
- Treat uncited synthesis as more authoritative than source material.

## Ingest Workflow

When ingesting a new source:

1. Identify the source path, title, author or origin if available, date if available, and source type.
2. Read the source carefully.
3. Create or update a source summary page under `wiki/sources/`.
4. Extract important topics and entities.
5. Create or update relevant pages under `wiki/topics/` and `wiki/entities/`.
6. Add internal links between source summaries, topic pages, entity pages, and syntheses.
7. Update `wiki/index.md`.
8. Append an entry to `wiki/log.md`.
9. Tell the user what changed and flag uncertainties.

For each ingest, prefer focused updates over broad rewrites. A source may touch many pages, but each edit should have a clear reason.

## Query Workflow

When answering a user question against the wiki:

1. Read `wiki/index.md` first if it exists.
2. Search the wiki for relevant pages.
3. Read the most relevant pages before answering.
4. Answer with citations or clear references to wiki pages and source summaries.
5. If the answer is durable and useful, offer or proceed to file it under `wiki/syntheses/`, depending on the user's instruction.
6. If filed back into the wiki, update `wiki/index.md` and append to `wiki/log.md`.

Do not rely only on memory when the answer should come from the maintained wiki.

## Lint Workflow

When asked to lint or health-check the wiki, inspect for:

- Orphan pages with no inbound or outbound links.
- Missing entries in `wiki/index.md`.
- Stale claims contradicted by newer sources.
- Duplicate pages covering the same concept.
- Important mentioned topics or entities without their own pages.
- Broken or ambiguous Obsidian links.
- Source summaries that are not connected to topic or entity pages.
- Missing log entries for substantial changes.

After linting, provide a concise report and make low-risk fixes directly. Ask before performing large reorganizations.

## Index Rules

`wiki/index.md` should be content-oriented.

Maintain sections that match the actual wiki, for example:

- Entry points
- Source summaries
- Topics
- Entities
- Syntheses
- Open questions

Each listed page should include:

- A wiki link.
- A one-line description.
- Optional metadata such as date, source count, status, or tags.

Update the index whenever pages are created, renamed, or substantially changed.

## Log Rules

`wiki/log.md` should be chronological and append-only.

Use entries like:

```markdown
## [2026-05-25] ingest | Source Title

- Added: [[Source Title Summary]]
- Updated: [[Topic Page]], [[Entity Page]]
- Notes: Short explanation of important changes or uncertainties.
```

Log these events:

- Source ingests.
- Durable query answers filed into the wiki.
- Lint passes.
- Structural changes.
- Major changes to `AGENTS.md`.

## Page Templates

Create templates when helpful. Suggested templates:

- `templates/source-summary.md`
- `templates/topic.md`
- `templates/entity.md`
- `templates/synthesis.md`

Keep templates lightweight. They should guide consistency without making every page feel bureaucratic.

## Evolving This File

This `AGENTS.md` is a living operating manual.

Update it when:

- The user changes the wiki's purpose.
- The folder structure changes.
- Page templates or naming rules change.
- The ingest, query, or lint workflow improves.
- Repeated agent mistakes reveal a missing rule.

When updating this file, preserve the distinction between:

- `LLM-wiki.md`: stable source idea.
- `README.md`: human-facing onboarding.
- `AGENTS.md`: AI-facing operating rules.
