# Todo Plugin for Claude Code

A lightweight task management plugin for Claude Code sessions.

## Skills

| Skill | Description |
|-------|-------------|
| `/todo` | Print the task summary table |
| `/todo-add <description>` | Add a new task |
| `/todo-remove <name or number>` | Mark a task complete / remove it |
| `/todo-checkout <number>` | Load a task's description and plan for the current session |
| `/todo-checkin <number>` | Save session progress back to the task's plan directory |

## Setup

Add to your Claude Code settings (`.claude/settings.json`):

```json
{
  "plugins": ["C:/local_working_projects/todo"]
}
```

## Data

- **Task list**: `C:\Users\cca79\.claude\todo.md` — master file with summary table and full task entries
- **Plan directories**: `C:\Users\cca79\.claude\todo\<N>\` — per-task plan files and working documents
