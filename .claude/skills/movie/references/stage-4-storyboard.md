# Stage 4 — storyboard prompts

Gate 4. Produces `<sandbox>/03_storyboard/**`.

## Run it

1. Spawn `storyboard-artist` with the sandbox path. It reads `01_script.md` (including the
   **VISUAL BIBLE** block), `ASSET_INDEX.md`, the naming contract, and `craft-visual.md`, then
   writes 12–18 panel files plus `STORYBOARD_INDEX.md`.
2. Spawn `cinematographer` in **mode 3** to review the panels against the visual bible.
3. If it returns `REVISE`, hand the findings back to `storyboard-artist` and have it correct the
   affected panels. One round is normally enough; cap at two.

Both foreground.

## Check before showing Rajan

- **Count and distribution.** 12–18 total, 2–3 per node, every node covered.
- **Names.** Strictly `SB_N<node>_<nn>`, numbered within their node from `01` in time order, never
  crossing nodes. Each file's `Output filename` matches its basename.
- **Asset references resolve.** Every name in a panel's `Assets in frame` exists as a file in
  `02_assets/`. Grep the panel files for `CHR_`, `ENV_`, `PRP_` and check each against
  `ASSET_INDEX.md`. A near-miss here becomes a broken node reference in stage 5.
- **Panels carry mood.** This is the inverse of stage 3 — if a panel prompt reads neutral and
  grey, the artist has confused the two rules. Panels are graded key frames.
- **The bookends rhyme.** `SB_N1_01` is the opening image; the last panel of node 6 is the closing
  image. They should echo each other — same place, same object, or same framing, changed meaning.

## What to tell Rajan

- Panel count per node and the full list of names in order
- A one-line description of each panel, so he can read the film's flow without opening 15 files
- Which image model each panel is assigned to
- Any beat the artist wanted a panel for but could not fit inside 18 — he decides whether to expand

Then stop.

## Handling revisions

Log the request verbatim in `PIPELINE.md`, then:

- **One panel is wrong** → edit that file directly.
- **A panel should be added, removed, or resequenced** → make the change and **renumber the whole
  node**, since panel numbers must stay contiguous within their node. Update
  `STORYBOARD_INDEX.md` in the same pass. Renumbering is safe here and only here — once Rajan has
  generated images, a renumber orphans his files.
- **The visual language is off across many panels** → the problem is upstream in the visual bible.
  Fix it in `01_script.md` first, then re-run `storyboard-artist` against the corrected bible.
  Patching panels one at a time against a wrong bible just moves the drift downstream.

## Why the visual bible is binding here

The storyboard artist and the prompt engineer both read the visual bible, and Seedance regenerates
the look from scratch six separate times. If the panels invent a second visual language alongside
the script's, the six nodes have two sources of truth to drift between, and they will. One bible,
stated once, obeyed everywhere.
