# CLAUDE.md

## What this project is

A workspace for producing many **30-second short films** made with AI image and video
generation models.

Each film lives in its own folder at the root of this project. A folder holds
everything for that one movie (script, shot list, prompts, reference images,
generated video, notes). Never mix assets between movie folders.

## Shape of a film

Every film in this workspace is **30 seconds**, generated as **one Seedance node**, and
structured in **three acts at 20 / 60 / 20**:

| Act | Job | Share | Window |
| --- | --- | --- | --- |
| One — Setup | The felt want or fear, in one wordless image | 20% | 0:00–0:06 |
| Two — Struggle | Escalation of feeling through image and action alone | 60% | 0:06–0:24 |
| Three — Resolution | Climax, then the closing image | 20% | 0:24–0:30 |

The beat clock inside that: a scroll-stopping hook by **0:02**, inciting incident at **0:06**,
the midpoint emotional turn near **0:15**, low point at **0:24**, climax **0:24–0:28**, closing
image **0:28–0:30**.

This arithmetic does not flex. Any stage that produces timings obeys it.

**Every film has no dialogue.** No spoken lines, no voiceover, no narration, no on-screen text —
the story lands through image and action alone. This is not a silent film: Seedance generates
real audio for every film — score, ambient sound, and sound effects — inferring ordinary
scene-appropriate audio on its own. Where a specific sound matters to the storytelling, it is
named explicitly in the prompt; everything else is left to Seedance.

**Every film is vertical, 9:16.** All generated video and the thumbnail render at 9:16,
1080×1920 minimum — a phone-first, vertical-feed format, with no per-film exception.

**Emotion is the vehicle; plot is the passenger.** Each film exists to transfer one feeling to
the viewer through epic, powerful imagery — which feeling is never fixed, it comes from that
film's own seed idea and Biblical anchor, different from film to film. Plot is subordinate to
that transfer: choose the incident that makes the feeling land hardest, not the one that makes
the most complete story. A viewer who rewatches the film should feel that transfer happen
again.

## Tooling

| Purpose | Model |
| --- | --- |
| Video generation (primary) | **Seedance 2.5** — 30 seconds, one node per film |
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
- Creatures, monsters, and robots are welcome, rendered with real cinematic weight — the scale
  and craft of a studio blockbuster, in the register of *Jurassic Park* or *Harry Potter*, not
  the soft taste of a children's picture book. Formidable, dangerous-looking, and spectacular is
  the target. This is not licence for horror: no gore, no blood, no splatter, no jump-scare
  staging, nothing played for dread rather than wonder.

**Biblical foundation, told in symbol.**
This workshop believes: God created the world and everything in it, including humans;
humanity sinned and fell short of the glory of God; Jesus, God's Son, came in human form,
gave His life on the cross, and rose on the third day to redeem humankind; the Holy Spirit
guides us into all truth; and we hold to the Trinity and to the Bible as the authority of
truth. That belief is why this workshop exists. The full mission is in
[VISION.md](VISION.md).

Every story is built from that belief the way C.S. Lewis built Narnia: a lion, not the
word "Christ"; a father who runs to meet the one who left, not the word "God"; a return
from somewhere no one returns from, not a resurrection sermon. The symbol carries the
truth, grand and imaginative and entertaining first — and it should welcome a viewer of
any faith, or none, to simply enjoy the story. A viewer who knows the Bible well should
feel something click. Neither experience should require the other.

What that means in every prompt: no literal *God*, *Jesus*, *the Bible*, *Christian*, or
*Scripture*, no chapter-and-verse citation, no real-world denomination or literal place of
worship. Reach instead for the symbol — a protector rendered as something magnificent, a
guiding presence, a costly rescue, a light that survives the dark, a return from the dead
that plays as wonder, not doctrine. That reach is the craft this workshop is built on.

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

`/movie` is a **manager**. Rajan talks only to it. It never does a stage's work itself; it hands
each stage to the one specialist that owns it, relays Rajan's notes back into that same
specialist, and reports what came back.

| Gate | Specialist | Produces |
| --- | --- | --- |
| 0 | `idea-scout` | Five one-line ideas to choose from |
| 1 | `script-writer` | `01_script.md` — the screenplay, in standard industry format — plus `01_look.md`, the one-page look sheet gates 2–4 inherit |
| 2 | `asset-prompt-engineer` | Asset prompts — characters, environments, props |
| 3 | `script-prompt-engineer` | The Seedance node prompt, copy-paste ready |
| 4 | `title-writer` | Five title candidates |
| 5 | `thumbnail-prompt-engineer` | The thumbnail prompt |
| 6 | `social-media-writer` | The promotional post — hook, sell copy, hashtags, and a platform title |
| 7 | the manager | Ships the sandbox into the movie folder |

Work in progress lives in `sandbox_one`, `sandbox_two`, … Only at gate 7 does it move into a
folder named for the film, and the sandbox is deleted.

A sandbox root holds **numbered deliverables only**, and `01_script.md` is a screenplay and
nothing else — no bindings, no colour script, no notes to other agents. Revisions overwrite in
place; git carries the history.

The protagonist is **Rajan** in every film. His raw character sheet and persistent likeness
locks live in [protagonist/](protagonist/), and his asset is always named `CHR_RAJAN`.

Supporting structure, all under [.claude/](.claude/):

- **[agents/](.claude/agents/)** — the seven specialists, one per stage. None holds a veto; Rajan
  is the reviewer. Each carries its own craft inline, ending in a `## Lessons` section that grows
  as films get made.
- **[skills/movie/](.claude/skills/movie/)** — `SKILL.md`, the manager, plus two contracts in
  `references/`: `naming.md`, which keeps prompt files, generated images, and Seedance reference
  lists pointing at each other, and `screenplay-format.md`.
- **[VISION.md](VISION.md)** — the project's mission statement in full: why these stories exist
  and how the symbol carries the truth.
