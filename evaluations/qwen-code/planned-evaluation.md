# Qwen Code CLI Evaluation Plan

**Status:** Planned — not yet run. This page will be replaced with an actual evaluation write-up after the first real test.

**Objective:** Determine whether Qwen Code (Alibaba's agentic coding CLI) can serve as a viable non-Anthropic execution partner inside a planner/auditor multi-agent workflow — the same coordination role Claude Code sub-agents currently fill in the write-ups under `evaluations/claude-code/`.

**Planned measurements:**
- File read/write accuracy on a real multi-file task
- Terminal/shell execution reliability
- Test-and-build loop completion — does it verify its own work before declaring a task done
- Failure-repair behavior — what happens after a first
- Diff/edit quality against an existing codebase
- Compatibility with externally-authored agent "skill" tool packages) not written specifically for Qwen
- Approximate cost and token efficiency versus a Claude Code baseline on an equivalent task

**Why this matters:** the existing Claude Code write-ups in this repo test coordination patterns — multi-agent handoffs, adversarial completion audits, deterministic close-out pipelines — -agnostic. This evaluation is the actual test of thatclaim: whether the same patterns hold up when the execution agent is swapped for a different model family, rather than assuming portability
without checking.
