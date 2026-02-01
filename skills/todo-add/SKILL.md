---
name: todo-add
description: Add a new task to the master todo list
argument-hint: <task description>
---

Add a new task to `C:\Users\cca79\.claude\todo.md`.

Use $ARGUMENTS as the task description. If no arguments provided, ask the user what task to add.

Every task MUST have a **Directory** field. If the user did not specify a directory, ask them: "What directory should this task start from?"

To determine the next task number, read the file and find the highest existing `### N.` heading, then increment by 1.

**Two edits are required:**

1. **Add a row to the summary table** (in the `## Summary` section) with columns: `#`, `Task`, `Dir`, `Plan`, `Status`. Set Plan to `—` and Status to `pending`.

2. **Append the full task entry** under `## Tasks`:

```markdown
### N. Task Title
- **Directory**: `C:/path/to/directory`
- **Description**:
  - Detail lines...
```

After adding the task, ask the user if they'd like to create an initial plan for it. If yes, create the directory `C:\Users\cca79\.claude\todo\<N>\` and a `plan.md` with the task description and any initial notes.

Confirm what was added.
