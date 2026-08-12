# CLAUDE.md

## What this project is

A workspace for producing many **3-minute short films** made with AI image and video
generation models.

Each film lives in its own folder at the root of this project. A folder holds
everything for that one movie (script, shot list, prompts, reference images,
generated video, notes). Never mix assets between movie folders.

## Tooling

| Purpose | Model |
| --- | --- |
| Video generation (primary) | **Seedance 2.5** |
| Reference image generation | **GPT Image 2**, **Google Nano Banana** |
| Spot corrections / touch-ups | **Google Gemini Omni Flash**, sometimes **Seedance 2.5** itself |

Generated images are used as **reference inputs** to Seedance 2.5, not as final
deliverables. Corrections may be applied either to reference images or to already
generated video.

## Content standards

Everything written here applies to **scripts, story concepts, shot descriptions, and
every prompt sent to any model**.

**Family audience, always.**
- No gore, no blood, no gratuitous fear or horror.
- No sexual content, imagery, or innuendo.
- Creatures, monsters, and robots are welcome — rendered with the taste and warmth of a
  children's picture book, never with violence or dread.

**Biblical foundation.**
Every story carries a concept, idea, or teaching rooted in Scripture and Christian
faith:
- God created the world and everything in it, including humans.
- Humanity sinned and fell short of the glory of God.
- Jesus came in human form, lived a holy life, gave His life on the cross, shed His
  blood, and redeemed all humankind.
- On the third day He rose, and He is now in heaven.
- He sent the Holy Spirit to guide us into all truth.
- We believe in the Trinity, and in what God teaches through His Word, the Bible.

Stories should be *inspired by* the Word of God — the truth can be woven into the story
rather than preached.

**Genuinely entertaining.**
This is for a general audience, so the films must be a joy to watch:
- Rich visual effects and highly imaginative shots.
- Inventive worlds, characters, creatures, and robots.
- Any genre is open, as long as the two standards above hold.

The goal of every film: **inspire people, give hope and faith, and encourage a more
fulfilling and meaningful life.**

## Workflow

Run **`/movie`** to build every prompt a film needs. It advances one gate per invocation,
stops, and waits for review — approve, ask for another set, or ask for a change.

| Gate | Produces |
| --- | --- |
| 0–1 | Seed idea, then five one-line ideas to choose from |
| 2 | The screenplay, written by a head writer and reviewed by a room |
| 3 | Asset prompts — characters, environments, props |
| 4 | Storyboard panel prompts, 2–3 per node |
| 5 | The six Seedance node prompts, copy-paste ready |
| 6–7 | Five title candidates, then the thumbnail prompt |
| 8 | Ships the sandbox into the movie folder and harvests craft lessons |

Work in progress lives in `sandbox_one`, `sandbox_two`, … Only at gate 8 does it move into a
folder named for the film, and the sandbox is deleted.

The protagonist is **Rajan** in every film. His raw character sheet and persistent likeness
locks live in [protagonist/](protagonist/), and his asset is always named `CHR_RAJAN`.

Supporting structure, all under [.claude/](.claude/):

- **[agents/](.claude/agents/)** — the nine specialists. `scripture-guardian` and
  `fact-checker` hold vetoes; the rest advise.
- **[craft/](.claude/craft/)** — the workshop's accumulated craft. Every agent reads these
  before working, and the gate-8 retrospective writes lessons back into them. This is how the
  system gets better with each film.
- **[skills/movie/references/](.claude/skills/movie/references/)** — the per-stage
  choreography, plus `naming.md`, the naming contract that keeps prompt files, generated
  images, and Seedance reference lists pointing at each other.
