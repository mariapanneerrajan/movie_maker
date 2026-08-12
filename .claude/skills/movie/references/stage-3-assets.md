# Stage 3 — asset prompts

Gate 3. Produces `<sandbox>/02_assets/**`.

## Run it

Spawn `asset-designer` with the sandbox path. It reads the approved `01_script.md`,
`protagonist/RAJAN_NOTES.md`, the naming contract, and `craft-assets.md`, then writes one prompt
file per character, environment, and prop, plus `ASSET_INDEX.md`.

Foreground — the next gate depends on it and nothing else can proceed meanwhile.

## Check its work before showing Rajan

Once it reports, verify yourself — cheaply, with `Glob` and a few `Read`s:

1. **Coverage.** Cross-read `01_script.md` for characters, locations, and named props. Everything
   in the script has a file. Anything missing goes back to the agent.
2. **`CHR_RAJAN` exists and is an image-to-image restyle**, declaring
   `**Input image:** protagonist/RAJAN_RAW.png` and carrying the likeness locks from
   `RAJAN_NOTES.md`. This is the one asset that is the same job on every film, and the one most
   worth checking by hand.
3. **The neutral rule holds in every file** — grey #808080 seamless, flat even neutral lighting,
   no grade, no mood, no atmosphere, plus a `## Negative` section. Grep for `#808080` across
   `02_assets/`; every prompt file should hit.
4. **Names conform** to `references/naming.md`, and each file's `Output filename` matches its own
   basename.

## What to tell Rajan

He is about to generate these images by hand, one at a time, so give him the shape of the job:

- Count by type, and the full list of names grouped as characters / environments / props
- Which image model each is assigned to
- Any consolidation the agent made (one environment covering two times of day, one character
  sheet covering two costumes) and why
- Anything the script left ambiguous that the agent had to guess at — flag these explicitly
  rather than burying them, since they are what he most needs to correct now

Then stop.

## Handling revisions

Log the request verbatim in `PIPELINE.md`, then:

- **One asset's prompt is wrong** → edit that file directly. Do not re-run the whole stage.
- **An asset is missing, or one should be split or merged** → make the change, and update
  `ASSET_INDEX.md` in the same pass. If it affects several files, re-spawn `asset-designer` with
  the specific instruction.
- **A name is wrong** → fix it now, before any image exists. Rename the file, update the
  `Output filename` line, update the `# heading`, and update `ASSET_INDEX.md`. Names are contracts;
  the only safe time to change one is here.
- **The neutral rule was violated** → fix directly and note it for the retrospective, since that
  is a craft lesson worth keeping.

## Why the neutral rule matters enough to enforce twice

These images are reference inputs to Seedance, which supplies all lighting, grade, and mood. Mood
baked into an asset sheet fights Seedance in every shot that asset appears in — a character lit
with dramatic rim light on their sheet drags that rim light into the noon scene. It is the single
most consequential rule in this stage, and image models add drama unbidden, so it has to be stated
positively in the prompt *and* negatively in the exclusions.
