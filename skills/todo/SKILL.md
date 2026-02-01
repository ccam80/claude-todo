---
name: todo
description: Show outstanding tasks from the master todo list
---

First, resolve the user's home directory by running `echo $HOME` via Bash. The todo file is at `<home>/.claude/todo.md`.

Read ONLY the summary table at the top of that file (everything between `## Summary` and `## Tasks`) and print it verbatim.

Do NOT read or display the full task descriptions below the table. Do NOT ask which task to work on — just print the table and stop. The user will indicate their next move.
