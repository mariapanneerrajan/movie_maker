# Stage 5 — the six Seedance node prompts

Gate 5. Produces `<sandbox>/04_script_prompts.md`. This is the file Rajan actually works from.

## Run it

1. Spawn `seedance-prompt-engineer` with the sandbox path. It reads `01_script.md` and its visual
   bible, `ASSET_INDEX.md`, `STORYBOARD_INDEX.md`, the naming contract, and `craft-seedance.md`,
   then writes all six nodes.
2. Spawn `continuity-checker` on the result. It runs ten mechanical checks and returns `PASS` or
   `FAIL` with a timing table.
3. On `FAIL`, hand the failures back to `seedance-prompt-engineer` for correction, then re-run
   `continuity-checker`. Cap at three cycles — if it still fails, bring the specific failures to
   Rajan rather than looping.

Both foreground. Do not show Rajan the file until the checker passes; a broken reference name
costs him a wasted Seedance run.

## The structure, restated

Rajan pastes each node into Seedance by hand, six times. Per node: a `## References to connect`
list outside any fence, then a `## Prompt` section holding **one fenced code block** containing
the continuity block, the timed shot breakdown, and the ambient audio line — in that order.

The three rules most worth holding in mind while you review:

**Each node's timeline restarts at 0s.** Node 4 reads `0s–30s`, not `90s–120s`. Seedance has no
knowledge of what came before.

**The continuity block is byte-identical across all six nodes**, except the palette line and a
single "Continues directly from NODE n" line. That repetition is the only mechanism holding the
six nodes together as one film.

**Nothing addressed to Rajan may appear inside the fence.** One click copies the whole block into
Seedance; a stray note becomes part of the prompt.

## What to tell Rajan

- The timing table per node, so he can see the arithmetic
- The complete reference list per node — this is what he connects before each run
- Any beat the engineer restaged for Seedance's limits, with what changed and why. He should know
  where the prompts diverge from his script, even when the divergence is correct
- Anything the checker flagged under Seedance limits (compound moves, long dialogue lines, very
  short shots) that survived as an accepted risk

Then stop.

## Handling revisions

Log the request verbatim in `PIPELINE.md`, then:

- **One shot's wording** → edit directly in `04_script_prompts.md`.
- **A timing change** → the node must still tile 0→30s. Adjust the neighbouring shot to absorb the
  difference, then re-run `continuity-checker`.
- **Anything touching the continuity block** → apply it to **all six nodes** in the same pass.
  This is the easiest thing in the pipeline to get half-right.
- **A story or dialogue change** → the script is the source of truth. Fix `01_script.md` first,
  then propagate. Do not let the node prompts and the script disagree; every later stage and the
  next film's retrospective both read the script.

Re-run `continuity-checker` after any structural edit. It is cheap and it is the only thing
standing between a typo and six wasted generations.
