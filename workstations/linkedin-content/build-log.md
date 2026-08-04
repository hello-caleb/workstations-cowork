# Build Log

Dated, raw observations from setting up and running this Cowork workspace. Material for posts — capture findings as they happen.

---

## 2026-08-03 — Setup review and v2 restructure

- **Verified: Cowork auto-loads a workspace-root CLAUDE.md every session.** Nobody could confirm this from documentation; we proved it by observing the file's contents appear in Claude's context without being pasted anywhere. Practical consequence: the project's Instructions field should stay empty.
- **The double-loading trap.** During setup, Jeff Su's ~200-line guide sat in the Instructions field while CLAUDE.md also loaded — both injected every session, doubling the cost the method exists to cut. Setup instructions are one-time reading; they don't belong in anything that auto-loads.
- **Compression loses the best ideas.** A written summary of Jeff Su's video dropped its two most important mechanisms: the prescriptive-vs-fact placement test (rules → CLAUDE.md, changeable facts → memory) and cascading memory (per-workstation memory files — the real reason his root memory stays under 100 lines, not the 150-line ceiling). Checked the full transcript to find them.
- **Workstations are folders, not files.** The summary said "each workstation gets its own .md file"; the video's migration demo shows a folder with its own claude.md, memory, and resources. Single files leave no room for accumulated context.
- First-pass CLAUDE.md: 46 lines. v2 after restructure: ~65 lines. Both far under the 300 ceiling.

## 2026-08-04 — The method became a skill (and got benchmarked)

- **Packaged the whole method as an installable Cowork Skill (`workstation-bootstrap`)** so any new project — new topic, new folder — bootstraps the rules-vs-facts structure in one prompt. Key insight: a project-local skill file can't bootstrap a *new* project (chicken-and-egg — nothing routes to it yet); only an installed, account-level Skill is available before any structure exists.
- **Benchmarked it properly instead of vibing it.** Three test cases (fresh code project, non-technical wedding project, migration of a deliberately bloated 115-line CLAUDE.md), each run with and without the skill, graded by independent agents against ~30 assertions. v1: 96% with skill vs 60% without — the baseline runs had the right spirit but drifted on every convention (workstations as single files, skills in plugin format, unrequested extras). The drift the method prevents is exactly what showed up the moment the method wasn't loaded.
- **Testing caught what review missed.** Three real defects surfaced only under test: no migration guidance despite the description promising it; facts stranded in memory if setup is abandoned mid-way (fixed with an in-project staging file); and both test runs *inventing years* for undated facts during migration ("in May" became "May 2025" in one run, "May 2026" in the other). A no-fabrication rule now exists because two independent runs made the same mistake.
- **v2 skill: 100% (33/33) vs old version's 85% on the same stricter tests.** Every fix individually validated — the old version reproduced each defect on cue.
- **Token cost of rigor: ~18–25% more per bootstrap.** Traced it to redundant work (self-audit re-reading files it just wrote; drafting everything twice), not to thinking. Trimmed both with no loss of checking. Lesson: bootstrap cost is a one-time proxy metric; per-session steady-state cost is the objective — same placement-test logic, applied to ourselves.
- **Context rot, resolved as design instead of instrumentation.** No harness gauge exists for context fill in the desktop app, and published guidance (Anthropic's context-engineering post, the "context rot" research) supports symptoms over thresholds — degradation is gradual and task-dependent, so any fixed percentage is false precision. The template now ships two rules: checkpoint state to memory at natural pauses (the handoff document is always already written), and proactively suggest a fresh chat when quality drifts. Old chats become disposable by design — the scaling answer to handoff-document chains.
