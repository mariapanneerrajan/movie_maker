# Stage 8 — ship and retrospective

Runs automatically on gate 7 approval. Two halves: move the work out of the sandbox, then harvest
what the film taught the system.

---

## Ship

This is the only irreversible step in the pipeline. Take it carefully.

### 1. Derive and confirm the folder name

From the chosen title in `05_title.md`. Sanitise for Windows: strip `< > : " / \ | ? *`, strip
trailing dots and spaces, keep it under 60 characters. Keep the title's own capitalisation and
spaces — `c:\movie_maker\The Keeper of Small Lights\` is a fine folder name and reads better than
an underscored one.

**Confirm the exact path with Rajan before moving anything.** One short message: here is the
folder I am about to create, here is what moves into it, the sandbox is deleted afterwards.

### 2. Move

Create the folder. Move every artifact from the sandbox into it, preserving the internal
structure — `00_seed.md` through `06_thumbnail.md`, `02_assets/`, `03_storyboard/`.

`PIPELINE.md` moves too. It is the record of every correction Rajan asked for, and it is worth
keeping with the film.

### 3. Verify, then delete

Compare the file list in the destination against what was in the sandbox — same count, same names,
same nesting. Only once that matches, delete the sandbox folder.

If anything is missing, stop and say so. Do not delete a sandbox you have not verified out of.

---

## Retrospective

Runs in the main thread, not a subagent — it needs the conversation, which subagents cannot see.

### What to read

- `PIPELINE.md` — every correction Rajan asked for, logged verbatim at the gate it happened
- `01_script_notes.md` — what the reviewers caught, and what the head writer declined
- The conversation itself — tone, hesitation, the things he asked for twice
- The current `.claude/craft/craft-*.md` files, so you propose lessons rather than duplicates

### What to look for

The signal is **repetition and correction**, not everything that happened. Specifically:

- A correction Rajan made more than once, at any stage
- A correction he made that the craft files should have prevented
- A reviewer finding that turned out to be right and was nearly missed
- A prompt pattern that clearly worked, worth keeping
- Something about how he wants to work, rather than about the film

Ignore one-offs specific to this story. "Mira should be older" is not a lesson. "Rajan cuts the
line where a character names the theme, every time" is.

### What to propose

**Up to 5 craft lessons**, each routed to the right file — `craft-story.md`, `craft-visual.md`,
`craft-assets.md`, `craft-seedance.md`, `craft-thumbnail.md`. One line each, in the format from
`CRAFT.md`:

```
- **[S-007]** When <trigger condition> → <the rule>. *(<film title>)*
```

The trigger must be concrete enough that a cold agent can recognise the situation. Prefix by file:
`S-` story, `V-` visual, `A-` assets, `D-` seedance, `T-` thumbnail. Number sequentially within
each file.

A lesson that contradicts an existing one **replaces** it — say which one, and why the new reading
supersedes it. If a file passes ~25 lessons, consolidate before adding.

**Up to 2 memory shards**, for things about Rajan or the project rather than about craft. These go
to `C:\Users\maria\.claude\projects\c--movie-maker\memory\` with an index line appended to
`MEMORY.md`. Use them for durable preference and working style; craft belongs in the repo files,
because that is the only place the agents can read it.

### Propose, then write

Show the proposed lessons and shards in chat and **wait for approval**. Nothing is written until
Rajan says yes. He may accept some and reject others.

Then write the approved ones, and report what changed — which files gained which lessons. Those
files are read by every agent on the next film, so it is worth him knowing what he just taught
them.

### Standalone

`/movie retro` runs this half alone, at any point, so a lesson learned mid-film is not lost
waiting for a ship that may be days away.
