# Skills (plain-markdown checklists)

**Important distinction:** these are not Cowork's installed Skills (the plugin-backed ones auto-suggested in chat). These are plain `.md` checklists that Claude reads on request when a task matches. No judgment needed — once triggered, Claude runs the process start to finish.

Examples: publishing a post, running a research sweep, a recurring data pull.

## How to create one

1. Make a new `.md` file in this folder, named after the skill (e.g. `publish-post.md`).
2. Write the process as a repeatable, ordered checklist — precise enough that Claude doesn't need to ask clarifying questions mid-run.
3. Add a line pointing to it under "Skills" in the root `CLAUDE.md` routing map.

## Template

```markdown
# [Skill Name]

**Triggers on:** phrases or situations that should invoke this skill

**Steps:**
1. ...
2. ...
3. ...

**Output:** what gets produced and where it goes
```

## Current skills

- [none yet]
