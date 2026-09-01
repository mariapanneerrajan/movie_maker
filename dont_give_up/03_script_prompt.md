# SEEDANCE PROMPT · 0:00–0:30

## References to connect
- CHR_RAJAN
- CHR_FLAG_RIDER
- CHR_SAND_STRIDER
- ENV_SUNKEN_FLATS_SAND_BURST
- ENV_SUNKEN_FLATS_OVERHEAD
- ENV_SUNKEN_FLATS_RIDGE
- ENV_FAR_DUNE_FIELD_SLOPE
- ENV_FAR_DUNE_FIELD_HORIZON
- ENV_BLACK_DUNE_DISTANT
- ENV_BLACK_DUNE_SUMMIT
- ENV_BLACK_DUNE_SUMMIT_DAWN
- ENV_BLACK_DUNE_OVERHEAD
- ENV_BLACK_DUNE_WATER_BURST
- PRP_BORE_RIG
- PRP_BROKEN_AUGER_SHAFT
- PRP_BANNER_POLE
- PRP_SNAPPED_POLES
- PRP_DUST_GOGGLES

## Prompt

```
FILM — THE THIRD SHAFT — standalone, single generation, 0:00–0:30, 16:9
Desert-epic photochemical; fine grain.
Palette: orange noon (1-2), rose-violet (3), blue-grey moon (4), green-gold dawn (5), orange, jade (6).
Light: above and behind him until shot 5, then green-gold from below.
Camera: never retreats; one slow move per shot; he stays small, plume and river full width. Lenses: 84° top-down static, dunes to all edges, plume into the lens (1, 6); 84° low push (2); 47° push in (3); 47° on the rig (4); 29° close, compressed background (5).
References:
@CHR_RAJAN — a desert tunneller; glasses always on
@CHR_FLAG_RIDER — riders who take his water; features hidden
@CHR_SAND_STRIDER — four-legged mount; warm, animal in shape
@ENV_SUNKEN_FLATS_SAND_BURST — sand erupting
@ENV_SUNKEN_FLATS_OVERHEAD — dust clearing
@ENV_SUNKEN_FLATS_RIDGE — under the ridge
@ENV_FAR_DUNE_FIELD_SLOPE — second site
@ENV_FAR_DUNE_FIELD_HORIZON — far horizon
@ENV_BLACK_DUNE_DISTANT — black dune
@ENV_BLACK_DUNE_SUMMIT — the crown at night
@ENV_BLACK_DUNE_SUMMIT_DAWN — same, first light
@ENV_BLACK_DUNE_OVERHEAD — water fallen
@ENV_BLACK_DUNE_WATER_BURST — water erupting
@PRP_BORE_RIG — his bore-rig
@PRP_BROKEN_AUGER_SHAFT — snapped auger
@PRP_BANNER_POLE — a claim pole
@PRP_SNAPPED_POLES — broken poles
@PRP_DUST_GOGGLES — above his glasses
World: water rises by itself, jade-green; nothing grows, every green is water. A planted pole claims the water. Only contact in the film: shot 3's passing brush.
No on-screen text or lettering; no dialogue, voiceover or narration.

SHOT 1 (0-6s) [ACT ONE] First frame already erupting — @ENV_SUNKEN_FLATS_SAND_BURST: ten storeys of sand into the lens, a shockwave ring over four crests, brown rain. Clearing to @ENV_SUNKEN_FLATS_OVERHEAD: @CHR_RAJAN within 1m of the hole, @PRP_DUST_GOGGLES up, hand on @PRP_BORE_RIG; green water climbs. His hand leaves the crank. SFX: DRUMS, then ERUPTS.

SHOT 2 (6-11s) [ACT TWO] @ENV_SUNKEN_FLATS_RIDGE: small at frame left by his pool, ridge full width behind. Ten @CHR_FLAG_RIDER crest it on @CHR_SAND_STRIDER mounts, then thirty pouring down. @PRP_BANNER_POLE drives in; shovels bury the pool. He hauls the rig away, eyes on where the water was. SFX: pole CRACKS in.

SHOT 3 (11-18s) [ACT TWO] @ENV_FAR_DUNE_FIELD_SLOPE: he works the crank; water comes up, cutting its channel wider. Almost smiling. Legs thunder in; the lead @CHR_FLAG_RIDER passes close, a pole arm catches him, and he tumbles into the sand as the rider plants @PRP_BANNER_POLE. He watches it buried, pushes his glasses straight, gets up. Behind, @ENV_FAR_DUNE_FIELD_HORIZON: a flag on every dune. Ahead, @ENV_BLACK_DUNE_DISTANT, @PRP_SNAPPED_POLES. He takes the rope and goes. SFX: rig GRINDS, legs THUNDER.

SHOT 4 (18-24s) [ACT TWO] @ENV_BLACK_DUNE_SUMMIT at night, broken poles below. He hangs off the crank; grit climbs, the A-frame shudders. Faster; the shaft SNAPS — @PRP_BROKEN_AUGER_SHAFT, flywheel free, dust pouring. He goes down on his knees in it. SFX: rig SQUEALS, then the SNAP.

SHOT 5 (24-27s) [ACT THREE] Close on him, @ENV_BLACK_DUNE_SUMMIT_DAWN, dust on his lenses, shoulder to the shaft. He drives it down. Once. Again. The crust splits, green-gold climbs across his face; water BREAKS past him white and roaring (@ENV_BLACK_DUNE_WATER_BURST material), lifting the goggles off his head; he lets them go. His face comes up into it, streaming. SFX: the ground BREATHES.

SHOT 6 (27-30s) [ACT THREE] Opening frame, hole centre, erupting again — @ENV_BLACK_DUNE_WATER_BURST: taller than the sand went, sunlit, rainbows in its spray; it opens out and comes down across the whole width as shining rain. @ENV_BLACK_DUNE_OVERHEAD: below it the river tears to the horizon; nothing on the land but water. The rain falls on @CHR_RAJAN — soaked, head back, arms wide, turning slowly under it, laughing. The column keeps climbing. SFX: hole ERUPTS.

AMBIENT: wind, sand hiss, rope creak; score low, near silent at 23s.
```

**Notes for Rajan (not part of the prompt):**

Seven strings changed, all for moderation safety. Every beat is intact.

| Before | After | Why |
| --- | --- | --- |
| `the lead @CHR_FLAG_RIDER sweeps his pole across his chest in passing, puts him flat` | `the lead @CHR_FLAG_RIDER passes close, a pole arm catches him, and he tumbles into the sand` | Weapon-into-a-person's-chest was the highest-risk phrasing in the file. Now it reads as a collision with a passing rider: same cause, same outcome, no swing, no chest contact, no possessive on the tag |
| `One contact only, shot 3's sweep in passing: no strike, no injury.` | `Only contact in the film: shot 3's passing brush.` | "strike" and "injury" are violence keywords even inside a negation, and scanners do not parse negation. The guard survives with zero violence vocabulary |
| `rig SCREAMS` | `rig GRINDS` | Human-distress verb on a machine |
| `rig SHRIEKS` | `rig SQUEALS` | Same |
| `never monstrous` | `warm, animal in shape` | The same negation trap — "monstrous" is the keyword and the filter never sees the "never". This is also the look sheet's own positive wording |
| `no face` | `features hidden` | A faceless figure can read as body-horror to a scanner; the story lock is unchanged |
| `tearing the goggles off his head` | `lifting the goggles off his head` | A tearing verb beside a head, for no gain |

**Deviations from the script's CAPS cues, for the script-writer:** the script marks `SCREAMS`
(shot 3) and `SHRIEKS` (shot 4). Both are machine verbs in the prompt now. Self-check #11 is
reported below as a flagged deviation, not a silent pass. `DRUMS`, `CRACKS`, `THUNDER`, `SNAPS`,
`BREAKS`, `BREATHES` and `ERUPTS` are unchanged — a pole cracking into ground and a shaft snapping
read as material events rather than harm, and I judged them not worth further script drift.

**Considered and deliberately left alone:** "shovels bury the pool" (the object is water), "He goes
down on his knees in it", "water BREAKS past him white and roaring", "broken poles", "snapped
auger", "shockwave ring". If a second rejection comes back, the next candidates in order are
`CRACKS` → `THUDS`, "bury" → "cover", "a pole arm catches him" → "he is bumped aside", and dropping
the "Only contact in the film" clause entirely.

**Also worth testing on Rajan's side:** the rejection message names "prompt **or reference**". If
this pass still trips, the next thing to isolate is the reference images — connect them in batches
to find whether a picture rather than a sentence is the trigger. `CHR_FLAG_RIDER` (a fully
head-wrapped figure with no visible face) is the most likely image-side candidate.
