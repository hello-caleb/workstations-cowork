# Creating a New Workstation (read before scaffolding one)

A workstation is a **folder** under `/workstations`, not a single file. Scaffold this structure:

```
/workstations/<name>/
  claude.md        # the workstation's own instruction set
  resources/       # only if it has reference material (examples, style guides)
```

Workstation-specific *memory* (facts, status, decisions) goes in Claude's built-in memory as a dedicated memory file for that workstation — not in a memory.md inside the folder. This is the cascading pattern: root index holds one line, detail loads only when the workstation is active.

## claude.md contents

```markdown
# [Workstation Name]

**Purpose:** what this workstation is for
**When to use:** what triggers a session here
**Inputs Claude needs:** files, data, context to gather first
**Typical flow:** the back-and-forth steps of a session
**Standing rules:** prescriptive, workstation-specific only — nothing the root CLAUDE.md already covers
```

## After scaffolding — always do all three

1. Add a routing-map row in root `CLAUDE.md` (Section 4) pointing to the new claude.md.
2. Add an index line under root `CLAUDE.md` Section 5.
3. Create the workstation's memory file in built-in memory with a one-line index entry.

## Checks

- Apply the placement test: rules in claude.md, facts in memory.
- Keep the workstation claude.md lean — same philosophy as root, smaller scale.
- For simple workstations with no resources, the folder may hold just claude.md. Still use a folder — it leaves room to grow.
