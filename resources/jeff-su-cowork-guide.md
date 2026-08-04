# Jeff Su's Cowork Setup Guide (reference — loads on demand only)

The written guide this workspace's setup is based on. Kept here for reference; it does NOT load every session. Two important ideas from the original video that this written summary under-emphasizes: the **prescriptive-vs-fact placement test** and **cascading memory** (per-workstation memory files) — both are now encoded in the root CLAUDE.md, Section 1.

---

## Tip 1: Use Obsidian as Your Markdown Editor

Claude Cowork's instructions and memory live in `.md` files. Editing them inside the chat panel is painful. Install Obsidian (free, obsidian.md), open your Cowork workspace folder as a vault, and all `.md` files render readably. Claude picks up Obsidian edits the next session.

Pro tips: `Cmd/Ctrl +` to zoom; Reading Mode icon to lock a file from accidental edits; Settings → Files and Links → Show all file types to see spreadsheets, PDFs, and images in the sidebar.

## Tip 2: Keep CLAUDE.md Under 300 Lines

CLAUDE.md loads every session; bloat wastes tokens (Jeff cut 600+ → ~250 lines, ~25% token reduction). Target 200–250 lines, hard ceiling 300.

Six sections (per the video): memory system pointer, preferences, rules, routing map, references (one-line pointers to on-demand files), and a creating-new-workstations pointer. Task-specific instructions live in a `/resources` folder, loaded on demand.

**Relocation test:** does Claude need this every session, or only for a specific task? If task-specific, move it to a sub-file and leave a one-line pointer.

**Placement test (from the video, missing from most summaries):** prescriptive entries ("always/never", "before X do Y") belong in CLAUDE.md; facts that could change belong in memory. Periodically audit both files for misplaced entries.

## Tip 3: Put MEMORY.md on a Diet

Root memory loads every session too. Structure: Active Projects / Scheduled Tasks / Core Memory. Hard ceiling 150 lines; entries 1–2 sentences max. When the ceiling is breached, compress and archive — never raise the ceiling. Old context moves to `archive.md`, which does NOT load at session start (so it needs no ceiling).

**Cascading memory (the key mechanism):** each workstation/project gets its own memory file. Root memory holds one status line per project and points down. This — not the ceiling — is why Jeff's root memory stays under 100 lines.

*(This workspace uses Claude's built-in memory system instead of a literal MEMORY.md — same principles, one system.)*

## Tip 4: The Project Transplant

Migrate native Claude Projects into the Cowork workspace for full structural control: project instructions → workstation claude.md; project memory → workstation memory file; knowledge files → the workstation's resources folder. Each migrated workstation is a **folder** (claude.md + memory + resources/), and the root routing map gets a new entry pointing to it.

## Tip 5: Workstations vs. Skills

The test: **is this a place I work, or a thing I do?** An ongoing area of work with its own voice and accumulated context → workstation (collaborative, human judgment in the loop). A repeatable process done the same way every time → skill (runs on autopilot, predictable output). Example skills: subject-line generator, workstation audit.

## Resources

- Free Cowork Toolkit & templates: https://academy.jeffsu.org/co-work-toolkit
- Obsidian: https://obsidian.md/
- Full Cowork playlist: https://www.youtube.com/playlist?list=PLfJdBHKuLOTRIlXB0KzCoe88cYM0ysiZp
