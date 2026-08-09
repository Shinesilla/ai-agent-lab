# AI Agent Lab

Write-ups from testing AI coding agents on real multi-step engineering tasks. Currently covers Claude Code; other tools (Cursor, Goose, and others) are being tested and will be added as write-ups are finished.

Each write-up describes a specific technique or tool tried in practice: the problem it was meant to solve, the approach taken, and what actually happened when it was used.

## Evaluations

- [`evaluations/claude-code/multi-agent-state-tracking.md`](evaluations/claude-code/multi-agent-state-tracking.md) — a lightweight state-tracking mechanism handed across three separate agent context windows
- [`evaluations/claude-code/adversarial-completion-audit.md`](evaluations/claude-code/adversarial-completion-audit.md) — a second agent independently re-checking another agent's self-reported "done" claims
- [`evaluations/claude-code/session-recovery-tool.md`](evaluations/claude-code/session-recovery-tool.md) — a deterministic script for resuming the right session after an unclean close
- [`evaluations/claude-code/deterministic-handoff-pipeline.md`](evaluations/claude-code/deterministic-handoff-pipeline.md) — a structured session-close pipeline with an automated pass/fail gate
- [`evaluations/claude-code/cross-machine-path-portability.md`](evaluations/claude-code/cross-machine-path-portability.md) — root-causing and fixing a hardcoded-path failure across machines

More write-ups get added as new tests are run.
