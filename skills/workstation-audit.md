# Skill: Workstation Audit

**Triggers on:** "audit [workstation]", "audit the workspace", "check for bloat", or monthly as maintenance.

**Scope:** one named workstation, or the whole workspace (root CLAUDE.md + all workstations) if none named.

**Steps:**
1. Read root `CLAUDE.md` and the target workstation's `claude.md` (all of them for a full audit).
2. **Misplaced entries** — apply the placement test to every entry: flag facts/status sitting in a claude.md (belongs in built-in memory) and prescriptive rules sitting in memory (belongs in a claude.md).
3. **Bloat** — check line counts against ceilings (root: 300). Flag any section needed only for specific tasks that could relocate to `/resources` with a one-line pointer. Flag memory entries over 2 sentences.
4. **Gaps** — flag: workstations missing from the routing map or Section 5 index; skills missing from Section 6; pointers to files that don't exist; workstations without a claude.md; stale index lines pointing at removed things.
5. **Duplication** — flag rules stated in both root and a workstation claude.md (workstation files should only add, never repeat).
6. Write the report to the outputs folder, then share it.

**Output:** a report with an executive summary up front, then findings grouped by category (misplaced / bloat / gaps / duplication), each with a specific recommended fix. Do not apply fixes — Caleb approves first, then changes run as a batch.
