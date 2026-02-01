---
name: todo-checkout
description: Check out a task — load its description and plan directory contents
argument-hint: <task number>
---

First, resolve the user's home directory by running `echo $HOME` via Bash. The todo file is at `<home>/.claude/todo.md`. The plan directories live under `<home>/.claude/todo/`.

Check out a task for the current session.

If $ARGUMENTS is a task number, use it. Otherwise print the summary table from the todo file and ask.

Steps:
1. Read the todo file and find the task by number
2. Display the task's full description
3. Check if `<home>/.claude/todo/<N>/` exists
   - If it does, read `plan.md` and list all other files in the directory. Read any `.md` or `.txt` files and summarise other file types present.
   - If it doesn't, tell the user there's no plan directory yet — one will be created on checkin
4. **Update the summary table**: set the task's Status to `active`
5. Note the task's **Directory** field and set that as the working context
6. Summarise the current state: what was done previously (from plan.md) and what remains

The user is now working on this task. All subsequent work should be understood in the context of this task until the user checks in or switches.
