# Instruction templates

Use only the sections the setup needs. Every line must pass the instruction checks.

## Project, GPT, `AGENTS.md`, or `CLAUDE.md`

```
[One sentence: what this project is for and who the work serves.]

## Rules
- [Only rules that change behavior in most chats here, stated as the target behavior.]

## Files
- Before [trigger], open `[file-name]` ([what it holds]).

## Defaults
- [Format, length, and finish line for the task this project repeats most.]
```

In a folder workspace (ChatGPT Work, Cowork), replace Files with a routing map, one line per file or folder:

```
## Where things live
- `[file or folder]`: [what it holds]. Open it when [trigger].
```

## Account-level instructions

Only what is true in every chat: the user's role and audience, preferred answer length and format, and tone as a leading word. Project-specific rules belong in their project.
