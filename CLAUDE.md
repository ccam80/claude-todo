# Todo Plugin

Lightweight task management for Claude Code sessions.

## Data locations

- **Master todo list**: `C:\Users\cca79\.claude\todo.md`
- **Plan directories**: `C:\Users\cca79\.claude\todo\<N>\` (per-task plans and working files)

## Todo file format

`todo.md` has two sections:

1. **`## Summary`** — a markdown table with columns `#`, `Task`, `Dir`, `Plan`, `Status`. This is the quick-reference view printed by `/todo`.
2. **`## Tasks`** — full task entries with headings, directory, and description.

All skills that modify tasks must update **both** the summary table and the full entry to keep them in sync.
