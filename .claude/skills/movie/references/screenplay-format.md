# The screenplay format contract

Read by: `script-writer`.

`01_script.md` contains **the screenplay and nothing else**. It is what Rajan reads. It is
formatted the way the industry formats a shooting script, so that anyone who has read a screenplay
before can read this one without being taught a local convention first.

## What belongs in the file

A title page block, then the screenplay. That is the whole file.

## What does NOT belong in the file — no exceptions

Everything below is real work that the pipeline genuinely needs. None of it goes in `01_script.md`.
It goes in `01_look.md`, the one-page look sheet written at the same gate, which is what gates 2, 3
and 4 inherit.

- Beat sheets, act-percentage tables, "why this beat" rationale
- `BINDING:` / `NOTE TO GATE n:` blocks, standing production notes, prompt hygiene, banned-word
  lists, negative prompts, agent names
- Colour scripts, lens language, aspect ratio, grade character, scale blocks
- Per-shot technical specs — focal length, camera height, colour temperature, generation notes
- Word counts, timing arithmetic proofs, tiling checks
- Scripture anchors, theme statements, intended-feeling statements

A screenplay does not explain itself. If a note is arguing with a future reader, it is not
screenplay — it is production paperwork, and it has a file.

## The title page

Plain, at the top of the file, before the first scene heading:

```
                              THE FIFTH STONE


                                 Written by
                             the Movie Workshop


                          30 seconds · three acts
                                2026-08-13
```

Working title until gate 5 replaces it. No logline, no anchor, no synopsis.

## Elements and their indentation

Wrap the screenplay in a single fenced code block so the fixed-width indentation survives. Columns
are counted from the left margin, and reproduce standard US screenplay geometry at 10 cpi.

| Element | Indent | Width | Case |
| --- | --- | --- | --- |
| Shot number / timecode rule | 0 / right to 56 | — | — |
| Scene heading (slugline) | 0 | 56 | UPPER |
| Action | 0 | 56 | Sentence |
| Transition | right to 56 | — | UPPER |
| Act heading | centred | — | UPPER |

One blank line between elements. Two before a new scene heading.

### Scene headings

`EXT. COOUM RIVER AT NAPIER BRIDGE - FIRST LIGHT`

`INT.` or `EXT.` (or `INT./EXT.`), the location, a hyphen, the time of day. Locations are named
consistently — the same place is spelled the same way every time it appears, because gate 2 turns
these into environment asset names.

`CONTINUOUS` is a claim about elapsed time and it must be true. Do not use it to mean "next".

### Shot numbers and timecodes

This is a shooting script for a film with a fixed running time, so every shot is numbered and
timed. The number sits at the left margin, the timecode at the right, on a rule line above the
scene heading:

```
1.                                                          0:00-0:05
```

Numbering runs 1..n across the whole film and never restarts. Timecodes are continuous and tile
0:00–0:30 exactly — no gaps, no overlaps. **These two numbers are the join between the screenplay
and every downstream gate.** They are the only production metadata that lives in the script, and
they earn their place because a timed shooting script is a real industry artifact.

The film is a single 30-second Seedance generation, so these timecodes carry straight through to
`script-prompt-engineer` unconverted — there is no node-local time to translate them into.

### Act headings

Centred, on their own line, with a blank line either side. Standard television convention:

```
                                 ACT TWO
```

Three of them, at 0:00, 0:06, and 0:24.

### Action

Present tense, third person. Only what a camera can photograph and a microphone can record. A
character's history, motive, or inner state is written only where a performance could carry it.

A character's name is in CAPS the first time they appear and normal case afterwards. Non-verbal
sound cues that matter — a roar, a bell, a crack of thunder — are in CAPS inline. Keep paragraphs
to four lines or fewer — white space is how a screenplay controls pace, and a wall of prose reads
as slow no matter what it describes.

Camera language is permitted where it is part of the telling, in the ordinary screenplay register:
`We PUSH IN`, `ANGLE ON`, `Her hand fills the frame`. It is not permitted as specification —
`47° standard normal, camera height 0.3m, 5600K` is a shot-list row and belongs in `01_look.md`.

### This is a wordless screenplay

No character cue, no parenthetical, no dialogue line, no voiceover, and no on-screen text appears
anywhere in `01_script.md`. Every beat is written as something a camera can show and a viewer can
feel without a single word — if a beat only works because a character explains it, restage it.
This is not a silent film, though: a non-verbal sound that matters still belongs in the action, in
CAPS, exactly as described above — that CAPS cue is what `script-prompt-engineer` carries forward
into the shot's `SFX:` line in the Seedance prompt.

### Transitions

`CUT TO:` right-aligned. Use sparingly — a cut between scene headings is assumed. `FADE IN:` opens
the script at the left margin; `FADE OUT.` closes it.

## Worked example

````markdown
```
1.                                                          0:00-0:05

EXT. COOUM RIVER AT NAPIER BRIDGE - FIRST LIGHT

Olive-green water under a slate sky. Hyacinth mats turning slowly.
Traffic crawls over the chequerboard arches.

The water DOMES. The mats slide apart.

A shoulder breaks the surface -- corrugated sheet metal lapped like
scales, bound with net and cable. It rises, and keeps rising. Sixty
metres of the city's own leavings, standing up out of the city's own
river. Its shoulders are rounded forward. Its head hangs.

It does not roar. It breathes once, and the sound is tired.


2.                                                          0:05-0:10

EXT. MARINA BEACH - FIRST LIGHT

Flat wet sand. A walker flicks a mango-yellow wrapper away without
looking.

Something comes across the sand after it -- a knot of pressed litter
the size of a football, trundling with somewhere to be. It goes over
the wrapper. The wrapper is gone.

A long-handled picker takes the wrapper straight back out of it.

RAJAN straightens up. Late thirties, lean, Corporation greens. Behind
him, a five-bin handcart. He is a man in the last hour of a night
shift.
```
````

## The rule that settles arguments

If a line in `01_script.md` is addressed to a downstream agent rather than to a reader of the film,
it is in the wrong file. Move it to `01_look.md` and leave the screenplay alone.
