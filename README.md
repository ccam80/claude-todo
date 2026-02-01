# Todo Plugin for Claude Code

A lightweight task management plugin for Claude Code sessions.

## Using it
Want to see what's on your todo list?
```
  /todo
```
Claude will print a numbered list of items and descriptions, and whether those items have a current plan.md file created.

Have an idea while you're working on something else? Tell Claude about it. Don't worry about format, just describe the task, Claude will interpret it. If you don't provide a directory that the project is in, Claude will ask you for it. It will also offer to read all of the reference info it has and make a plan for the job, which you can accept if you want it to do some beginning legwork:
```
/todo-add add [feature] to my other project.
```

Have an idea about a running todo item that you don't want to forget? Checkout the task, make the change, check it back in.

```
\todo-checkout 2    #or
\todo-checkout the task about that feature I wanted

Do some research on how we can interface with [x]. Create a concrete specification for the interface that agents can use later to design our code

\todo-checkin
```

Done? 
```
\todo-remove 2
```

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
