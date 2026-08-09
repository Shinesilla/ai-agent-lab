# Session Recovery Tool

**Problem:** A multi-session agent workflow accumulates state across many separate conversations. When a session ends without an explicit handoff, resuming means manually hunting through session history to find the right one — slow and increasingly error-prone as the number of past sessions grows.

**Approach:** A small deterministic script, not agent judgment, was built to solve this. It reads session transcript metadata directly — no agent reasoning involved — and ranks recent sessions by a combination of recency, size, and keyword match against the current query. The design choice was deliberate: recovery should be a fast, repeatable lookup that produces the same answer every time for the same inputs, not something an agent re-derives from scratch each time it's asked.

**Result:** The tool turns "find the right session to resume" from a multi-minute manual search into a single ranked list the operator can scan in seconds. Because the ranking logic is fully deterministic rather than agent-judged, it can be tested and improved independently of any specific agent run, and its output is reproducible given the same transcript set.
