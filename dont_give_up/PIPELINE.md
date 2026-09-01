# PIPELINE

**Sandbox:** sandbox_two
**Started:** 2026-08-14
**Working title:** DON'T GIVE UP (chosen 2026-08-15; script header still reads "The Third Shaft")
**Current gate:** 7 — SHIPPED 2026-08-17

## Live agents

| Gate | Agent | Id |
| --- | --- | --- |
| 0 | idea-scout | a7801442c051e71da |
| 1 | script-writer | a2682e4a495958193 |
| 2 | asset-prompt-engineer | a74791a5d825e71c0 |
| 3 | script-prompt-engineer | a887afa09b825c734 |
| 4 | title-writer | a444bb45c62c9c50f (fresh spawn 2026-08-15; a12b327f2c98c55ff unresumable — session boundary) |
| 5 | thumbnail-prompt-engineer | a4c1819ea267546c2 |
| 6 | social-media-writer | abafde2bc5a057f52 |

## Gate log

### Gate 0 — Idea — APPROVED 2026-08-14
  Seed (verbatim): "I want to tell the essence of the story of Isaac and Rehoboth. In the
  Bible, we read how he was prosperous in a land, but everybody got jealous of him and asked
  him to go out of the land. He dug a well, and people came and argued with him, so he moved
  away from it. He dug a well again, and people came, and there was a bit of strife there as
  well, so he just moved again. Finally, the third time he dug a well, there was no argument
  or strife, and he named that place Rehoboth. ... The idea that I want to convey is: rebuild,
  persevere, and when you keep persevering, you will definitely find your place and you will
  prosper. ... I want the audience to feel encouraged, even if they had fallen down, to get
  back up again, to rebuild, to try again, and encourage them that when we don't give up, when
  we persevere, we will find our place and we will prosper."
  Chose: Idea #2, the desert tunneller — "Twice driven off the buried water-lines he digs, a
  desert tunneller bores beneath the one dune nobody claims — and a green river surfaces,
  racing across the sand faster than his rivals can plant flags." (per `00_ideas.md`, Set 1)

### Gate 1 — Script — APPROVED 2026-08-14
  Rajan: "looks good! Let's proceed to the next step." No corrections requested — approved
  as first drafted. `01_script.md` ("The Third Shaft") and `01_look.md` both complete.

### Gate 2 — Assets — IN PROGRESS
  Corrections:
  - "I want you to make sure that the Asset Prompt Engineer creates characters only with three
    panels, as shown in the Reference Protagonist Character Sheet: 1. The first panel should be
    the front view with the head hidden. 2. The second panel should be the back view. 3. The
    third panel should be the close-up. That's something that the Asset Prompt Engineer should
    have in its instruction. Can you ensure that it is added to the agent and the prompts for
    the characters are updated? As shown in the attached image, by using the prompt for the
    Rajan character, it generated seven poses, but it should have just created three panels."
    (Rajan attached the current CHR_RAJAN turnaround render showing 7 poses: 4-pose body row +
    3-pose headshot row, as the problem example.)
  - Applied: `.claude\agents\asset-prompt-engineer.md` updated — "Per-asset shape" now specifies
    exactly 3 panels per character sheet (front body/head cropped, back body, front close-up),
    plus a Lessons entry. All three character prompts in this sandbox (CHR_RAJAN,
    CHR_FLAG_RIDER, CHR_SAND_STRIDER) being regenerated to match via the live agent instance.
  - Done: all three character sheets rewritten to exactly 3 panels (front body/head cropped,
    back view, front close-up). CHR_RAJAN keeps its image-to-image restyle and likeness locks
    unchanged. CHR_SAND_STRIDER lost its mounted-rider view and foot-detail view to fit the
    3-panel lock — no asset now shows a rider seated on a strider, though shots 2-3 show them
    mounted. Flagged for Rajan. Lock applied to characters only, not props/environments, per
    his wording ("characters only with three panels").
  Rajan: "yes, let us move on to the next step to create the keyframes." — APPROVED 2026-08-14,
  as revised (3-panel character sheets, mounted-rider pairing left dropped).

  Note: the keyframe stage was retired from the pipeline on 2026-08-14, after this gate had
  begun work under it. That in-progress work is discarded; the sandbox advances directly to
  `script-prompt-engineer` (gate 3 under the current numbering).

  Reopened 2026-08-14, environments only. Rajan: "I noticed that environment assets seem to have
  two views of the same environment in the same image. I want each environment view to be its
  own image, so update the asset-prompt-engineer to create a prompt for each single environment
  view as a respect to the image. And even now, I want just the environment prompts to be
  recreated, having one view per image, and name it appropriately. And once that is done, I want
  the script prompt to also be updated with the latest names"
  Applied: `.claude\agents\asset-prompt-engineer.md` updated — environments now follow the same
  one-view-per-image rule characters already have; "provide two views on one sheet" is gone.
  Every distinct view a space's shots require gets its own file, named `ENV_<PLACE>_<VIEW>` per
  `naming.md`. Added to self-checks and Lessons. The three existing `ENV_*` files (characters and
  props untouched) being recreated via the live agent instance, re-deriving the correct view
  count per environment from the shots rather than assuming two.
  Done: three combined sheets became seven single-view assets — `ENV_SUNKEN_FLATS_OVERHEAD`,
  `ENV_SUNKEN_FLATS_RIDGE`, `ENV_FAR_DUNE_FIELD_SLOPE`, `ENV_FAR_DUNE_FIELD_HORIZON`,
  `ENV_BLACK_DUNE_DISTANT`, `ENV_BLACK_DUNE_SUMMIT`, `ENV_BLACK_DUNE_OVERHEAD`. Re-derivation
  (not a mechanical split) found real gaps the old 2-view sheets missed: shot 6 (overhead on the
  black dune) had no reference at all, shot 3 actually needs three distinct framings not one, and
  the snapped-pole ring was missing from the summit view despite the look sheet requiring it in
  shots 3 and 4. `ASSET_INDEX.md` updated with a shot-to-environment map. The agent's toolset has
  no delete — I removed the three superseded stub files (`ENV_SUNKEN_FLATS.md`,
  `ENV_FAR_DUNE_FIELD.md`, `ENV_BLACK_DUNE.md`) from disk myself and verified `03_script_prompt.md`
  still exists (the agent's report incorrectly claimed gate 3 hadn't run yet — verified false by
  direct file listing; noted here in case this recurs). Sending the new names to
  script-prompt-engineer next, per Rajan's request.
  Done: `03_script_prompt.md` now connects 15 references (was 11) — the 3 old ENV_* names fully
  replaced by the 7 new ones, shot 3 now carries 3 environment tags across its single camera arc,
  shot 6 gained a sourced reference for the shot-1/shot-6 overhead rhyme it previously lacked.
  Verified directly (grep) that no bare old ENV_SUNKEN_FLATS/ENV_FAR_DUNE_FIELD/ENV_BLACK_DUNE
  name remains anywhere in the file. Full 14-point self-check re-run, all PASS.
  - Rajan asked whether the film could generate at 16:9 instead of 9:16. Manager's analysis:
    shots 1/3/4/5/6 survive or improve; shot 2 is the one genuinely vertical composition (ridge
    filling frame height) needing restaging; the env references are framed 9:16; CLAUDE.md's
    no-exception 9:16 rule flagged as his to waive. Decision, verbatim: "Keep the environment
    prompts as it is. Only refine the script prompt so that it works well with a 16:9 aspect
    ratio."
  - Applied: 16:9 conversion of `03_script_prompt.md` requested from the live script-prompt
    agent — aspect line, shot 2 restaged for width rather than height, any other vertical-frame
    phrasing swept. Environment prompts deliberately left 9:16 per Rajan's instruction. This is
    a this-film decision, not a pipeline change: agent definitions and CLAUDE.md stay 9:16.
  - Done: `03_script_prompt.md` reframed to 16:9. Aspect line changed; new `Composition rule:`
    line added (scale carried by breadth, edge-to-edge ridges/rider-lines/flag-chains/river,
    never cropped tight — the 16:9 substitute for the look sheet's vertical-stacking rule).
    Shot 2 fully restaged for width: ridge runs edge to edge behind him, rider line fills the
    crest, poles march across the frame; camera push now makes the rider line spread past both
    edges while he stays one small centred figure. Shots 1/4/5/6 got width touches; shot 3
    genuinely improves. Trades flagged by the agent: (1) shot 2 loses its towering-loom (width
    gives outnumbered, not loomed-over) — the single real loss; (2) the above-vs-below lighting
    axis is less physically felt in a wide shallow frame; (3) the tiny-figure payoff at 0:29
    reads smaller relative to frame width. Full 14-point self-check re-run, all PASS.
    Standing note for gate 5: the thumbnail prompt must be told this film ships 16:9 — 01_look.md
    ("9:16 throughout") and CLAUDE.md were deliberately not edited.
  - "update the script prompt such that it is less than 4000 characters in length."
  - Applied: fenced prompt measured at 12,277 chars (whole file 14,749). Compression to <4,000
    chars of the fenced block requested from the live agent, preserving timings, act tags,
    reference tags, the two prohibition lines, and the emotional beats.
  - Done: fenced block now 3,804 chars (manager-verified by direct measurement; agent reported
    ~3,774). Survived: all timings/act tags/boundaries, all 15 @-tags, 16:9, three palette
    states, shot-5 light reversal, shot-1/6 rhyme, breadth rule, drift locks, prohibitions (as
    one merged line), all CAPS cues. Cut: scene-heading shot titles, per-shot Light: lines
    (except "riders backlit" in shot 2), within-shot second-by-second timestamps, wardrobe/
    appearance prose, world rules trimmed to three. Four beats paraphrased, none changed in
    meaning. Agent's honest-trade warning: grade, per-shot lighting, and within-shot pacing are
    now the three drift risks; cheapest repair if the first render drifts is re-adding ~40-char
    per-shot Light: clauses.
  - "It looks like Eleven labs, the platform that we are using to do the video generations
    through Seedance 2.5, right now it takes in prompts that are less than 4,000 characters
    only. ... Later on, when I switch to another platform, I am thinking of Higgs field. At that
    time, we might have a bigger limit ... but as of now, remember to create the script which is
    less than 4,000 characters in length."
  - Applied: `.claude\agents\script-prompt-engineer.md` — the <4,000-char fenced prompt is now a
    hard rule (with the ElevenLabs platform context and the possible future Higgsfield change
    noted), self-check #20 (measure, don't estimate, report the number), check #7 softened to
    budget-aware verbatim, and a Lessons entry. `SKILL.md` gate-3 count updated to twenty. No
    regeneration needed — current prompt already measures 3,804.
  Rajan: "alright, let's move on to the next gate." — APPROVED 2026-08-15. Final form: 16:9,
  fenced block 3,804 chars, 15 references with folded drift locks, FILM header.

### Gate 4 — Title — IN PROGRESS
  Corrections:
  (paused 2026-08-15 — Rajan reopened story/assets/prompt before selecting a title; Set 1
  stands, no titles rejected)
  Note 2026-08-15: further work on `03_script_prompt.md` happened outside this conversation's
  log — the file on disk now carries 18 references (new: `ENV_BLACK_DUNE_SUMMIT_DAWN`, used by
  shot 5, meaning the dawn finale was chosen), plus a moderation-safety wording pass (sweep →
  "passes close / tumbles", SCREAMS → GRINDS, SHRIEKS → SQUEALS, "never monstrous" → "warm,
  animal in shape", "no face" → "features hidden", etc.) with fallback candidates listed in the
  file's notes after an apparent platform rejection. Treat the on-disk file as current.
  Resumed 2026-08-15: Rajan said "all right, let's move on to the next gate" — gate 4 needs his
  title selection; Set 1 re-presented with a note that two rationales weakened after the
  flag-free ending.
  - Rajan: "what about the title 'Don't Give Up'? Can you give me some suggestions similar to
    this?" — Set 1 not selected (not formally rejected either); Set 2 requested in the direct
    encouragement/imperative register around his candidate "Don't Give Up".
  - Set 2 delivered (fresh title-writer spawn a444bb45c62c9c50f): Don't Give Up / Keep Digging /
    One More Turn / They Can't Bury Water / Your Ground Is Waiting / It's Still Down There.
    Writer recommended Keep Digging.
  Rajan: "let's go with 'don't give up'." — APPROVED 2026-08-15. Title: DON'T GIVE UP.
  Chained into gate 5.

### Gate 5 — Thumbnail — IN PROGRESS
  Corrections:
  - Delivered first draft (`05_thumbnail.md`): shot-6 finale image — soaked, laughing Rajan,
    arms wide, water column behind, green-gold from below + dawn rim — with the one deliberate
    change of camera (35mm low three-quarter waist-up instead of the film's top-down, so the
    face reads and the likeness locks apply). Title band: DON'T GIVE UP, heavy wide grotesque,
    cream-white, lower band. 16:9 1920x1080 per the film's format exception — DEVIATES from
    the charter's 9:16 thumbnail rule; surfaced to Rajan. Engineer notes: expect the
    apostrophe in DON'T to need a spot-correction/composite pass; grimace-instead-of-laugh is
    a re-roll not a prompt fix.
  - "for the thumbnail can you mention all the references that I need to plug in as input to
    the image generation model, and below the title I always want to have a subtitle that says
    'AI short film' Update the thumbnail prompt engineer to have this instruction."
  - Applied: `.claude\agents\thumbnail-prompt-engineer.md` updated permanently — (1) new
    "References to connect" section: thumbnail prompt files now carry the connect list plus
    @-tagged References: block inside the fence, same convention as script-prompt-engineer;
    CHR_RAJAN always connected, otherwise only assets genuinely in frame; ASSET_INDEX.md added
    to its reading list; (2) fixed subtitle "AI short film" directly below the title on every
    thumbnail, subordinate type, a standing disclosure not a per-film choice. Self-checks
    updated (also generalized the 9:16 check to honour a look-sheet format exception).
    `05_thumbnail.md` being revised via the live agent instance.
  - Done: connect list = CHR_RAJAN + ENV_BLACK_DUNE_WATER_BURST + ENV_BLACK_DUNE_SUMMIT (not
    OVERHEAD — top-down geometry fights the low-angle poster; no props in frame). Subtitle "AI
    short film" centred below the title, same grotesque, 1/5 cap height, light, letterspaced,
    no bevel — caption not object. Caution logged: ENV_BLACK_DUNE_SUMMIT's reference includes
    the snapped-pole ring the look sheet bars from the finale imagery; negative clause guards
    it, but pole stumps on the horizon in a render = that reference leaking, fix by re-roll.
    Lettering: apostrophe in DON'T and the small light subtitle are the two expected garble
    points — subtitle is a platform disclosure so must be verified legible before publishing;
    composite drop-in space reserved.
  Rajan: "okay, let's go to the next gate." — APPROVED 2026-08-15. Final form: rain-joy
  low-angle poster, 3 references connected, DON'T GIVE UP + "AI short film" subtitle, 16:9.

### Gate 6 — Social post — IN PROGRESS
  Corrections:
  - "I want to keep the social media posts a bit more concise. I just want to say something
    like, using AI, I created a short film called 'Don't Give Up.' Hope it inspires you to
    persevere, even in the face of adversity."
  - Done: post rewritten as a personal first-person note (Rajan's draft lightly polished + one
    cuttable descriptive middle clause: "thirty seconds, no dialogue — a man digging for water
    in the desert, losing it, and going again"). Platform title changed to "DON'T GIVE UP — a
    30-second AI short film" (the punchy "They Took His Water Twice" line dropped as a register
    mismatch with the humble body; recoverable on request). Hashtags 9 → 4: #dontgiveup
    #shortfilm #aishortfilm #perseverance. Two emoji (desert, water). AI disclosure in his own
    opening words. Banned words absent.
  Rajan: "All right, go move on to the next gate." — APPROVED 2026-08-15.

### Gate 7 — Ship — IN PROGRESS
  Awaiting Rajan's confirmation of the destination folder name/path before moving anything.
  - Rajan (verbatim): "Always use lower camel case naming convention for folder names. For
    example, here the name should be dont_give_up . Update the appropriate AI agent to remember
    this instruction." (His example is snake_case; the example is treated as the authority.)
  - Applied: SKILL.md gate-7 instruction updated — film folder names are lowercase snake_case
    derived from the title, punctuation dropped (DON'T GIVE UP → dont_give_up), as a standing
    convention. Shipped 2026-08-17 to c:\movie_maker\dont_give_up\ — all files verified arrived, sandbox_two deleted. GATE 7 COMPLETE; film shipped.

### Gates 1-3 reopened — 2026-08-15, after first video generation
  Rajan (verbatim): "I want to refine the script prompt. In the beginning, when there's this
  burst of sand coming out of the hole, and then at the end of the movie we see a burst of
  water springing out, those two scenes are very important for the movie. I want it to be much
  more emphasized if needed. Shall we also create a couple of reference images to convey the
  power of the water bursting out and also the sand coming in at the beginning and then water
  bursting at the end? Now, based on this prompt in the video that I generated, I was able to
  see that yes, the bad guys come and take over the first well that he opens up, but the second
  one, they don't seem to be coming to close it up. It should be very evident at least these
  two times: the first and the second time. The bad guys, the sand striders with the flag
  rider, should come and close up the well. Maybe the second time, make the flag rider even
  push Rajan to the ground and close the well, because that's very important for the story. I
  want to visually emphasize the burst of sand and then water coming in the beginning, and also
  the burst of sand and water coming at the end. That should be emphasized."
  Manager's read: (a) story change — the second dispossession must be explicit on screen,
  including a rider pushing Rajan to the ground, which overrides the look sheet's
  "nobody ever touches him" world rule (Rajan's explicit call); script is source of truth, so
  script-writer revises 01_script.md/01_look.md first. (b) New reference images for the opening
  sand burst and closing water burst — asset-prompt-engineer, after the script lands.
  (c) script-prompt-engineer then updates the node prompt: emphasized bursts, new shot-3
  staging, new references, still 16:9 and <4,000 chars. Executing in that order.
  - Done (a): script revised. Shot 3 expanded to 0:11-0:18 (7s): striders thunder down, lead
    rider's pole sweep puts Rajan flat in passing, pole planted, burial watched from the
    ground, "He pushes his glasses straight. He gets up." Both bursts now set-pieces (10-storey
    sand column w/ shockwave ring + brown rain reveal; water column taller, sunlit, rainbowed).
    Shot 2 now 0:06-0:11, shot 5 0:24-0:27, shot 6 0:27-0:30. Boundaries 0:06/0:24 intact.
    Look sheet world rule now "the only contact in the film is that one push"; 16:9 recorded as
    per-film exception in a new Format block; writer also self-corrected a chapter-and-verse
    citation out of the look sheet anchor. Writer's flagged risk: shot 3 carries 6 actions in
    7s; trim candidate if render struggles is "He is almost smiling."
  - Rajan: "have you updated the script prompt?" — read as approval of the revised script and
    go-ahead for the cascade; (b) assets and (c) prompt executing now.
  - Done (b): two burst assets created — ENV_SUNKEN_FLATS_SAND_BURST (base:
    ENV_SUNKEN_FLATS_OVERHEAD; shot 1, 0:00-0:03) and ENV_BLACK_DUNE_WATER_BURST (base:
    ENV_BLACK_DUNE_OVERHEAD; also-connect the sand burst so the two match and the water reads
    taller; shot 6, 0:27-0:29, plus material reference for shot 5). Both framed 16:9, eruption
    frozen sharp (no motion blur) so structure reads. No third asset for shot 5's close
    eruption — judged covered by CHR_RAJAN + water burst material; easy to add if a render
    under-delivers. Sun/rainbows deliberately NOT baked into the references (Seedance's job).
    ASSET_INDEX.md updated: 17 assets, 6 base chains, new shot-to-environment map. OPEN
    DECISION flagged by the agent: the two overhead bases are still written 9:16 while their
    burst variations are 16:9 — recommendation is to regenerate just those two prompts at 16:9
    since the shot-1/shot-6 rhyme depends on them; awaiting Rajan.
  - Done (c): `03_script_prompt.md` rebuilt against revised script + 17 references. New
    timings (0-6-11-18-24-27-30), both bursts staged as state not build ("already erupting"),
    shot 3's shove staged as one continuous pass (no two-body struggle). Manager-measured
    fenced block: 3,995 chars — under the limit but only by 5; agent's own estimate was ~3,915
    (regex bucketing, no shell available to it). Self-checks: 18 PASS, #7 FLEX (paraphrases
    listed in file), #16 deliberate FAIL — the per-shot Blocking: line didn't survive the
    budget; placement carried inline in action lines instead; restoring costs ~80 chars.
    ENV_*/PRP_* one-liners now 2-4 words (below the 5-15 guidance) to afford the bursts.
  - Rajan (verbatim): "in the final burst, I don't want any flags to be seen. Because basically
    what we are conveying is that, at the end, there are no enemies coming to capture what
    Rajan has got. And when the water bursts the final time, it is a night scene do we need a
    reference for the water bursting and the environment in the night scene, or will Seedance
    be able to take care of it?"
  - Applied: script-writer revising shot 6 to remove the flag chain from the ending (river
    runs free, no claim markers, no enemies anywhere in the frame). Manager's answer on the
    night reference: none needed — references are deliberately time-of-day-neutral and
    Seedance supplies lighting from the prompt. Flagged to Rajan: as scripted the final burst
    is FIRST LIGHT/dawn (sunlit, rainbows, Act One orange restored), not night — awaiting his
    call on whether to relight shot 6 as night or keep dawn.
  - Done (script): shot 6 rewritten — flag beat replaced with "Open land, edge to edge. The
    water is the only thing moving on it." Shots 1-5 byte-identical, timecodes unchanged. Look
    sheet updated in 4 places (anchor, feeling, bursts bullet, new world rule "The last ground
    is uncontested and stays uncontested"); snapped-pole ring hardened to shots 3-4 only;
    crimson exits the film at 0:18. Cost noted by writer: the grace-to-the-takers note is gone
    — ending is now possession without threat, matching Rajan's stated intent. Manager updated
    PRP_BANNER_POLE shots to "2, 3" (file + index) and the index shot-6 map row. Node prompt
    rebuild for the new ending sent to script-prompt-engineer; night/dawn still open with
    Rajan (script-writer notes: if night is chosen, the strong version lights the column from
    inside with the green-gold rising from the hole, keeping grace-from-below).
  - Rajan (verbatim): "also, I do not want any grass to be growing. Just the water gushing out
    in an epic manner and raining on a joyful Rajan would be powerful imagery."
  - Applied: script-writer sweeping all grass/reed/bloom growth from 01_script.md and
    01_look.md (shot 3's banks, shot 6's banks, the living-bloom world rule); the jade-green
    water itself stays the film's life image; ending re-centred on the epic column and its rain
    falling on a joyful Rajan. Node prompt to follow once the current shot-6 rebuild lands.
  - Done (script): 6-hit sweep — shot 3 grass → "cutting its own channel downhill, widening";
    shot 6 grass line deleted; world rule replaced with hard exclusion "Nothing grows anywhere
    in this film" (abundance = volume/speed/height/noise of water only); colour script now
    "every green in this film is water, never plant life"; anchor "sows" → "opens"; the word
    "bloom" purged from both files. New escalation rule: thread at 0:05 → ribbon at 0:13 →
    column+river at 0:27, measured in water alone. Shot 6 ending rewritten: rain falls on
    Rajan, soaked, head back, arms wide, turning slowly, laughing (joy built from body for the
    top-down); river demoted to one clause; last line "The column keeps climbing." Shot 5
    gained "His face comes up into it. Open, streaming, lifted." (Writer flagged: that phrase
    had existed only in an agent report, never on disk — now written in.) Shots 1/2/4
    byte-identical; timecodes, sluglines, flag removal, banned words all hold.
  - Done (prompt): shots 3/5/6 rebuilt grass-free with the rain-on-Rajan ending ("soaked, head
    back, arms wide, turning slowly under it, laughing. The column keeps climbing."). Manager-
    verified: fenced block 3,939 chars (61 margin); zero growth words anywhere in fence; zero
    flag/pole/rider/strider words in shots 5-6. Checks: 18 PASS, #7 FLEX (paraphrases listed),
    #16 deliberate FAIL (no separate Blocking: lines — placement inline). Agent's note: shot 6
    carries three elements in 3s (column, river clause, rain-on-Rajan); if a render feels
    crowded, cut the river clause (~75 chars back). Night/dawn finale still open with Rajan.

  Reopened again 2026-08-15. Rajan: "also, I want to give another instruction to the asset
  prompt engineer. Now, whenever there is an asset that is a variation of a base asset, it needs
  to be mentioned above the prompt (because in that way, when I generate the variation of the
  base asset, I can connect the base asset as reference). Update this instruction to the Asset
  Prompt Engineer and check if there are any such dependencies in the environment asset prompts.
  If so, kindly add it before the actual prompt."
  Applied: `.claude\agents\asset-prompt-engineer.md` updated — every variation asset now carries
  a `**Base asset:**` line above its `## Prompt` block naming what it varies from, so Rajan can
  connect the base's generated image when generating the variation; standalone assets omit the
  line; ASSET_INDEX.md gains a base-asset column; added to self-checks. Live agent instance
  checking the seven environment prompts for such dependencies and adding the line where found.
  Done: six files gained `**Base asset:**` — ENV_SUNKEN_FLATS_OVERHEAD ← ENV_SUNKEN_FLATS_RIDGE,
  ENV_FAR_DUNE_FIELD_HORIZON ← ENV_FAR_DUNE_FIELD_SLOPE, ENV_BLACK_DUNE_SUMMIT ←
  ENV_BLACK_DUNE_DISTANT, ENV_BLACK_DUNE_OVERHEAD ← ENV_SUNKEN_FLATS_OVERHEAD (geometry anchor
  for the shot-1/shot-6 rhyme, plus an `**Also connect:**` line for ENV_BLACK_DUNE_SUMMIT's grit
  colour), PRP_SNAPPED_POLES ← PRP_BANNER_POLE, PRP_BROKEN_AUGER_SHAFT ← PRP_BORE_RIG. Each
  variation prompt now describes itself relative to its base image rather than from scratch.
  Judged NOT dependencies: ENV_BLACK_DUNE_DISTANT vs FAR_DUNE_FIELD_HORIZON (opposite subjects),
  cross-place same-sand pairings (would chain all seven to one root), rider vs strider (two
  designs, not variations). ASSET_INDEX.md gained a Base asset column and a generation-order
  section listing the five chains. (Manager fixed two regressions the index rewrite reintroduced:
  "keyframe engineer" wording and the deleted-stubs note.)

### Gate 3 — Script prompt — IN PROGRESS
  Corrections:
  - "on the script prompt, it's good that we are mentioning all the different references that
    are associated with this prompt with the ad symbol. I want to have a small one-line
    description of what that reference is, so that the video model will have more context
    explicitly. Make that update now."
  - Applied: `.claude\agents\script-prompt-engineer.md` updated — the `References:` block inside
    the fenced prompt is now multi-line, one `@NAME — one-line description` per reference,
    description pulled from `ASSET_INDEX.md` so wording stays consistent with the index. Added
    as self-check #13 (now thirteen checks total); `SKILL.md` gate-3 instruction updated to
    match. `03_script_prompt.md` in this sandbox being regenerated via the live agent instance.
  - Done: `03_script_prompt.md`'s `References:` block rewritten to 11 one-liners, one per name,
    pulled from `ASSET_INDEX.md`. Everything else in the file unchanged. Full 13-point self-check
    re-run, all PASS.
  - "I'm noting that the script is starting with some sort of a continuity text. Why is that
    happening? This is just a standalone video generation. It doesn't continue from something
    else. Can you proofread the entire script once again, because I can see that at least the
    references are getting mentioned more than one time with a description?"
  - Applied: `.claude\agents\script-prompt-engineer.md` updated — the prompt's opening line is
    now `FILM — <title> — standalone, single generation, 0:00-0:30` instead of `CONTINUITY —
    <title>`, since that label could read as pointing to footage outside the prompt. Also fixed
    the actual duplication Rajan spotted: `CHR_*` entries in `References:` were repeating the
    same appearance detail already in `Characters:` below; `References:` now gives characters a
    short role/identity tag only, while `ENV_*`/`PRP_*` keep their full one-liner (their only
    description in the prompt). Added as self-check #14 (fourteen checks total); `SKILL.md`
    updated to match. Full proofread + regeneration of `03_script_prompt.md` requested from the
    live agent instance.
  - Done: full proofread applied. `FILM —` header in place; `CHR_*` References: entries are
    short role tags, no longer duplicating `Characters:`; also caught and deduped: rider
    silhouette description (Lighting: vs Characters:), the shaft-snap timing (reference line vs
    world rules), the snapped-poles shot references (world rules vs shots 3-4 themselves), and
    the goggles wearing rule (reference line vs Characters:); reworded two shot-6/palette lines
    that pointed at "shot 1" by number to instead describe the frame directly. Full 14-point
    self-check re-run, all PASS.
  - "now, not just for the characters, I want a short description of all the references. Keep
    it just concise. It doesn't need to be too descriptive, just a one-line description of what
    that reference is that should be included."
  - Applied: `.claude\agents\script-prompt-engineer.md` updated again — the `ENV_*`/`PRP_*`
    one-liners had stayed long (pulled near-verbatim from `ASSET_INDEX.md`'s description
    column, 30-40+ words), inconsistent with the short `CHR_*` role tags. Rule is now uniform:
    every `References:` one-liner, for every reference type, is a short concise phrase
    (~5-15 words) identifying what the thing is, not a full re-description. `ASSET_INDEX.md` is
    a starting point to condense from, not text to paste in. Self-check #13 updated to match.
    `03_script_prompt.md`'s `References:` block being trimmed via the live agent instance.
  - Done: all 11 one-liners now 5-13 words. Also lightly trimmed the two CHR_* lines (16/18
    words) down to the same range, and avoided "well" in the environment lines per 01_look.md's
    Biblical-anchor word ban (used "bore-hole" instead, matching the script's own vocabulary).
    Full 14-point self-check re-run, all PASS.
  - "can you update the script-prompt-engineer agent to remember to add this one-line
    description for all references?"
  - Applied: added a `## Lessons` entry to `.claude\agents\script-prompt-engineer.md` recording
    the one-liner requirement plus the two mistakes made getting there (CHR_* duplicating
    Characters:, ENV_*/PRP_* pulled too long from ASSET_INDEX.md) and the CONTINUITY-label
    lesson, so future runs of this specialist start from the corrected shape rather than
    re-discovering it. The rule itself was already load-bearing via the Output template and
    self-checks #13-14; this makes it explicit and durable the way other specialists' Lessons
    sections work.
  Rajan: "in the script, why are we describing the character Rajan, character Flag Rider, and
  character Sandstrider In detail once again. We already have the images of the respective
  characters attached, right? Can't we just directly focus on the prompt for the video movie
  generation?" — asked, then via AskUserQuestion chose "Keep a trimmed safety-net version": drop
  the full appearance writeup but keep 1-2 hard locks per character most prone to drift and most
  load-bearing to the story (not a full redescription).
  Applied: `.claude\agents\script-prompt-engineer.md` — `Characters:` block trimmed from full
  hard-lock writeups to 1-2 locks per character max; a character with nothing genuinely at risk
  of drifting gets no line at all. Self-check #15 added (fifteen total); `SKILL.md` updated to
  match; Lessons entry added recording the rationale (drift risk over a 6-shot node vs. pure
  redundancy with the attached image). `03_script_prompt.md`'s `Characters:` block being
  trimmed via the live agent instance.
  - Done: `Characters:` cut from ~190 to ~55 words. CHR_RAJAN keeps glasses-always-on plus the
    goggles-vs-glasses relationship (load-bearing for shot 5's climax); CHR_FLAG_RIDER keeps
    faceless/mid-ground-only; CHR_SAND_STRIDER keeps formidable-not-frightening. Everything else
    (build, wardrobe, hair, hide, etc.) now rests solely on the reference images. Full 15-point
    self-check re-run, all PASS. Flagged: the indigo work-coat's cut/weathering now has no text
    backup if it drifts on first render — cheap fix if needed.
  Rajan: "can we fold the one-line descriptions of the characters that are in the references and
  also under the characters heading, all under just the references?"
  Applied: `.claude\agents\script-prompt-engineer.md` — the `Characters:` heading is gone
  entirely. A `CHR_*` name's drift lock (if it has one) is now appended to that name's own
  `References:` one-liner after a semicolon, instead of a separate line under a separate
  heading. Self-checks merged back to fourteen total (#13 now covers both the one-liner and any
  folded-in drift lock); `SKILL.md` updated to match; Lessons entry added. `03_script_prompt.md`
  being restructured via the live agent instance.
  - Done: `Characters:` heading removed; each CHR_* line is now identity phrase + folded drift
    lock after a semicolon, on the same References: line. ENV_*/PRP_* lines unchanged. Full
    14-point self-check re-run, all PASS.
  Rajan: "Update the script-prompt-engineer.md instructions with this instructions so that
  whenever it creates a script prompt, it just has one References heading under which it just
  includes a 1- or 2-line description of whatever is important to be known of each of the
  attached references for the video generation model"
  Applied: `.claude\agents\script-prompt-engineer.md` — added a leading summary rule stating the
  settled shape plainly (one References: heading, one 1-2 line description per reference,
  nothing about any reference restated elsewhere), plus a Lessons entry marking this final after
  three rounds of convergence, so future runs treat it as standing instruction rather than
  something to re-derive. `03_script_prompt.md` already matches this shape from the prior round
  — no regeneration needed.
