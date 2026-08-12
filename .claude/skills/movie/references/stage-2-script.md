# Stage 2 — the writers' room

Gate 2. This is the heart of the pipeline. Everything downstream treats `01_script.md` as the
source of truth, so it is worth the rounds.

Choreographed from the main thread. Your job here is orchestration and arbitration, not writing —
the agents write.

## The room

| Agent | Seat | Veto |
| --- | --- | --- |
| `head-writer` | Holds the pen | — |
| `scripture-guardian` | Biblical truth and doctrine | **Yes**, on `BLOCKING` |
| `fact-checker` | Real-world truth, internal coherence | **Yes**, on `BLOCKING` |
| `entertainment-doctor` | Is this a joy to watch | No |
| `cinematographer` | Visual language | No |

## The sequence

### 1. Draft

Spawn `head-writer` with: the sandbox path, the chosen logline and scripture anchor from
`00_seed.md`, and the intended audience feeling. Ask for the beat sheet and first-draft
screenplay. **Run it in the foreground** — everything else waits on it.

### 2. Round 1 — four reviewers in parallel

One message, four `Agent` calls. Give each the sandbox path and the draft screenplay inline (they
cannot see your conversation, and the draft is not on disk yet). Each returns its fixed findings
format.

Run these in the foreground together — you need all four before the next step, and nothing else
can usefully happen meanwhile.

### 3. Integrate

`SendMessage` to the **same `head-writer` instance** with all four note sets. Its draft context is
intact, which is why this is a message and not a fresh spawn. Ask for a revised screenplay plus
its response log (`ACCEPTED` / `DECLINED` per finding).

### 4. Round 2

Re-spawn `scripture-guardian` and `entertainment-doctor` on the revised draft. Re-spawn
`fact-checker` only if the revision introduced new real-world claims — otherwise its round-1 pass
still holds. Re-run `cinematographer` only if it returned `REVISE`.

### 5. Arbitrate

- All vetoes clear and no `REVISE` verdicts → proceed.
- Vetoes clear, `entertainment-doctor` still says `REVISE` → one more integrate-and-review cycle,
  then proceed regardless. Craft notes do not block indefinitely.
- A veto holder still returns `BLOCKING` after two integration rounds → **stop and bring it to
  Rajan.** Show the finding, the head writer's response, and your read of it. Do not write the
  script to disk, and do not quietly overrule a veto. This is his call.

Cap the whole room at **three integration rounds**. If it has not converged by then, the problem
is the logline, not the draft — say so and offer to return to gate 1.

### 6. Final visual pass

Spawn `cinematographer` in mode 2 with the approved draft. It returns the screenplay rewritten
with the **VISUAL BIBLE** block on top and camera, lens, and lighting baked into the action lines.
This pass is what makes stages 4 and 5 possible — without it, the storyboard artist and prompt
engineer each invent their own visual language and the film comes apart.

### 7. Write

Write `<sandbox>/01_script.md` — the visual-bible-inflected screenplay, with the header block
(logline, runtime, theme, scripture anchor, tone) above it and node markers throughout.

Write `<sandbox>/01_script_notes.md` — every reviewer's full findings from every round, the head
writer's response log, and any arbitration you made. This is the record the retrospective reads.

### 8. Stop

Report to Rajan in chat: the logline, the six beats one line each, the scripture anchor, notable
findings that changed the script, and anything a reviewer flagged that you overruled. Then stop
and let him read.

## Handling revision requests

When Rajan asks for a change ("the ending is too neat", "make Mira younger"), log it verbatim in
`PIPELINE.md`, then route it:

- **Story, structure, dialogue** → `SendMessage` to `head-writer` if the instance is still alive;
  otherwise spawn a fresh one with the current script.
- **Visual, lighting, camera** → `cinematographer`, mode 2, on the current script.
- **Small and unambiguous** (a name, a line, a beat's ordering) → just make the edit yourself. Do
  not spawn an agent to change one word.

After any story change touching theology or real-world claims, re-run the relevant veto holder
before rewriting the file. A revision can introduce a problem the first pass cleared.
