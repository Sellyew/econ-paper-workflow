# Econ Scholar Workflow

## Positioning

This repository is a Codex workflow overlay for empirical economics research, especially:

- empirical microeconomics
- policy evaluation
- `Stata + Python` research workflows
- paper drafting, revision, replication, and `R&R` response work

Default user-facing outputs may still be in Chinese unless the prompt asks for another language. Keep technical terms such as `DID`, `IV`, `RDD`, `event study`, `JEL`, `reghdfe`, and `ivreg2` in their standard form.

## Routing Rules

Route to the empirical economics workflow by default when the user mentions topics such as:

- `Stata`, `do-file`, `reghdfe`, `ivreg2`, `esttab`, `outreg2`
- `DID`, `event study`, `RDD`, `IV`, `matching`, `shift-share`, `synthetic control`
- regression tables, robustness, heterogeneity, mechanisms, placebo tests, balance tables
- identification strategy, institutional background, variable construction, appendix tables, replication packages
- referee reports, `R&R`, response letters, revision memos

Interpret broad words such as "results," "experiment," "paper," or "review comments" in an empirical economics sense unless the user explicitly gives another context.

## Preferred Skills

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

## Preferred Agents

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

## Results Interpretation Branch

When core empirical results arrive:

1. use `results-analysis` and `data-analyst` to recover the specification and sample
2. use `theory-auditor` to test theory fit and competing mechanisms
3. save interpretation memos under `results_memos/`

## Optional Story-Diagnostics Loop

Use `story-diagnostics` when current results do not yet support a credible economics story.

Possible outcomes:

- `STORY_READY`
- `CREDIBLE_NULL`
- `ITERATE_WITH_CURRENT_DATA`
- `NEW_DATA_REQUIRED`

Rules:

- maximum `3` rounds unless the user asks for more
- only propose theory-, design-, or measurement-based next steps
- stop if only opportunistic specification searches remain

## QA Thresholds

- `80` = commit-ready
- `90` = internal-share or submission-ready
- `95` = excellence

Paper hard gates:

- identification logic contains a clear error
- headline text does not match tables, figures, or appendices
- citations are distorted or unverifiable
- replication instructions are materially incomplete

Response hard gates:

- a key referee point is unanswered
- the letter promises a change that was not implemented
- the response and change map do not match
- the tone is evasive or materially misleading

## Default Output Files

- `literature-review.md`
- `identification-map.md`
- `data-source-plan.md`
- `analysis-plan.md`
- `regression-spec-matrix.md`
- `table-shells.md`
- `replication-checklist.md`
- `response-letter.md`
- `comment-to-change-map.md`
- `results_memos/theory_audits/*.md`
- `results_memos/story_diagnostics/*.md`
- `quality_reports/papers/*.md`
- `quality_reports/responses/*.md`
- `quality_reports/verifier/*.md`
