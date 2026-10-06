# Claude setups

Checked 2026-10-06. Menus move between releases; when a path does not match, describe what the setting does so the user can find it.

## Claude chat (claude.ai, desktop, mobile)

| Layer | Rung | Where the user finds it | Scope |
| --- | --- | --- | --- |
| Instructions for Claude | Always-read | Settings, Instructions for Claude (older versions: personal preferences on the Profile page) | Every chat and every Cowork session |
| Styles | Always-read while selected | The style picker in the message box | Chats using that style |
| Memory | Always-read | Settings, memory options | Every chat while on; each project keeps its own memory |
| Project instructions | Always-read | The project's Instructions | Every chat in the project |
| Project knowledge | Knowledge, or always-read while small | The project's Files | Read in full while the project is small; searched once it grows past what fits (RAG mode, paid plans) |

A small project's files are context load: every file is read in every chat, so a stale or off-topic file pollutes every answer. Weigh file cleanup accordingly. Uploaded files cannot be renamed in place: the user renames the file on their computer, removes the old upload, and uploads the new one. Pointers still earn their line here, with a different job: with every file already in view, a pointer says which file governs which task and which wins when two disagree. Once the project switches to search, the same line becomes the trigger that gets the file found.

What you can access: inside a project you usually see the project instructions and, while the project is small, the files' contents, so say which layers you can see. Ask the user for anything you cannot see, including account instructions outside the project. You cannot change settings or files; hand back paste-ready text.

## Claude Cowork (desktop app)

| Layer | Rung | Where it lives | Scope |
| --- | --- | --- | --- |
| Instructions for Claude | Always-read | Settings, shared with chat | Every session |
| Cowork project instructions | Always-read | The project's settings, Instructions | Every session in the project |
| `CLAUDE.md` | Always-read | A project folder | Read for project instructions; when a folder has no `CLAUDE.md`, Claude reads `AGENTS.md` instead |
| Project memory | Always-read | Saved by Claude per project | Every session in the project |
| Folders, links, linked claude.ai projects | Knowledge | The project's settings | Opened when needed |
| Skills and plugins | Disclosed | Customize, plugins | Loaded when a skill's description matches the task |

Cowork offers two always-read homes for project rules: project instructions and `CLAUDE.md`. Rules split across both are a duplication finding. Pick one home: `CLAUDE.md` travels with the folder; project instructions stay in the app.

The folders are the environment and their file tree is the source of truth. Keep `CLAUDE.md` to rules plus a short routing map rather than a copy of what the folders already show.

What you can access: read `CLAUDE.md` and the attached folders yourself. Make edits and file operations only after the user approves the full list.
