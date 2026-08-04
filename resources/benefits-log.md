# Benefits Log

Purpose: a quantitative record of what this memory/token method actually buys — token efficiency, usage patterns, and contextual-understanding quality — so claims in the public README are backed by real sessions, not impressions.

This is different from `/workstations/linkedin-content/build-log.md`, which is anecdotal raw material for posts. This file is the evidence; the build log is the story.

## How to log an entry

After a session where something notable happened — a big token difference, a moment Claude correctly applied a project rule without being told, a moment it *didn't* and you had to correct it — do this:

1. Run the `explain-usage` skill (if available for that session) to get a token breakdown.
2. Add one row to the table below. Keep it short — 1–2 sentences per column, same hygiene as the memory system.
3. If it's post-worthy, cross-link it into `build-log.md` too.

Don't force an entry every session. Sparse-but-real data beats padded data.

## Entries

| Date | Session / Task | Tokens (from `explain-usage`) | Context-quality note | Before/After comparison |
|---|---|---|---|---|
| — | — | — | — | — |

*No entries logged yet — this table fills in as real sessions happen. See the CLAUDE.md rule (Section 3) that triggers logging.*

## Summary (update periodically once entries accumulate)

Once there are enough rows to see a pattern, summarize it here in 2–3 sentences: rough token trend, most common type of context win, anything that *didn't* work as expected. This section — not the raw table — is what the public README's Results section should quote.
