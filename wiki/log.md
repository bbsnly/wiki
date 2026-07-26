# Log

Append-only chronology of wiki operations. Every entry starts
`## [YYYY-MM-DD] <ingest|query|lint|setup> | <title>`; never rewrite past entries.
Recent activity: `grep "^## \[" wiki/log.md | tail -5`.

## [2026-07-26] setup | Wiki initialized

Scaffolded per the LLM-wiki pattern (llm-wiki.md): `raw/` for immutable sources; `wiki/` with
index.md, log.md, sources/, entities/, concepts/; CLAUDE.md as the schema. Git repo initialized.
Decisions: multi-topic personal wiki; plain markdown, no Obsidian; ingest one source at a time,
interactively.
