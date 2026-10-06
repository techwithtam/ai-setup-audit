# Example: a personal trainer's ChatGPT project

This is a made-up setup. Jess, a personal trainer, uses one ChatGPT project for client programs, check-in messages, and Instagram posts. She says the programs ignore her method and every answer is a wall of text. She pasted her custom instructions, memory, project instructions, and file list. Below is the audit the skill returned.

---

### The short version

Programs come out generic because "use my files" never names a file, your exercise library is buried in `Everything.docx`, and a 2023 template competes with the current one. Answers run long because "be detailed" gives no finish line.

### Your fix list

1. Do the Files checklist below first, so the pointers have files to find.
2. In the Coaching project, open Files. Remove the old files, then upload the new ones.
3. Replace the project's Instructions with Block 2, so each file gets opened.
4. In Settings, Personalization, Custom instructions, paste Block 1 into "What traits should ChatGPT have?" It keeps answers short.
5. On that screen, clear "Anything else." It is out of date.
6. In Memory, Manage memories, delete the five items below once you agree.
7. Run the tests below in a new chat.

### Copy blocks

**Block 1.** Custom instructions, "What traits should ChatGPT have?"

```
Upbeat and direct, like a good coach. Bottom line first, then short paragraphs. Use a table or short list when it makes things easier to scan. Go longer only when I ask for more.
```

"Anything else ChatGPT should know about you?": Clear this field.

**Block 2.** Coaching project, Instructions.

```
Coaching assistant for Jess, an online and in-person personal trainer whose clients are mostly busy moms 30 to 50. Jobs: client programs, check-in messages, Instagram posts.

### Rules
- Every program has 3 phases: Build (4 weeks), Load (4 weeks), Peak (2 weeks).
- Every week has 3 strength days and 2 walks. Every session runs under 45 minutes.
- Beginners get no barbell work. Use dumbbells, machines, bands, and bodyweight instead.
- When a client mentions pain, an injury, or a health condition, suggest they get their doctor's okay first and keep to training choices.

### Files
- Before writing any program, open `program-template.docx` (the layout every program follows) and pick exercises from `exercise-library.docx`.
- Before writing a program for a new client, check `client-intake-questions.pdf` and ask me for any answers I have not given.
- Before writing a check-in message, open `client-check-in-examples.txt` (messages I liked).
- Before writing an Instagram post, open `instagram-caption-examples.docx`.
- Before quoting a price or answering a question about my services, open `business-info.docx` (bio, prices, FAQ).

### Defaults
- Programs: one phase at a time unless I ask for all three, as a table with one row per session.
- Check-in messages: 3 to 5 sentences, ending with one question, in the voice of the examples.
- Instagram posts: under 100 words, a hook first line, one call to action.
- Emojis: up to 2 in check-ins and posts, none in programs.
```

Guesses to edit: beginner equipment, one phase at a time, check-in length, 100-word limit, emoji cap.

### Files

- [ ] Split `Everything.docx` into `exercise-library.docx`, `instagram-caption-examples.docx`, `business-info.docx` (bio, prices, FAQ). Delete the original.
- [ ] Rename `Program Template FINAL.docx` to `program-template.docx`, `Untitled document.pdf` to `client-intake-questions.pdf`, and `client check-in examples.txt` to `client-check-in-examples.txt`.
- [ ] Delete `program template old.docx`. Search may treat it as current.
- [ ] Delete `Nutrition Basics (scanned).pdf`: a scan ChatGPT reads poorly, and no job uses it.
- [ ] Start the template, library, and business files with 2 lines on what each covers and when to use it. Date the prices.

Want me to do the splitting? Paste the contents of `Everything.docx` here and I'll return the three new files, ready to save.

### Memory (approve each delete)

- "Is a personal trainer named Jess": in custom instructions.
- "Works mostly with busy moms": same.
- "Prefers upbeat tone": Block 1 covers it.
- "Is launching a supplement line in summer 2025": date has passed.
- "Uses the 3-phase Build, Load, Peak method": now in the project instructions.

### Why this works

- **Context pointer.** A line that tells the AI which file to open, and when. "Use my files" named none.
- **Context load.** Everything in your instructions is read in every chat, so every line must earn its place. "Elite fitness expert" did not.
- **Completion criterion.** A clear picture of what a finished answer looks like: format, length, count. "Be detailed" gave none.

### Test it

1. In the project: "New client: Sam, 40, beginner, dumbbells at home. Write her program." Pass: it asks for missing intake answers, then writes only the Build phase, as a table, no barbell, sessions under 45 minutes.
2. In the project: "Write a check-in for a client who missed two workouts." Pass: 3 to 5 sentences, one closing question.
3. In the project: "Write an Instagram post about why walks count as training." Pass: under 100 words, a hook, one call to action.

Want the full audit, with every finding's check and principle?
