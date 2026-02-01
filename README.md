# Todo Plugin for Claude Code

A lightweight task management plugin for Claude Code sessions.

## Installation

Install via the Claude Code plugins interface:

1. Open Claude Code
2. Run `/install-plugin https://github.com/ccam80/claude-todo`

That's it. The `/todo` commands are now available in all your sessions.

## Usage

Want to see what's on your todo list?
```
> /todo
```
```
 #  Task                                 Dir                        Plan  Status
 1  Add CSV export to dashboard          ~/projects/analytics       ✓     Active
 2  Fix auth timeout on mobile           ~/projects/mobile-app      —     Active
 3  Migrate user table to new schema     ~/projects/backend         ✓     Active
```

Have an idea while you're working on something else? Tell Claude about it. Don't worry about format, just describe the task. If you don't provide a directory, Claude will ask. It will also offer to read your project and make a plan:
```
> /todo-add Add retry logic to the payment webhook handler in the backend project
```
```
Added task #4: "Add Retry Logic to Payment Webhook Handler"
  Directory: ~/projects/backend

Want me to read the codebase and draft a plan for this task? (y/n)
```

Have an idea about a running todo item? Check it out, do some work, check it back in:

```
> /todo-checkout 1
```
```
Loaded task #1: Add CSV export to dashboard
  Directory: ~/projects/analytics
  Plan: Read — last updated 2 sessions ago.

Current plan summary:
  - Add "Export CSV" button to report toolbar
  - Use papaparse for serialisation
  - Stream large datasets via Blob URL

Ready to work on this task.
```
```
> Actually, we also need to support Excel .xlsx. Update the plan to use the
  SheetJS library so we can offer both CSV and XLSX from the same button.

> /todo-checkin
```
```
Checked in task #1. Updated plan.md with:
  - Switched from papaparse to SheetJS for dual CSV/XLSX support
  - Added format selector dropdown to export button spec
```

Done?
```
> /todo-remove 2
```
```
Marked task #2 (Fix auth timeout on mobile) as complete and removed.
```

## Skills

| Skill | Description |
|-------|-------------|
| `/todo` | Print the task summary table |
| `/todo-add <description>` | Add a new task |
| `/todo-remove <name or number>` | Mark a task complete / remove it |
| `/todo-checkout <number>` | Load a task's description and plan for the current session |
| `/todo-checkin <number>` | Save session progress back to the task's plan directory |

## Data

All data is stored under your user-level Claude config directory (`~/.claude/` — this is wherever your Claude Code user configuration lives, e.g. `C:\Users\<you>\.claude\` on Windows or `~/.claude/` on macOS/Linux).

- **Task list**: `~/.claude/todo.md` — master file with summary table and full task entries
- **Plan directories**: `~/.claude/todo/<N>/` — per-task plan files and working documents
