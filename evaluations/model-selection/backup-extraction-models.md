# Backup Model Selection for Token-Conserving AI Workflows

**Problem:** A recurring task — extracting verbatim content from a large batch of iterative document versions, then analyzing them for quality drift across the sequence — doesn't need a frontier model's full reasoning budget for the extraction half, but was defaulting to one anyway, burning primary-agent token spend on work a free-tier model could plausibly do.

**Approach:** Two stages, and they are worth keeping distinct.

*Stage 1 — shortlisting.* Four free-tier candidates were compared on paper against the task's two demands (verbatim extraction fidelity, analysis quality) to pick one to actually try. This wasmeasured benchmark — the scores below are prior estimates used to choose a starting point, not results from running the task four times.

| Model | Extraction | Analysis | Cost | Context Window |
|:--|:--:|:--:|:--|:--|
| Gemini 2.5 Pro | 9/10 | 7.5/10 | Free tier | 1M tokens |
| Kimi 2.5 | 8/10 | 7/10 | Free tier | 128K tokens |
| DeepSeek R1 | 7/10 | 8/10 | Free tier | 128K tokens |
| Qwen 2.5 | 7/10 | 6.5/10 | Free tier | 128K tokens |

Gemini 2.5 Pro was picked to try first, on the theory tthe entire document set in one pass with no chunking.DeepSeek R1 was noted as the likely better choice for reasoning-heavy passes despite the smaller window.

*Stage 2 — actually running it.* Gemini was given the real task: roughly 29 source documents, extract verbatim, deduplicate, and index.

**Result:** the extraction half held up. Verbatim fidelity was clean on the versions that were spot-checked against source, and the three-stage catalog/deduplicate/extract structure it prle.
                                                                                                                                            Two things did not hold up, and both are the interestin
                                                                                                                                            - **The analysis half silently didn't happen.** The tas version. Gemini catalogued and extracted, but did notjudge — no scores, no diff analysis of what each version added or dropped. It produced an index where an evaluation was requested, and did  not flag the substitution.
- **The context-window advantage didn't survive contact.** The one-pass-no-chunking theory was the entire reason for the pick, but the uploachunked anyway, which forced deduplication to run progrll documents at once. One document family grew from 4 to 8 to 13 members as later chunks arrived — the model couldn't cross-compare everything simultaneously, so dedup quality degraded as it went. 
**Finding:** a large advertised context window is not the same as a large *effective* working set once upload mechanics get involved, and a free-tier model may quietly deliver the easy half of a the harder half without saying so. The extraction wasworth the $0. The unverified assumption — that picking on context-window size would carry the whole job — was the actual lesson.

Free-tier limits, context windows, and model versions move fast. Treat the shortlist above as a snapshot of the versions named, not a standing recommendation.
