---
name: movie
description: Drives the end-to-end pipeline that builds every prompt needed for a 3-minute short film — seed idea, five loglines, writers'-room script, asset prompts, storyboard prompts, six Seedance node prompts, title, thumbnail, then ships the folder and harvests craft lessons. Invoked as /movie; auto-advances to the next unapproved gate. Use whenever Rajan is making a movie in this workspace.
---

# /movie — the short-film prompt pipeline

You are running a workshop that turns a seed idea into every prompt needed to generate a
3-minute short film with Seedance 2.5.

The pipeline has **eight gates**. It advances one gate per invocation, stops, and waits for
Rajan. He reviews everything; you never advance past a gate he has not approved.

## Every time you are invoked

1. **Read `c:\movie_maker\CLAUDE.md`** — the creative charter. It is law and it binds every string
   any agent in this pipeline writes, including strings destined for an image or video model.
2. **Read `c:\movie_maker\.claude\craft\CRAFT.md`** — the standing rules and the map of accumulated
   craft.
3. **Locate the sandbox.** `Glob` for `c:\movie_maker\sandbox_*`. If none exists, create
   `sandbox_one`. Ordinals in words: `sandbox_one`, `sandbox_two`, `sandbox_three`, `sandbox_four`,
   `sandbox_five`, `sandbox_six`, `sandbox_seven`, `sandbox_eight`, `sandbox_nine`, `sandbox_ten`.
   If several exist, use the highest — but say which one you picked, in case an old one was left
   behind.
4. **Read `<sandbox>/PIPELINE.md`** to find the last approved gate.
5. **Load only that stage's reference file** from `references/`. Do not read all of them.
6. **Run the stage, write its artifacts, stop, and ask for review.**

## The gates

| Gate | Stage | Reference file | Produces |
| --- | --- | --- | --- |
| 0 | Seed capture | `stage-1-ideas.md` | `00_seed.md` |
| 1 | Five loglines | `stage-1-ideas.md` | `00_seed.md` updated |
| 2 | Writers' room | `stage-2-script.md` | `01_script.md`, `01_script_notes.md` |
| 3 | Asset prompts | `stage-3-assets.md` | `02_assets/**` |
| 4 | Storyboard prompts | `stage-4-storyboard.md` | `03_storyboard/**` |
| 5 | Seedance nodes | `stage-5-nodes.md` | `04_script_prompts.md` |
| 6 | Five titles | `stage-6-7-title-thumb.md` | `05_title.md` |
| 7 | Thumbnail prompt | `stage-6-7-title-thumb.md` | `06_thumbnail.md` |
| 8 | Ship + retrospective | `stage-8-ship-retro.md` | `<Movie Title>/`, craft lessons |

Gates 0→1, 1→2, 6→7, and 7→8 chain within a single turn — a selection is an approval, and the
next stage should start immediately rather than making Rajan type again. The rest stop and wait.

`references/naming.md` is loaded by any stage that creates or references asset or panel names —
gates 3, 4, and 5.

## Reading Rajan's response

- **Approval** — "approved", "looks good", "yes", "go", "next" → log the gate and advance.
- **Selection** — "3", "idea 2", "use the second one" → record the choice, log the gate, advance.
- **Another set** — "give me 5 more", "none of these" → stay on the gate, generate fresh
  candidates. Applies at gates 1 and 6.
- **Revision** — anything describing a change → **stay on the gate**, make the change, show it,
  wait again. Route it per the stage reference file's revision section.

When it is genuinely unclear whether he is approving or asking for a change, ask. Advancing a gate
on a misread costs a whole stage of work built on the wrong foundation.

## PIPELINE.md

Created with the sandbox. The state file and the correction log.

```markdown
# PIPELINE

**Sandbox:** sandbox_one
**Started:** <YYYY-MM-DD>
**Working title:** <once known>
**Current gate:** 3

## Gate log

### Gate 0 — Seed captured — APPROVED <YYYY-MM-DD>
### Gate 1 — Logline selected — APPROVED <YYYY-MM-DD>
  Chose: <the logline>
  Corrections:
  - "<verbatim, exactly as Rajan wrote it>"
### Gate 2 — Script — IN PROGRESS
  Corrections:
  - "<verbatim>"
```

**Log every correction verbatim, as it happens, before acting on it.** Do not paraphrase and do
not summarise. That log is the raw material the retrospective reads to make the agents better next
film — a paraphrase loses exactly the signal it needs.

Update `Current gate` whenever you advance.

## The agents

Spawn via the `Agent` tool. They start cold — they cannot see this conversation — so pass the
sandbox path and any draft content inline.

| Agent | Used at |
| --- | --- |
| `head-writer` | Gate 2 — drafts and revises the screenplay |
| `scripture-guardian` | Gate 2 — **veto** on doctrinal error |
| `fact-checker` | Gate 2 — **veto** on real-world falsehood |
| `entertainment-doctor` | Gates 2, 6, 7 |
| `cinematographer` | Gates 2, 4, 7 |
| `asset-designer` | Gate 3 |
| `storyboard-artist` | Gate 4 |
| `seedance-prompt-engineer` | Gate 5 |
| `continuity-checker` | Gate 5 |

Run reviewer sets **in parallel in one message** — they are independent and you need all of them
before proceeding. Keep `head-writer` alive across revision rounds with `SendMessage` rather than
respawning; its draft context is the point.

Do not spawn an agent for a change you can make in one edit.

## Forcing a stage

`/movie script`, `/movie assets`, `/movie storyboard`, `/movie prompts`, `/movie title`,
`/movie thumbnail`, `/movie ship`, `/movie retro` re-run that stage regardless of gate state.
`/movie status` reports the current gate and what is done without running anything.

## What never changes

- **180 seconds, six nodes, 30 seconds each.** The arithmetic does not flex.
- **The script is the source of truth** once gate 2 is approved. No downstream stage invents
  story, dialogue, character, or world detail that is not in it. If something is missing, say so
  rather than filling the gap.
- **Names are contracts** — see `references/naming.md`. A name becomes a filename Rajan types by
  hand and a reference string in a Seedance node. Fix a wrong name at the gate that created it,
  never after an image exists.
- **`CHR_RAJAN` is the protagonist in every film**, always an image-to-image restyle of
  `protagonist/RAJAN_RAW.png`, keeping the same asset name whatever the character is called in
  the story.
- **Family audience, Biblical foundation, genuinely entertaining** — all three, in every prompt,
  every time.

## Starting fresh

If Rajan asks to start a new film while a sandbox already exists and is unshipped, ask before
creating a second one — an abandoned sandbox is usually a mistake, and shipping the current film
first is usually what he meant.
