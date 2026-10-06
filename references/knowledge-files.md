# Knowledge file audit

Files sit on the bottom rung: the AI reaches them through search or a context pointer. Search matches on file names, headings, and the words inside, so a file's name and first lines work as its pointer from below.

## Inventory

One row per file: name, what it holds, format, how current, and which instruction line points to it. A file nobody can describe in one line is a finding on its own.

## Checks

- **Unclear name.** `Document (3).pdf`, `notes.docx`, `FINAL v2 (1).docx`. Rename to say what is inside and its scope: `brand-voice-guide.md`, `menu-fall-2026.pdf`, `client-onboarding-checklist.docx`. Lowercase words joined by hyphens; add a date or season only when the content expires.
- **Orphan.** No context pointer names the file. Add one, or delete the file if no task needs it.
- **Duplicate.** Two files cover the same ground (`brand-guide-2023.pdf` and `brand-guide-2025.pdf`), or a file repeats the instructions. Keep a single source of truth; merge or delete the rest. When two files disagree, ask the user which is current; until they answer, prefer the later content date and say so.
- **Sediment.** Superseded versions, past campaigns, old prices. Delete them: search returns an outdated file as confidently as a current one.
- **Mixed scope.** One file covering many topics (`everything-about-my-business.docx`). Split by topic so search lands on the right file and each pointer targets one job.
- **Fragments.** Many small files on one topic. Merge into one file with clear headings.
- **Unreadable format.** Scanned PDFs, text inside images, slide decks whose meaning lives in pictures. Convert to text: `.md`, `.txt`, `.docx`, or a text-based PDF. Lookup tables work best as CSV with a header row.
- **No summary header.** A file longer than a page or two with no opening that says what it is. Add 2 to 3 lines at the top: what the file covers and when to use it.
- **Wrong rung.** A few rules every chat needs, buried in a long file, move up into the instructions. Instruction text that is really reference moves down into a file.
- **Stale copy of a live source.** A pasted copy of a web page, price list, or shared doc that keeps changing elsewhere. Record the source and a refresh date in the summary header, or connect the live source if the platform supports it.

## Actions

Every file ends with exactly one action: keep, rename, merge, split, convert, delete, or promote to instructions. The inventory table shows the action and any new name.
