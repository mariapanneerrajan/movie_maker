# craft-seedance

Read by: seedance-prompt-engineer, continuity-checker. Read `CRAFT.md` first.

## Founding principles

### The arithmetic

Seedance 2.5 generates a maximum of **30 seconds per node**. A three-minute film is **six nodes**.
Each node's prompt describes **its own 30 seconds starting from 0s** — Seedance has no knowledge
of what came before, so node 4's timeline runs 0s–30s, not 90s–120s. This is the single most
common way these prompts go wrong.

### Continuity is carried by repetition, not by reference

Seedance cannot remember node 3 while generating node 4. Anything that must stay constant has to
be restated, verbatim, in every node. That is what the continuity block is for, and why it is
byte-identical across all six: style, palette, grade, aspect ratio, lighting character, and each
character's hard locks. Rewording it between nodes is how a film drifts.

The one permitted variation is a single "continues directly from NODE n, where …" line for nodes
2 through 6 — one sentence describing the exact state the previous node ended in, so the first
frame matches the last.

### Structure inside a node

1. **Continuity block** — everything repeated, first, so it frames what follows.
2. **Shot breakdown** — contiguous time ranges tiling 0s to 30s, no gaps, no overlaps.
3. **Ambient / global audio** — the bed running under the whole node, last.

Per-shot sound effects live **with their shot**, next to the timing. Only continuous ambience
goes at the end. A gunshot at 12s belongs at 12s; the sound of rain belongs at the bottom.

### Writing a shot

Each shot carries: its name from the script, the time range, the action, the emotional beat, the
camera (position, size, lens, one motivated move), the lighting, and any dialogue or SFX. Shot
names and emotional beats are lifted from `01_script.md` — never re-invented, because the script
is the source of truth and the storyboard was built from the same names.

Three to six shots per 30-second node is the workable range. Fewer and the node has no rhythm;
more and each shot has too few seconds for Seedance to resolve the motion.

### What these models do well and badly

- **Well:** slow single-intent camera moves, atmosphere, scale, creatures and machines in motion,
  environmental spectacle, one character performing one clear emotion.
- **Badly:** compound camera moves, more than two characters interacting precisely, hands doing
  fiddly work, readable on-screen text, exact lip-sync to long dialogue, and continuity of small
  props across a cut.
- **Consequence:** write toward the strengths. If a beat needs three characters in precise
  physical interaction, restage it so the camera sees one of them and infers the rest.

### On-screen text

Do not ask for it. These models render text unreliably and a misspelled word ruins a frame. The
continuity block should carry an explicit "no on-screen text, no subtitles, no signage lettering"
instruction. The one exception is the thumbnail, which is a still and a different pipeline.

### Dialogue and audio

Seedance 2.5 generates audio. Give it dialogue as a quoted line attributed to a character, kept
short — a line over about eight words begins to drift out of sync. Describe voice quality once in
the continuity block (age, timbre, accent, pace) so a character sounds the same in node 6 as in
node 1.

### The prompt is a copy-paste artifact

Rajan pastes each node's prompt into Seedance by hand, six times. It sits in a single fenced code
block so one click takes all of it. Nothing that is instruction-to-Rajan may appear inside the
fence — the reference list, the notes, and the commentary all live outside it.

### Reference images

Each node connects a set of reference images by name: the assets appearing in that node, plus
that node's storyboard panels. Keep the list tight — every asset that genuinely appears, and
nothing that does not. Names must match `naming.md` exactly and must resolve to real prompt files
in `02_assets/` and `03_storyboard/`.

---

## Lessons

*(none yet — the first retrospective will add here)*
