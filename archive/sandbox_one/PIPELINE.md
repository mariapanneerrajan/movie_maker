# PIPELINE

**Sandbox:** sandbox_one
**Started:** 2026-08-14
**Working title:** The Shrinking Giant
**Current gate:** 3

> Gate numbering shifted 2026-08-14: the keyframe stage was removed from the pipeline. Gate 3 is
> now the script/node prompt (was gate 4), gate 4 is the title (was 5), gate 5 is the thumbnail
> (was 6), gate 6 is ship (was 7). Gate 2 (assets) is unaffected and stays approved-pending as
> below.

> Restored 2026-08-14 from conversation history after a `/movie` bug reset this file to a fresh
> gate-0 stub. `00_ideas.md`, `01_script.md`, `01_look.md`, and `02_assets/**` survived untouched
> on disk throughout; only this state/log file was affected.

## Live agents

| Gate | Agent | Id |
| --- | --- | --- |
| 0 | idea-scout | a225c9a16a236bb8c |
| 1 | script-writer | abc157c0fbcef13a4 |
| 2 | asset-prompt-engineer | a780d8f202f3bef53 |
| 3 | script-prompt-engineer | a7aacafee937e182c (supersedes a3ba7550d80413e1b, retired — stale definition) |

## Gate log

### Gate 0 — Idea — APPROVED 2026-08-14
  Seed (verbatim, from Rajan):
  - "the seed idea for the film is that I want to tell the essence of the story of David versus Goliath, of how faith overcame fear. I want to tell this idea in the context of a sci-fi setting happening in the future on planet Earth. I want the battle to be between humans living in a utopian city vs monsters and strange creatures that are trying to take over the city. By watching this short movie, the audience should feel a sense of confidence that they can overcome any odds if they believe and have faith."
  Chose: #1, "The Shrinking Giant" — "A colossus grows on the city's fear; one unarmed engineer
  walks steadily toward it without flinching, until the giant starves down to a trembling creature
  small enough to hold in his palm." Rajan, verbatim: "yes, let us go ahead with idea number one,
  the shrinking giant."

### Gate 1 — Script — APPROVED 2026-08-14
  Corrections:
  - "I like the script. I just want to emphasize in the human side of Rajan: it shouldn't be as if he is infallible. He is doing this, afraid. It should be evident that he is choosing faith in the face of uncertainty and fear. That challenge that he is facing should be more evident in the script. It's good that we have a low point. I want that to be emphasized so that he himself is valuable. I like the way in which, when he falls and starts to become afraid, the entire city backs him up and they also are inspired to take on the giant. Just refine based on this feedback. And make sure the visuals get enough screen time. If needed, you can always make the story much simpler. The visuals should not be hurried because we want the emotions and the impact of the visuals to stick with the audience. The purpose is to inspire them, and they should carry this video. Whenever they are afraid of a giant or something overwhelming, just by watching this video, they should be inspired to move forward and take on and overcome. Refine the script based on the above feedback."
  Rajan, verbatim: "yes, this script looks good. Let's move on to the next step."

### Gate 2 — Assets — APPROVED 2026-08-14
  `02_assets/` fully populated: ASSET_INDEX.md plus CHR_RAJAN, CHR_COLOSSUS,
  CHR_COLOSSUS_PALM, CHR_CITY_CROWD, ENV_WHITE_CITY_PLAZA, ENV_WHITE_CITY_SKYLINE,
  PRP_BLAST_SHUTTER, PRP_FEAR_THREAD_BLUE, PRP_FEAR_THREAD_GOLD, PRP_RAJAN_GLASSES,
  PRP_TOOL_HARNESS.
  Corrections:
  - "I have updated the reference protagonist character sheet @protagonist/RAJAN_RAW.png so, based on it, I want you to recreate the prompts for the characters to be similar to the paneling and layout of this reference protagonist character sheet." — resolved: all four character sheets rebuilt to the new 3-panel layout (standing front/no head, standing back/head, close-up headshot; no height scale; no profile/3-4 view). Also caught and fixed: glasses lock corrected to fully rimless (was "near-rimless"), and PRP_RAJAN_GLASSES updated to match.
  - Rajan approved two follow-on one-line fixes: "yes, go ahead and make those fixes" — (1) 01_look.md "near-rimless" -> "fully rimless"; (2) RAJAN_NOTES.md posture lock "hands in trouser pockets" -> "arms relaxed at his sides", matching the new raw sheet. Both applied directly, no agent respawn needed.
  - "I want you to update the asset prompt engineer agent to not have the output file name mentioned as a .png file in each of the prompt files." — resolved: `.claude/agents/asset-prompt-engineer.md` template and all 11 sandbox_one/02_assets/**/*.md files updated to drop the .png extension from `**Output filename:**`. Flagged (not yet actioned): naming.md, keyframe-prompt-engineer.md, and thumbnail-prompt-engineer.md still use the old `.png` convention.
  - Also asked (answered, no file change): whether script-prompt-engineer references images via `@` in the prompt itself — it did not at the time.
  - "yes, I'll be connecting these references as input to the Seedance node. In the prompt itself, we can use the Add symbol to specifically mention the references that are connected... I want you to update the script-prompt-engineer.md to make use of the Add symbol to mention the references in the prompt itself along with the list of references that are already mentioned above, the prompt needs to be connected to the node." — resolved: `.claude/agents/script-prompt-engineer.md` updated — continuity block now has an `@`-tagged `References:` line, every shot must `@`-tag each connected asset at first mention, new hard rule + self-check (#12) enforcing the `@`-tags match `## References to connect` exactly. `.claude/skills/movie/SKILL.md` gate-4 instructions bumped from "eleven" to "twelve" self-checks. Applies going forward; nothing to retrofit yet since 04_script_prompt.md doesn't exist for this film.
  - "the Colossus character doesn't embody fear, and it is looking too childish and kind of friendly and not menacing. I needed it to be much more menacing and look like it is tormenting the city. It should look like a real monster, like a dinosaur and dragon, with big teeth, so that it can roar. This character doesn't even have a mouth. I need this monster to be a combination of a dinosaur and dragon. Refine the prompt so that we have a Colossus that looks a bit more menacing, and based on that, update the Colossus palm prompt as well." — routed to script-writer first since it touched the approved 01_look.md Cast Lock. Resolved: 01_look.md's Colossus lock rewritten as a theropod/dragon hybrid (claws, dorsal ridge, horns, wing-spars, real jaw with teeth); 01_script.md got 4 surgical line edits (shots 1, 2, 3, 5) so the screenplay's own description matches. New world rules: jaw opens exactly once (0:21, the roar), never frames open jaw + a person together, matte/carved-look negatives against gore/wet-gloss. CHR_COLOSSUS / CHR_COLOSSUS_PALM asset prompts not yet regenerated — waiting on the policy change below first.
  - "I want you to update the workflow and remove the clause where all the creatures need to look kiddish or from a children's picture book, because I want this to be like a blockbuster movie where we have real creatures... I don't want it to be like a horror film, but I definitely want real creatures and elements that are something that you would see in a blockbuster movie like Jurassic Park or Harry Potter and so on. So I want you to update the appropriate agents and the CLAUDE file to remember this." — resolved: CLAUDE.md's creature clause rewritten (blockbuster/cinematic register, e.g. Jurassic Park, Harry Potter — not children's-picture-book taste; still no gore/blood/horror/gratuitous dread). Same rewrite applied to the Standards sections of idea-scout.md, asset-prompt-engineer.md, keyframe-prompt-engineer.md, script-prompt-engineer.md, thumbnail-prompt-engineer.md, and the craft-constraint bullet + look-sheet guidance in script-writer.md. Added a dated Lesson to asset-prompt-engineer.md's `## Lessons` section documenting the specific failure mode (round heads/round eyes read as cute by default regardless of scale). Flagged and folded into the next script-writer round below: 01_look.md's Grade section for this film ("carved object... never a photoreal animal... cathedral gargoyle") was written just before this policy change and needs reconciling with the new blockbuster-realism direction.
  - "and I want the futuristic environment to be luscious, and I want it to be open. I don't want it to be like cement columns. Rather, there should be a lot of glass, and there should be a lot of greenery. The city itself should be like this utopian, thriving place you I want you to update the prompt for the environments according to this." — resolved together with the Grade-section reconciliation above. 01_look.md: Grade section rewritten to full photoreal blockbuster capture (safety now held by matte-surface + no-jump-scare staging rules, not by "carved object" restraint); THE WHITE CITY promoted to its own environment lock — glass towers, curtain walls, glass footbridges, vines/trees/moss/hanging gardens everywhere, planted water channels, columned/cement arcade explicitly banned. Colour conflict resolved: fear-thread is the film's only *emissive* colour, greenery its only *reflective* colour, so they never compete tonally — and the greenery now drains ash-grey through Act Two at the same rate the giant feeds, then returns with the gold wave in Act Three, strengthening the closing-rhyme structure. New world rule: the city is drained, never wrecked — no building damage anywhere. 01_script.md got 4 more surgical edits (shot 1's crane now descends past the towers/forests/footbridges before finding the crowd; shot 2's shutter now drops across a glass pavilion over water; shot 3 gained one new line — "Terrace by terrace, the green goes out of the city" — flagged as an addition, not a fix, cuttable if unwanted; shot 4 pays it off with "the green comes back up" behind the gold tide). Flag from script-writer: shot 1 is now the film's densest shot (crane must show the city AND find the crowd AND find Rajan in 6s) — if gate 3 storyboards it as rushed, the fix is dropping the footbridge line, not the crowd. CHR_COLOSSUS, CHR_COLOSSUS_PALM, ENV_WHITE_CITY_PLAZA, ENV_WHITE_CITY_SKYLINE asset prompts not yet regenerated to match — next step.
  Rajan, verbatim: "yes, let us go ahead and regenerate the asset prompts." — resolved: CHR_COLOSSUS,
  CHR_COLOSSUS_PALM, ENV_WHITE_CITY_PLAZA, ENV_WHITE_CITY_SKYLINE rewritten from scratch; knock-on
  fixes to PRP_BLAST_SHUTTER, PRP_FEAR_THREAD_BLUE/GOLD, ASSET_INDEX.md. Manager caught and fixed
  two regressions the live agent instance reintroduced from stale context: `.png` back on 7
  `Output filename:` lines (stripped again), and 01_look.md's glasses lock reverted to
  "near-rimless" by an earlier script-writer full-file rewrite (restored to "fully rimless").
  - "yes, keep the fourth open jaw panel, and yes, revisit the crowd wardrobe and
    also create an asset for the leaves to turn gray." — CHR_COLOSSUS's 4-panel layout confirmed,
    no action needed. Resolved: CHR_CITY_CROWD wardrobe rebuilt (low-chroma plant-dyed everyday
    cloth, out of both the emissive thread register and reflective foliage register); new asset
    ENV_WHITE_CITY_DRAINED created (plaza only, near-clone of ENV_WHITE_CITY_PLAZA differing only
    in foliage material state — naming rationale: this is a material change, not a lighting/
    time-of-day change, so it's exempt from naming.md's ban on splitting environments by time of
    day). 12 assets total now. Also fixed in passing: stray `.png` in ASSET_INDEX.md's CHR_RAJAN
    description. Confirmed stale/already-resolved: the "hands in trouser pockets" flag — fixed in
    RAJAN_NOTES.md several rounds ago, no longer an open item.
  - "similar to the city crowd, can we update the costume of the Rajan character as
    well?" — wardrobe-only change to CHR_RAJAN (build/face/hair/likeness untouched, per
    RAJAN_NOTES.md's "wardrobe is restyled per film, not a lock"). Resolved in 01_look.md: slate-blue
    tool harness (which fought the ice-blue fear-thread crossing the same chest) replaced with oiled
    walnut-brown leather-and-webbing; coveralls now faded-oatmeal raw-flax canvas with clay-brown
    patches; boots now oiled clay-brown leather. Separated from the crowd by *value* not hue (he's
    the lightest figure in a field of mid-tones — reads as "he stood up," not "he's special"). New
    load-bearing rule: harness straps leave sternum-to-collar clear so the fear-thread always lifts
    off bare cloth. Brass work lamp at the sternum kept unlit/unchanged (only light source in the
    closing shot). One script line touched (shot 1's wardrobe description). Flag: oatmeal against
    pale glass could wash him out in the Act Three wide — mitigated by depth separation in the lens
    language already, but if gate 3 finds him washing out, the fix is darkening the harness further,
    not greying the coverall.
  Recurring bug, now fixed at the source: the RAJAN glasses lock ("fully rimless") has reverted to
  the old wrong wording ("near-rimless") three separate times across this gate, each time
  script-writer rewrote 01_look.md from its own in-context memory instead of the current disk
  content, silently clobbering a manager-made direct fix in between. Fixed on disk again; also
  added an explicit "re-read before you write" instruction to script-writer.md for future films and
  messaged the live instance directly so it applies for the rest of this one too.
  Rajan, verbatim: "yes, update his wardrobe." — routed to asset-prompt-engineer to regenerate
  CHR_RAJAN.md.
  Rajan, verbatim: "alright, let's move on to the next stage, which is the script prompt."

### Gate 3 — Script/node prompt — IN PROGRESS
  First draft (agent a3ba7550d80413e1b) written and reported all-pass against the *old* 12-check
  version of script-prompt-engineer.md.
  Corrections:
  - "I want you to rerun the script-prompt-engineer because the prompt-engineer instruction has
    been updated. I want to regenerate the prompt using the latest script-prompt-engineer agent."
    — the agent definition changed since the first draft (learned from another film, "The Third
    Shaft"): References: block now needs a short one-liner per reference, not a bare @tag; header
    line changed from "CONTINUITY —" to "FILM — <title> — standalone, single generation,
    0:00–0:30"; self-check count went from 12 to 14. A resumed instance would keep its stale system
    prompt, so this needs a fresh spawn, not a SendMessage, to actually pick up the new rules.
    Resolved: fresh instance (a7aacafee937e182c) rewrote 03_script_prompt.md from scratch, 14/14
    self-checks pass. New shot timing: 0-6/6-15/15-20/20-24/24-28/28-30 (was 0-6/6-14/14-20/20-24/
    24-28/28-30 in the retired draft — shot 2/3 boundary moved from 14s to 15s).
