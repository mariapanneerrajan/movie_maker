# Stages 6 and 7 — title and thumbnail

Gates 6 and 7. Produce `<sandbox>/05_title.md` and `<sandbox>/06_thumbnail.md`.

---

## Stage 6 — five titles

Run from the main thread. Read `01_script.md` — the header block, the scripture anchor, and the
visual bible — and `00_seed.md` for what Rajan wanted the audience to feel.

Generate **five candidate titles**. Spread them across registers rather than offering five
variations on one word:

- One drawn from a concrete object or image in the film
- One drawn from a line of dialogue
- One that names the theme obliquely
- One that is a short evocative phrase with no direct referent in the plot
- One that is a single strong word

### What makes a title work here

Intrigue without explaining. Survives being read in a crowded feed at small size. Easy to say
aloud. Promises what the film actually delivers — a title over-promising spectacle the film does
not contain costs the audience's trust, which is the opposite of this workshop's purpose.

Avoid: colons and subtitles, articles at the start unless they earn it, anything over four words,
and anything so abstract it could sit on any of these films.

Optionally spawn `entertainment-doctor` to rank the five before presenting — worth it when the
candidates feel close, skippable when one is obviously strongest.

### Present and stop

In chat, numbered 1 to 5. For each: the title in bold, then one line on what it promises and where
it comes from. Then stop — Rajan picks a number, or asks for five more.

If he asks for another five, note what the rejection implies and push the new set elsewhere.
Record every set in `05_title.md` under `Set 1`, `Set 2`, so the rejected ones survive for the
retrospective.

### When he picks

Write `<sandbox>/05_title.md` with all sets, the chosen title marked, and a note of the folder
name it implies for shipping. Log the gate and advance to stage 7 in the same turn.

---

## Stage 7 — the thumbnail prompt

Read `.claude/craft/craft-thumbnail.md` first — it holds the poster craft this stage runs on.

### Run it

Draft the prompt yourself in the main thread, then spawn `cinematographer` and
`entertainment-doctor` in parallel for an advisory pass — one judges the image, the other judges
whether anyone would click it. Integrate their notes.

### What the prompt must specify

- **16:9, 1920×1080 minimum.**
- **`CHR_RAJAN` prominent and recognisable** — large in frame, lit flatteringly, face turned
  enough to read as a person. Carry his likeness locks from the character sheet. This is the one
  place his face must be unmistakable at a glance, since he is the face of every film here.
- **The key story elements** — the creature, the machine, the world, whatever the film promises.
  Three clear depth planes: subject, mid-ground story element, vista behind.
- **The chosen title as designed type** — weight, case, era, material, and where it sits in frame.
  "Heavy condensed sans in weathered brass, all caps, lower right, integrated into the haze" is
  directable; "nice title text" is not. Title words only — no taglines, no channel name.
- **Fully graded and dramatic**, pushed beyond the film's own grade. Rim light separating the
  subject from the background. Strong value separation so the silhouette survives desaturation.
- Nothing under about 3% of frame width — small detail vanishes at 350px.

Note in the file that image models render text imperfectly: Rajan should expect a spot-correction
pass with Gemini Omni Flash, or to composite the title himself. The prompt still specifies the
treatment so the generated image leaves the right space for it.

### Write and stop

`<sandbox>/06_thumbnail.md` — the prompt, its negative clause, the image model, and
`**Output filename:** THUMBNAIL.png`. Present it in chat and stop.

Family audience applies here too. Eye-catching never means fear-baiting; the epic scale on offer
is plenty without it.

### When he approves

Gate 7 approval is the end of the creative work. Log it, then move straight into stage 8 — ship
and retrospective.
