---
name: ai-setup-audit
description: Audit and rebuild someone's AI setup in ChatGPT or Claude, covering custom instructions, project or GPT instructions, AGENTS.md or CLAUDE.md, memory, and knowledge files. Use when someone wants to set up a project, fix instructions the AI ignores, organize knowledge files, or learn how a good setup works.
---

# AI setup audit

Audit the user's setup the way an experienced builder would, draft the fixes, and teach the principle behind each finding so the user can build the next setup on their own.

## The setup model

A setup is an information hierarchy with three rungs:

1. **Always-read instructions**: account-level instructions, memory, and project, GPT, or folder instructions (`AGENTS.md`, `CLAUDE.md`). Pure context load: read at the start of every chat in scope, whether or not they apply.
2. **Context pointers**: lines inside those instructions that name a knowledge file and the condition for opening it. The pointer's wording decides whether the file gets opened.
3. **Knowledge files**: reference reached through search or a pointer, read only when needed.

A healthy setup keeps rung 1 short, gives every file a pointer on rung 2, and keeps reference on rung 3. Most setups invert it: long instructions carrying reference, files no pointer names, and the same rule repeated across layers.

Which layers exist, where the user finds them, how files are read, and what you can access directly all depend on the environment. Read the matching file before step 2:

- ChatGPT chat, projects, GPTs, or ChatGPT Work: [`platforms/chatgpt.md`](platforms/chatgpt.md)
- Claude chat, projects, or Cowork: [`platforms/claude.md`](platforms/claude.md)

## Steps

1. **Locate.** Identify the environment and read its platform file. Done when you know every layer this user's setup can have.
2. **Gather.** Collect each always-read layer and a file inventory (name, what it holds, format including whether it is a scan, how current, which instruction line points to it). Where you can read the instruction file and folder yourself, read them; elsewhere ask the user to paste. Ask what goes wrong today. Done when every layer in the platform file is collected or the user has said it is empty, every file is in the inventory, and you have a concrete annoyance or the user asked for a general tune-up.
3. **Audit.** Apply every instruction check below to every always-read layer, and every check in [`references/knowledge-files.md`](references/knowledge-files.md) to every file. Done when each annoyance is traced to a cause, every file has an action, and every failed check is a finding.
4. **Draft.** Read [`templates/instructions.md`](templates/instructions.md), then draft the replacement for each always-read layer, the file changes, and any memory changes. Account-level layers and memory shrink; a project layer grows only by pointers, output defaults, and rules an annoyance proved missing. Done when every draft line passes the instruction checks, every kept file has exactly one context pointer (a folder pointer covers its files), and every number or choice only the user can make is listed as a guess under its copy block, so the pasted text stays clean.
5. **Test.** Write 2 to 4 messages to run in a new chat, each with what a pass looks like. Done when every annoyance has a test.
6. **Apply.** In chat apps the user pastes the drafts and edits the files. Where you have folder access, list every file operation and instruction edit, get the user's yes, then make them. Change saved memory only after the user approves each change.

## Instruction checks

Context load is the lens: a line in an always-read layer costs attention in every chat in its scope, so it earns its place only by changing behavior in most of those chats.

- **No-op.** The model already does it: "be helpful," "you are a world-class expert," "use good grammar." Delete the whole sentence. Test: would a new chat behave differently without it?
- **Missing or weak context pointer.** A file no line names, or a catch-all like "refer to the attached files." Write one pointer per file, file name first, then the trigger: "Before quoting a price, open `pricing-2026.pdf`."
- **Wrong rung.** Reference in the instructions (bios, product lists, long examples) moves down to a file. A rule every chat needs, buried in a file, moves up. A project-only rule in account-level settings moves to that project; a rule several projects share moves up to account level.
- **Duplication.** One meaning in two places, often memory plus instructions plus a file. Keep a single source of truth on the right rung.
- **Conflict.** Two lines pull opposite ways ("be brief," "be thorough"). Pick the winner and the condition for the exception.
- **Negation.** "Don't use jargon" keeps jargon in view. State the target: "use everyday words." Keep a prohibition only as a hard guardrail, paired with its positive.
- **No completion criterion.** A repeated task with no picture of done. Add format, length, or count: "3 subject lines, under 8 words each, best first."
- **Missing leading word.** An adjective pile circling one idea. Replace it with a term the model already knows: "bottom line up front," "plain English," "newsroom style."
- **Sediment.** Old jobs, finished projects, past dates, workarounds for older models.
- **Sprawl.** One project or GPT serving jobs that need different files or output formats, so each chat carries every job's rules. Split by job when the jobs share few files; when most files serve every job, keep one project and give each job its own default.

## Teaching

The user learns from their own setup, not from a lecture. Teach in two places: a few words of why on each fix ("so ChatGPT knows which file holds your method"), and the "Why this works" section, which names the two or three principles behind the biggest fixes. Name each principle and define it in one plain sentence:

| Principle | Define it as |
| --- | --- |
| Context load | Everything in your instructions is read in every chat, so every line has to earn its place. |
| Context pointer | A line that tells the AI which file to open, and when. |
| Progressive disclosure | Keep instructions short and put the detail in files the AI opens when needed. |
| Single source of truth | Say each thing once, in one place. |
| No-op | A line the AI already follows without being told. |
| Negation | Telling the AI what not to do puts that very thing in its head. |
| Sediment | Leftovers from old jobs, old files, or older models. |
| Completion criterion | A clear picture of what a finished answer looks like: format, length, count. |
| Leading word | A familiar phrase that carries a whole style, so one phrase replaces a pile of adjectives. |
| Sprawl | One setup doing too many jobs, so every chat carries rules it does not need. |

Write for a smart adult who is new to these ideas: everyday words, short sentences, and each technical term explained the first time.

## Output

The reader acts on this today, so apply progressive disclosure to them too: actions first, reasons second, the full audit on request. Keep everything outside the copy blocks under 500 words; when over, trim tests and principles to two each before trimming fixes.

1. **The short version.** Two or three sentences on what causes each annoyance.
2. **Your fix list.** Numbered steps in the order to do them. One action per step, where to click, which copy block to use, and a few words of why. Done when the user could finish every step without asking how.
3. **Copy blocks.** One per layer, labelled with where it goes. A layer that should end up empty gets "Clear this field." List guesses under the block.
4. **Files.** A checklist of renames, merges, splits, conversions, and deletions, with the new names. Offer to do the text work for splits, merges, and summary headers: the user pastes the file and gets back new files ready to save.
5. **Memory.** Each delete, edit, or addition, for the user to approve one by one.
6. **Why this works.** Two or three principles, each tied to something in the user's own setup.
7. **Test it.** The test messages and what a pass looks like.
8. **Questions.** Only the ones that block a fix.

End by offering the full audit: every finding with its check and principle.
