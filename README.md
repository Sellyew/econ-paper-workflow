# Econ Scholar Workflow for Codex

Language: English | [中文](README.zh-CN.md)

An empirical economics workflow package for Codex, designed for:

- empirical microeconomics
- policy evaluation
- `Stata + Python` research workflows
- paper drafting, result interpretation, submission QA, and `R&R` response work

This repository is the public package. It includes only the shareable economics workflow layer:

- routing rules in `AGENTS.md`
- public agent prompts in `agents/`
- public skills in `skills/`
- configuration examples in `config.example.toml`
- QA templates in `quality_reports/`
- memo scaffolding in `results_memos/`

## What This Workflow Assumes

By default, Codex should interpret requests here in an empirical economics sense:

- "results" means regression tables, figures, and interpretation memos
- "experiment" means an empirical design or estimation strategy
- "paper" means an empirical economics paper structure
- "review response" means a journal revision letter

Default stack:

- literature: `Google Scholar`, `RePEc`, `IDEAS`, `NBER`, `AEA` journals, field journals
- analysis: `Stata` first, `Python` for support tasks
- outputs: `literature-review.md`, `identification-map.md`, `analysis-plan.md`, `regression-spec-matrix.md`, `response-letter.md`

## Workflow Stages

### 1. Research Ideation

- `research-ideation`
- `literature-reviewer`

Typical outputs:

- `literature-review.md`
- `identification-map.md`
- `data-source-plan.md`

### 2. Data Audit And Analysis Planning

- `results-analysis`
- `data-analyst`

Typical outputs:

- `analysis-plan.md`
- `regression-spec-matrix.md`
- `table-shells.md`
- `replication-checklist.md`

### 3. Theory-Facing Interpretation

- `theory-auditor`

Typical outputs:

- `results_memos/theory_audits/*.md`

### 4. Story Diagnostics

- `story-diagnostics`

Typical outputs:

- `results_memos/story_diagnostics/*.md`

Possible verdicts:

- `STORY_READY`
- `CREDIBLE_NULL`
- `ITERATE_WITH_CURRENT_DATA`
- `NEW_DATA_REQUIRED`

### 5. Paper Drafting

- `paper-writing`
- `paper-miner`

### 6. QA And Revision

- `paper-self-review`
- `qa-paper`
- `review-response`
- `qa-response`
- `rebuttal-writer`
- `artifact-verifier`

### 7. Post-Acceptance Finalization

- `post-acceptance`

## Main Agents And Skills

Agents:

- `literature-reviewer`
- `data-analyst`
- `theory-auditor`
- `paper-miner`
- `paper-critic`
- `paper-fixer`
- `rebuttal-writer`
- `response-critic`
- `response-fixer`
- `artifact-verifier`

Skills:

- `research-ideation`
- `results-analysis`
- `story-diagnostics`
- `paper-writing`
- `paper-self-review`
- `review-response`
- `qa-paper`
- `qa-response`
- `citation-verification`
- `post-acceptance`

## Setup

1. Read `AGENTS.md` and this README.
2. Merge the relevant sections from `config.example.toml` into your real `~/.codex/config.toml`.
3. Sync `AGENTS.md`, `agents/`, and `skills/` into your Codex environment.
4. Configure Zotero MCP if you want literature import, collections, and PDF attachment.
5. Open your research project from its root so Codex can load the project-level `AGENTS.md`.

Notes:

- `config.example.toml` contains placeholders; do not copy credentials verbatim.
- `MCP_SETUP.md` and `MCP_SETUP.zh-CN.md` document the Zotero MCP setup path.
- This package assumes you already have Codex CLI, Git, and your preferred local research tooling.

## Practical Prompts

```text
Use the empirical economics workflow to map the literature, identification strategies, and feasible data sources for [topic].
```

```text
Reconstruct the sample construction and specification ladder from my do-files, logs, and tables, then produce a regression-spec matrix.
```

```text
Use results-analysis and theory-auditor on these baseline results. I want a memo on theory fit, competing mechanisms, and the next defensible empirical steps.
```

```text
Use story-diagnostics. The current results do not yet support a credible economics story. Tell me what to run next and when to stop.
```

```text
Run qa-paper on this draft. I want hard gates, a score, and a submission-readiness verdict.
```

## Repository Layout

- `AGENTS.md`: routing rules, economics defaults, and quality standards
- `agents/`: public agent prompts
- `skills/`: public workflow skills and references
- `config.example.toml`: Codex configuration example
- `MCP_SETUP.md`: Zotero MCP setup notes
- `quality_reports/`: QA templates and report directories
- `results_memos/`: memo scaffolding for interpretation and diagnostics

## Included And Excluded Content

Included:

- shareable economics workflow files
- public-safe templates, references, and memo scaffolding
- configuration examples with placeholders

Excluded:

- project-specific research folders
- private datasets and manuscript files
- secrets, personal paths, and live credentials
- historical non-default workflow material
