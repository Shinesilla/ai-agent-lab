# Adversarial Completion Audit

**Problem:** Agents self-report task completion, and that self-report is easy to trust by default. But an agent's account of "done" can diverge from what actually happened, especially on multi-step tasks where partial progress can look complete from the inside — the agent isn't lying, it's just reporting its own belief rather than checking evidence.

**Approach:** A review pattern where a second, independent agent instance re-checks a first agent's completion claim against primary evidence — file diffs, script output, test results — instead of trusting the report text itself. The checking agent has no access to the reporting agent's reasoning or conversation history, only the artifacts it actually produced. This forces the check to answer "does the evidence support this claim" rather than "does this explanation sound reasonable."

**Result:** Run against a sample of prior task reports, the audit surfaced cases where a "done" claim wasn't backed by evidence in the artifacts — not because the reporting agent fabricated anything, but because the underlying check had never actually been run before the claim was made. The pattern generalizes: any workflow that uses an agent's self-report as a gate benefits from a second, independent agent checking evidence instead of trusting the claim directly.
