# Todo Plugin

Lightweight task management for Claude Code sessions.

## Resolving the config directory

The todo data lives under the user's `.claude` config directory. To find it:

1. Run `echo $HOME` via Bash to get the user's home directory
2. The config directory is `<home>/.claude/`

All paths below use `$CLAUDE_CONFIG` as shorthand for this resolved absolute path.

## Data locations

- **Master todo list**: `$CLAUDE_CONFIG/todo.md`
- **Plan directories**: `$CLAUDE_CONFIG/todo/<N>/` (per-task plans and working files)

## Todo file format

`todo.md` has two sections:

1. **`## Summary`** — a markdown table with columns `#`, `Task`, `Dir`, `Plan`, `Status`. This is the quick-reference view printed by `/todo`.
2. **`## Tasks`** — full task entries with headings, directory, and description.

All skills that modify tasks must update **both** the summary table and the full entry to keep them in sync.
