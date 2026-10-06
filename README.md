# AI Setup Audit

Audit the instructions, memory, and files your ChatGPT or Claude setup runs on,
then get the fixes ready to paste. For anyone who uses projects, custom GPTs,
Cowork, or ChatGPT Work for repeated work and feels the AI keeps ignoring them.

**[Download the skill ZIP](https://github.com/techwithtam/ai-setup-audit/releases/latest/download/ai-setup-audit.zip)**
· [Read the skill](SKILL.md) · [See an example audit](examples/personal-trainer.md)

The ZIP contains the complete skill folder:

```text
ai-setup-audit/
├── SKILL.md
├── platforms/
│   ├── chatgpt.md
│   └── claude.md
├── references/
│   └── knowledge-files.md
└── templates/
    └── instructions.md
```

`SKILL.md` holds the audit steps and tells the assistant which other file to
read at each step. Keep the folder together so those links work.

No plugins, code, API keys, or account connections are required.

## What it does

It reviews your whole setup at once: account instructions, memory, project or
GPT instructions, `AGENTS.md` or `CLAUDE.md` files, and the knowledge files
they rely on. You get back:

- what is causing your problem, in two or three sentences
- a numbered fix list in the order to do it
- new instructions ready to paste, with one clear line per file
- a checklist of files to rename, merge, split, or delete
- memory changes for you to approve one at a time
- a few test messages to check that the fix worked

Each fix comes with the reason behind it, so you learn how a good setup works
while you repair yours.

## Upload to Claude

1. Download the ZIP above. Keep it zipped.
2. In Claude, open **Customize > Skills**, then **+ > Create skill > Upload a skill**.
3. Upload `ai-setup-audit.zip` and turn the skill on.
4. Open the project you want to audit and send the request below.

Claude requires **Code execution and file creation** to be enabled under
**Settings > Capabilities**. A team administrator may control skill uploads.
[Claude's upload instructions](https://support.claude.com/en/articles/12512180-use-skills-in-claude)
cover those settings. Skills you upload also work in Cowork.

## Use in ChatGPT

1. Download the same ZIP and attach it to a ChatGPT Work chat that can open files.
2. Ask: "Unzip this file, read SKILL.md and the files it links to, and use the skill to audit my setup."
3. Add the request below.

If your chat cannot open the ZIP, unzip it yourself and attach every file in
the folder, or paste their contents. Saving a skill for reuse depends on your
app and workspace.
[OpenAI's skill documentation](https://learn.chatgpt.com/docs/build-skills)
explains the supported skill environments.

## Install for Claude Code, Codex, Cursor, and other agents

```bash
npx skills add techwithtam/ai-setup-audit
```

## Start with your problem

> Audit my AI setup for this project. Here's what keeps going wrong: [describe it]. Ask me for anything you can't see.

Paste your instructions and list your files when it asks. In Cowork and
ChatGPT Work it can read your folder itself, and it asks before changing
anything.

It cannot change your settings, so in chat apps you paste the new text
yourself. Numbers it suggests, such as a word limit, are starting guesses for
you to adjust.

## Credits

The approach adapts [writing-for-agents](https://github.com/mattpocock/skills)
by Matt Pocock, used under the MIT License. See [NOTICE.md](NOTICE.md).

Created by [Tech With Tam](https://techwithtam.com/resources/ai-setup-audit).
Released under the [MIT License](LICENSE).
