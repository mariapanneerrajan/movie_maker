# CRAFT — the accumulated craft of this workshop

Every agent in this pipeline reads this file first, then its own craft file below.

These files are the memory of the agents. Subagents spawn cold — they cannot see the
conversation, and they cannot see session memory. **These files are the only way a lesson
learned on film one reaches an agent working on film two.** Treat them as binding.

## The craft files

| File | Who reads it |
| --- | --- |
| `craft-story.md` | head-writer, scripture-guardian, fact-checker, entertainment-doctor |
| `craft-visual.md` | cinematographer, storyboard-artist |
| `craft-assets.md` | asset-designer |
| `craft-seedance.md` | seedance-prompt-engineer, continuity-checker |
| `craft-thumbnail.md` | whoever drafts the thumbnail prompt |

## Standing rules — every agent, every film

1. **The charter is law.** Read `CLAUDE.md` at the repo root. Family audience, Biblical
   foundation, genuinely entertaining. These are not aspirations to balance against craft —
   they are the boundary inside which craft operates.
2. **The standards bind every string you write**, including strings destined for an image or
   video model. A prompt that would produce gore, dread, or sensuality violates the charter
   exactly as much as a script that describes it.
3. **The script is the source of truth.** Once `01_script.md` is approved, no downstream agent
   invents story, dialogue, character, or world detail that is not in it or directly implied by
   it. If the script is missing something you need, say so — do not quietly fill the gap.
4. **Names are contracts.** See `.claude/skills/movie/references/naming.md`. A name you invent
   becomes a filename Rajan types by hand and a reference string in a Seedance node. Never
   rename an existing asset.
5. **Three minutes is 180 seconds is six 30-second nodes.** Every stage is built around that
   arithmetic. It does not flex.

## How lessons get added

Only the retrospective (stage 8) writes to these files, and only after Rajan approves the
proposed lessons. Format, one line each:

```
- **[S-007]** When <trigger condition> → <the rule>. *(<film title>)*
```

The trigger must be concrete enough that an agent can recognise the situation. "Write better
dialogue" is not a lesson. "When a character states the theme aloud in the final beat → cut the
line and let the image carry it; Rajan removes these every time" is a lesson.

A new lesson that contradicts an existing one **replaces** it. Lessons do not stack into
sediment. If a file exceeds ~25 lessons, the retrospective consolidates before adding.
