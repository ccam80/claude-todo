---
name: todo-remove
description: Mark a task as complete or remove it from the todo list
argument-hint: <task name or number>
---

Read `C:\Users\cca79\.claude\todo.md`.

If $ARGUMENTS matches a task (by name or number), remove it. If no arguments or ambiguous, print the summary table and ask the user which task to remove.

**Two edits are required:**

1. **Remove the row from the summary table** in the `## Summary` section.
2. **Remove the full task entry** (the `### N.` heading and all its content) from the `## Tasks` section.

Note: the task's plan directory at `C:\Users\cca79\.claude\todo\<N>\` (if it exists) is kept as an archive. Do NOT delete it.

Confirm what was changed.
