# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repository Is

A curated Awesome-list of papers, benchmarks, and datasets on **memory for robotics** — not generic LLM memory. All content lives in Markdown files; there is no build system, tests, or code to run.

## Repository Structure

- **`README.md`** — the primary list, organized by taxonomy sections
- **`docs/taxonomy.md`** — extended taxonomy with additional papers organized by timescale, representation, usage, and application domain
- **`docs/evaluation.md`** — detailed benchmark descriptions, metrics, and evaluation protocols
- **`docs/datasets.md`** — dataset index
- **`CONTRIBUTING.md`** — contribution guidelines and entry format

## Entry Format

All paper entries use this table row format:

```markdown
| Paper Title | Venue | Year | [[Paper]](url) [[Code]](url) [[Project]](url) |
```

Benchmark entries in `README.md` use a slightly different format:

```markdown
| Benchmark Name | Year | One-line description of what it tests | [[Paper]](url) [[Project]](url) [[Code]](url) |
```

Only include link types that actually exist for that paper. Order: `[[Paper]]` → `[[Project]]` → `[[Code]]`.

## Taxonomy (sections in README.md)

Memory is divided by **timescale**:
- **Contextual Memory** — within-episode working memory (keyframes, context windows, history)
- **Episodic Memory** — specific past experiences (memory banks, replay buffers, latent tokens)
- **Semantic Memory** — structured knowledge (scene graphs, neural-symbolic, CoT)
- **Long-term Memory** — cross-task, cross-session accumulation (continual learning, skill transfer)

And by **application domain**: VLAs, Mobile Manipulation, General Manipulation, Navigation, Locomotion, Spatial & Scene Memory, World Models, Lifelong Learning.

A paper often fits multiple sections — it is fine (and expected) to list it in more than one table if the contribution spans categories.

## Conventions

- **Within each section, newer papers go first** (descending year order). CONTRIBUTING.md says "newer papers should be added at the bottom," but the actual README lists 2026 entries before 2025 entries — follow the existing order (newest first).
- **Venue**: use the official short name (arXiv, CVPR, ICRA, NeurIPS, etc.). For blog/tech reports, use the org name (e.g., "Physical Intelligence", "Rhoda AI").
- **Year**: use publication year, not submission year.
- Before adding a paper, check all existing sections to avoid duplicate rows within the same section.
- A paper already in `docs/taxonomy.md` or `docs/evaluation.md` does not need to be duplicated there unless the main README entry is also being added.

## Known Quirks

- Line 96 of README.md contains a typo: `"threfour"` — leave it unless fixing it is the task.
- "Contextual" is consistently misspelled as "Contexual" throughout the repo (section headings, TOC anchors, taxonomy). Do not silently fix this misspelling unless it is the explicit task, as it would break anchor links.
- `docs/taxonomy.md` is richer than README.md in some categories (retrieval-based memory, active perception, embodied agents with LLM/VLM) and can be consulted when deciding where a paper fits.
