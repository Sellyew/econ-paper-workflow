# Econ Scholar Workflow for Codex

语言：中文 | [English](README.md)

这是一个面向实证经济学研究的 Codex 工作流公开包，主要服务于：

- 实证微观经济学
- 政策评估
- `Stata + Python` 研究流程
- 论文写作、结果解释、投稿前 QA、`R&R` 回复

这个仓库是公开发布包，只包含可共享的经济学工作流层：

- `AGENTS.md` 中的路由规则
- `agents/` 中的公开 agent 提示词
- `skills/` 中的公开工作流说明
- `config.example.toml` 中的配置示例
- `quality_reports/` 中的 QA 模板
- `results_memos/` 中的 memo 结构文件

## 这套工作流默认如何理解任务

默认情况下，Codex 会按实证经济学语境理解这里的请求：

- “结果”指回归表、图和解释 memo
- “实验”指实证设计或识别策略
- “论文”指经济学论文结构
- “审稿回复”指期刊 `R&R` 回复

默认栈：

- 文献：`Google Scholar`、`RePEc`、`IDEAS`、`NBER`、`AEA` 期刊与领域期刊
- 分析：以 `Stata` 为主，`Python` 负责辅助任务
- 产物：`literature-review.md`、`identification-map.md`、`analysis-plan.md`、`regression-spec-matrix.md`、`response-letter.md`

## 工作流阶段

### 1. 研究构思

- `research-ideation`
- `literature-reviewer`

常见输出：

- `literature-review.md`
- `identification-map.md`
- `data-source-plan.md`

### 2. 数据审计与分析规划

- `results-analysis`
- `data-analyst`

常见输出：

- `analysis-plan.md`
- `regression-spec-matrix.md`
- `table-shells.md`
- `replication-checklist.md`

### 3. 理论导向解释

- `theory-auditor`

常见输出：

- `results_memos/theory_audits/*.md`

### 4. Story Diagnostics

- `story-diagnostics`

常见输出：

- `results_memos/story_diagnostics/*.md`

可能结论：

- `STORY_READY`
- `CREDIBLE_NULL`
- `ITERATE_WITH_CURRENT_DATA`
- `NEW_DATA_REQUIRED`

### 5. 论文写作

- `paper-writing`
- `paper-miner`

### 6. QA 与回复

- `paper-self-review`
- `qa-paper`
- `review-response`
- `qa-response`
- `rebuttal-writer`
- `artifact-verifier`

### 7. 录用后整理

- `post-acceptance`

## 主要 Agents 与 Skills

Agents：

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

Skills：

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

## 安装与配置

1. 先阅读 `AGENTS.md` 和本 README。
2. 将 `config.example.toml` 中相关片段合并到真实的 `~/.codex/config.toml`。
3. 将 `AGENTS.md`、`agents/` 和 `skills/` 同步到你的 Codex 环境。
4. 如果需要文献导入、collection 管理和 PDF 附件能力，再配置 Zotero MCP。
5. 在你的研究项目根目录启动 Codex，让它读取项目级 `AGENTS.md`。

注意：

- `config.example.toml` 里只有占位符，不要原样复制真实凭据。
- `MCP_SETUP.md` 与 `MCP_SETUP.zh-CN.md` 说明了 Zotero MCP 的配置路径。
- 这套公开包默认你已经安装好 Codex CLI、Git，以及本地研究所需工具。

## 实用提示词

```text
请使用经济学实证工作流，为 [topic] 做文献地图、识别策略梳理和可行数据源评估。
```

```text
请根据我的 do-file、log 和回归表，还原样本构造与 specification ladder，并生成 regression-spec matrix。
```

```text
请用 results-analysis 和 theory-auditor 分析这些基准结果。我需要一份关于 theory fit、竞争机制和下一步可辩护实证动作的 memo。
```

```text
请使用 story-diagnostics。当前结果还不支持一个可信的经济学故事，请告诉我下一步该跑什么，以及什么时候该停。
```

```text
请对这份 draft 运行 qa-paper。我需要 hard gates、分数和明确的投稿准备度结论。
```

## 仓库结构

- `AGENTS.md`：路由规则、经济学默认设定与质量标准
- `agents/`：公开 agent 提示词
- `skills/`：公开工作流 skills 与参考资料
- `config.example.toml`：Codex 配置示例
- `MCP_SETUP.md`：Zotero MCP 配置说明
- `quality_reports/`：QA 模板与报告目录
- `results_memos/`：解释与诊断 memo 的结构文件
