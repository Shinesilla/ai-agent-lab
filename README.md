# AI Agent Lab

Write-ups from testing AI coding agents and models on real multi-step engineering tasks. Covers Claude Code hands-on, plus model-selection work across other providers. Qwen model evaluation completed; Qwen Code CLI evaluation planned.

Each write-up describes a specific technique or tool tried in practice: the problem it was meant to solve, the approach taken, and what actually happened when it was used.

## Claude Code

- [`evaluations/claude-code/multi-agent-state-tracking.md`](evaluations/claude-code/multi-agent-state-tracking.md) — a lightweight state-tracking mechanism handed across three separate agent context windows
- [`evaluations/claude-code/adversarial-completion-audit.md`](evaluations/claude-code/adversarial-completion-audit.md) — a second agent independently re-checking another agent's self-reported "done" claims
- [`evaluations/claude-code/session-recovery-tool.md`](evaluations/claude-code/session-recovery-tool.md) — a deterministic script for resuming the right session after an unclean close
- [`evaluations/claude-code/deterministic-handoff-pipeline.md`](evaluations/claude-code/deterministic-handoff-pipeline.md) — a structured session-close pipeline with an automated pass/fail gate
- [`evaluations/claude-code/cross-machine-path-portability.md`](evaluations/claude-code/cross-machine-path-portability.md) — root-causing and fixing a hardcoded-path failure across machines

## Model Selection

- [`evaluations/model-selection/backup-extraction-models.md`](evaluations/model-selection/backup-extraction-models.md) — shortlisting Gemini, Kimi, DeepSeek, and Qwen as free-tier backup models, then what actually broke when the pick was run for real

## Cross-Model

- [`evaluations/cross-model/prompt-portability-constraint-drift.md`](evaluations/cross-model/prompt-portability-constraint-drift.md) — testing whether a strict-format prompt's constraints hold up unmodified on a different model family

## Qwen Code

- [`evaluations/qwen-code/planned-evaluation.md`](evaluations/qwen-code/planned-evaluation.md) — evaluation plan for Qwen Code as a non-Anthropic execution agent (planned, not yet run)

More write-ups get added as new tests are run.
