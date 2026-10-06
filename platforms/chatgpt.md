# ChatGPT setups

Checked 2026-10-06. Menus move between releases; when a path does not match, describe what the setting does so the user can find it.

## ChatGPT chat (web, desktop, mobile)

| Layer | Rung | Where the user finds it | Scope |
| --- | --- | --- | --- |
| Custom instructions | Always-read | Settings, Personalization | Every chat |
| Memory | Always-read | Settings, Personalization, Memory | Every chat while memory is on |
| Project instructions | Always-read | The project's Instructions | Every chat in the project; they take priority over custom instructions there |
| Project files | Knowledge | The project's Files | Searched when relevant |
| GPT instructions | Always-read | GPT editor, Configure, Instructions | Every chat with that GPT |
| GPT knowledge | Knowledge | GPT editor, Configure, Knowledge | Searched when relevant |

Project and GPT files are searched, not read in full, so file names, headings, and context pointers decide what gets found. Each instruction box has a character limit shown in its editor; drafts must fit it. Uploaded files cannot be renamed in place: the user renames the file on their computer, removes the old upload, and uploads the new one.

What you can access: custom instructions, memory, and project or GPT instructions are usually in your context, so say which layers you can see. File search shows only what matches a query, so ask the user for the full file list. You cannot change settings or files; hand back paste-ready text.

## ChatGPT Work (desktop app)

Work runs tasks inside a folder on the user's computer and shares Codex's runtime.

| Layer | Rung | Where it lives | Scope |
| --- | --- | --- | --- |
| Custom instructions and memory | Always-read | Settings, as above | Every task |
| `AGENTS.md` | Always-read | The folder root, named exactly `AGENTS.md` | Read before every task in that folder |
| Folder files | Knowledge | The folder and its subfolders | Opened when needed |
| Skills | Disclosed | Skills sidebar or plugins | Loaded when a skill's description matches the task |

The folder is the environment and its file tree is the source of truth. Keep `AGENTS.md` to rules plus a short routing map (which subfolder holds what, and when to open it) rather than a copy of what the folder already shows.

What you can access: read `AGENTS.md` and list the folder yourself. Make edits and file operations only after the user approves the full list.
