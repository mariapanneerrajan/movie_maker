# Stage 1 — seed capture and five loglines

Gates 0 and 1. Run from the main thread; no subagents needed.

## Gate 0 — capture the seed

If `00_seed.md` does not exist or has no seed recorded, ask Rajan for it. He may give you a fully
formed idea, a fragment, an image, a feeling, or a verse. Any of those is enough.

Ask for what is missing, in one message, and only what genuinely matters:

- The seed idea itself
- What he wants to convey through the story
- What he wants the audience to feel as the credits land

If he gave all three unprompted, do not ask again — write the file and move straight to gate 1 in
the same turn.

Write `<sandbox>/00_seed.md`:

```markdown
# Seed

**Captured:** <YYYY-MM-DD>

## The seed idea
<verbatim, as Rajan gave it>

## What this should convey
<...>

## What the audience should feel
<...>

## Loglines
*(filled at gate 1)*

## Chosen
*(filled when Rajan selects)*
```

## Gate 1 — five one-line ideas

Read `CLAUDE.md`, `.claude/craft/CRAFT.md`, and `.claude/craft/craft-story.md` (the lessons at the
bottom of craft-story especially — they encode what Rajan has picked and rejected before).

Generate **five loglines**. Each is genuinely one line — a sentence, maybe two clauses. Not a
paragraph, not a pitch.

### What makes these five good

**Spread them.** Five variations on one idea wastes the gate. Vary the genre, the scale, the tone,
the protagonist's relationship to the problem, and which Biblical pattern sits underneath. One of
the five should be the obvious strong reading of the seed; one should be the strange one Rajan
would not have thought of.

**Each must be shootable in 180 seconds.** One character, one want, one obstacle, one change. A
logline implying a feature film is not a candidate.

**Each must carry something true**, woven in — see `craft-story.md`. Name the scripture anchor
alongside each so Rajan can see what it is really about. The anchor is for him, not for the film.

**Each must promise spectacle.** The charter asks for inventive worlds, creatures, robots, and
rich visual effects. A logline that could be shot in a kitchen is under-using the medium.

### How to present them

In chat, not in a file — Rajan reads these in the terminal and picks. Number them 1 to 5. For
each: the logline in bold, then two short lines — `Anchor:` the Biblical pattern underneath, and
`Why it works:` the reason it is worth 180 seconds. Keep the whole set scannable; this is a menu,
not an essay.

Then stop. Say plainly that he can pick a number, or ask for five more.

### If he asks for another five

Generate a genuinely fresh set — do not re-skin the first five. Note briefly what you took from
the rejection (tone too dark, too abstract, too small, whichever) and push the new set the other
way. Append every set to `00_seed.md` under `## Loglines`, labelled `Set 1`, `Set 2`, so the
rejected ones stay on record for the retrospective.

### When he picks

Record the chosen logline and its anchor under `## Chosen` in `00_seed.md`, log the gate in
`PIPELINE.md`, and advance to stage 2 in the same turn — the writers' room takes a while, so
start it immediately rather than making him type again.
