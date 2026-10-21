# PRD — south-korea

> Product requirements for `ai-world-view/south-korea`, self-growing knowledge base — the country south korea.
> Sources: [README.md](README.md), [CLAUDE.md](CLAUDE.md), `_config.yml`, and the hub
> [`ai-world-view/ai-world-view.github.io`](https://github.com/ai-world-view/ai-world-view.github.io). Unknowns are marked **TBD**.

## 1. Overview / problem

`south-korea` is a **self-growing knowledge base** about the country South Korea, one member repo of the
[`ai-world-view`](https://github.com/ai-world-view) lineage. It provides a readable, encyclopedic
reference that grows over time without a human writing each article.

This repo holds only its own content, a GitHub Pages `_config.yml` (a `remote_theme`
consumer of `bamr87/zer0-mistakes`), the `.claude/` adapter toolkit and `telemetry/`.
Growth is orchestrated **centrally by the hub** (`ai-world-view/ai-world-view.github.io`): on each tick the hub stages
the agent framework and this repo's concept seed, runs a Haiku → Sonnet → Opus
escalation to research and write content, and publishes only new content and
telemetry back here (see CLAUDE.md).

## 2. Target users

- Readers who want a neutral, sourced overview of the country South Korea (published at https://ai-world-view.github.io/south-korea).
- Maintainers of the `ai-world-view` lineage who operate the hub's growth loop.
- Specific audience segments / personas: **TBD**.

## 3. Goals and non-goals

**Goals**
- Cover the country South Korea across the seed's taxonomy categories with factual, neutral,
  encyclopedic, third-person articles.
- Verify every fact against at least two sources (CLAUDE.md convention).
- Publish as a static GitHub Pages site with no theme code in this repo.

**Non-goals**
- Holding the seed, growth policy, or agent framework (these live in the hub).
- Theme files (`_layouts`, `_includes`, `_sass`) — the theme is remote.
- Opinion, commentary, or unsourced content.

## 4. Core features (current)

- Static site: Jekyll with `remote_theme: bamr87/zer0-mistakes@v1.26.0`, `baseurl: /south-korea`.
- Content by taxonomy category (Markdown files with `title` / `date` / `category` front matter):

| Category directory | Markdown files |
|---|---|
| `culture-society/` | 29 |
| `economy/` | 21 |
| `geography/` | 20 |
| `government-politics/` | 10 |
| `history/` | 16 |
| `people/` | 18 |

- Index/navigation documents at root: `README.md`, `TIMELINE.md`, `INDEX.md`, `CLAUDE.md`, `LICENSE`.
- `telemetry/` growth ledger written by the hub's growth ticks.
- `.claude/` thin adapters (skills/commands) pointing at hub-staged procedures.

## 5. Requirements

**Functional**
- FR1: Each topic is a single Markdown file in its category directory with required front matter (`title`, `date`, `category`).
- FR2: The site builds on GitHub Pages using the remote theme and `_config.yml` alone.
- FR3: Growth ticks add content and telemetry only; they do not change the seed or framework here.
- FR4: Root index pages (README/TIMELINE/INDEX) link to published articles.

**Non-functional**
- NFR1: Accuracy — every fact verified against ≥2 sources; neutral tone.
- NFR2: Minimal footprint — no theme code, no build tooling beyond Pages.
- NFR3: Traceability — every growth tick leaves a telemetry record.
- Performance, accessibility, and availability targets: **TBD**.

## 6. Success metrics (proposed — not defined in sources)

- Article count and coverage per category (baseline in the table above).
- Share of articles with ≥2 cited sources.
- Pages build success rate.
- Reader traffic: **TBD** (no analytics source found in the repo).

## 7. Roadmap / open questions

- No repo-local roadmap found.
- Target size / completion criteria for this country: **TBD** (governed by the hub's growth policy).
- Roadmap is owned by the hub; see `ai-world-view/ai-world-view.github.io`.

## 8. Links

- [README.md](README.md) · [CLAUDE.md](CLAUDE.md) · [TIMELINE.md](TIMELINE.md) · [INDEX.md](INDEX.md)
- Live site: https://ai-world-view.github.io/south-korea/
- Hub: https://github.com/ai-world-view/ai-world-view.github.io
- CHANGELOG: none in this repo (last commit 2026-10-03).
