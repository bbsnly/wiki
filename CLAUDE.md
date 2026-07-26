# Personal knowledge wiki

A personal knowledge base built on the LLM-wiki pattern (`llm-wiki.md` — read it before changing
this schema). The human curates sources and asks questions; Claude writes and maintains the
entire wiki layer. Multi-topic by design: anything worth remembering.

## Layers

- `raw/` — source documents the human drops in. **Immutable: read them, never edit, move, or
  delete anything inside.**
- `wiki/` — Claude-owned. All generated pages, plus `index.md` (catalog) and `log.md`
  (chronology); each documents its own format in its header. File new pages under `sources/`
  (one summary per raw source), `entities/` (people, orgs, tools, works, places), `concepts/`
  (ideas, topics, themes); overviews, syntheses, and comparisons live at the `wiki/` top level.
  kebab-case filenames, standard relative markdown links.
- `CLAUDE.md` — this schema. It co-evolves with the human as the workflow settles; change it
  only with their agreement.

## Conventions

- Cite origins on every page: link the raw source and/or its summary page claims came from.
- Never silently overwrite a claim that new information contradicts — record the contradiction
  on the page until the human resolves it.
- Cross-link related pages in both directions; a single source may touch 10–15 pages.
- Durable answers (comparisons, analyses, discovered connections) get filed back into the wiki
  as pages, indexed and logged, so explorations compound instead of vanishing into chat history.

## Operations

**Ingest** — one source at a time, interactive. Read the new file in `raw/` (text first; view any
referenced local images separately). Discuss key takeaways with the human before filing — they
guide what to emphasize. Then: write the summary page in `wiki/sources/`, update or create the
entity and concept pages the source touches, update `wiki/index.md`, append to `wiki/log.md`.

**Query** — read `wiki/index.md` first to locate relevant pages, drill into them (and raw sources
when needed), answer with citations to the pages used. Offer to file durable answers back into
the wiki.

**Lint** — on request: find contradictions between pages, claims superseded by newer sources,
orphan pages with no inbound links, concepts mentioned but lacking their own page, missing
cross-references, and data gaps a web search or new source could fill. Suggest questions to
investigate and sources to look for; log the pass.

## Scaling (adopt only when needed)

Index-first lookup works to roughly ~100 sources / hundreds of pages; beyond that, consider
[qmd](https://github.com/tobi/qmd) for local markdown search. Answers can also take other
formats on request: comparison tables, Marp slide decks, matplotlib charts.
