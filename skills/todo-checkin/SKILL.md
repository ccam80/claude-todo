---
name: todo-checkin
description: Check in a task — save progress, plan updates, and working files
argument-hint: <task number>
---

Save progress on a task back to its plan directory.

If $ARGUMENTS is a task number, use it. If only one task was checked out this session, use that. Otherwise ask.

Steps:
1. Create `C:\Users\cca79\.claude\todo\<N>\` if it doesn't exist
2. Write or update `C:\Users\cca79\.claude\todo\<N>\plan.md` with:
   - **Status**: brief one-line summary (e.g. "In progress — fixture refactor done, coverage at 80%")
   - **Last session**: date and summary of what was accomplished this session
   - **Approach**: current strategy/decisions (update if changed)
   - **Next steps**: concrete items to pick up next session
   - **Open questions**: anything unresolved
   - Preserve previous session entries under a `## Session log` section (append, don't overwrite)
3. If there are working files discussed or produced during the session, save them to the task directory and reference them from plan.md
4. **Update the summary table** in `C:\Users\cca79\.claude\todo.md`:
   - Set the task's Plan column to `yes`
   - Set the task's Status back to `pending` (or a brief status like `in progress` if partially done)
5. Confirm what was saved, listing all files written to the task directory
