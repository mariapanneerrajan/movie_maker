# ASSET INDEX — THE THIRD SHAFT

All three character sheets share one layout, mirroring `protagonist/RAJAN_RAW.png`: **exactly three
tall vertical panels** on flat mid-grey — **front full body with the head out of frame / back full
body / front close-up**. No three-quarter view, no profile view, no extra head angles, no height
scale.

**Environments are one view per image.** Each named environment asset is a single camera view or
single moment serving specific shots; no environment file asks for two views on one sheet.

**Format.** This film generates **16:9 horizontal** (per-film exception, `01_look.md`). The two
burst assets are framed 16:9 to match. The seven earlier environment views were written vertical
9:16 before that exception existed and are being kept as-is at Rajan's direction — see the note at
the foot of this file.

**Base assets.** Where an asset is a variation of another, the `Base asset` column names the image
to connect as a reference when generating it. Generate bases before their variations. Assets with a
blank cell are standalone. `CHR_RAJAN` has no base asset because it already declares an input image,
`protagonist/RAJAN_RAW.png`, which serves the same purpose.

| Name | Kind | Base asset | In-story name | Description | Shots |
| --- | --- | --- | --- | --- | --- |
| `CHR_RAJAN` | Character | *(input image: `RAJAN_RAW.png`)* | Rajan | Lean late-thirties desert tunneller, salt-and-pepper curls, fully rimless glasses always on, faded indigo knee-length work-coat, oatmeal shirt, ochre trousers, brass dust goggles pushed up on the forehead above the glasses. Image-to-image restyle; front panel is cropped above the neck, per the raw sheet. | 1, 2, 3, 4, 5, 6 |
| `CHR_FLAG_RIDER` | Character | | the flag-riders | Fully head-wrapped claim-rider in wind-cracked ochre and rust robes, no face at any angle, a blank bleached-crimson banner pole slung across the back. Never individuated. In shot 3 the lead rider sweeps his pole arm across Rajan's chest in passing — the film's only physical contact. | 2, 3 |
| `CHR_SAND_STRIDER` | Character | | sand-strider | The riders' mount: eleven feet at the shoulder, four long double-hinged legs, low-slung slender body, dune-tan hide with bone-coloured keratin plates, leather saddle rig and empty pole scabbard. Human mannequin in the front panel for scale. | 2, 3 |
| `ENV_SUNKEN_FLATS_RIDGE` | Environment | | The Sunken Flats, under the ridge | Low wide view from the basin floor: bore-hole in the near foreground, the dune ridge running behind it. Root view of the Flats. | 2 |
| `ENV_SUNKEN_FLATS_OVERHEAD` | Environment | `ENV_SUNKEN_FLATS_RIDGE` | The Sunken Flats, from above | Straight-down aerial onto the basin floor, orange dune backs filling the frame, the drum-wide bore-hole and its tailings collar dead centre. | 1 |
| `ENV_SUNKEN_FLATS_SAND_BURST` | Environment | `ENV_SUNKEN_FLATS_OVERHEAD` | The Sunken Flats erupting | The same top-down frame at the instant of eruption: a ten-storey column of dry sand boiling up into the lens, mushrooming flat, tipping into brown rain, a shockwave ring skating over four dune crests. 16:9. | 1 (0:00–0:03) |
| `ENV_FAR_DUNE_FIELD_SLOPE` | Environment | | The far dune field, working slope | Eye-level view of a flat sand shelf falling away into a long clean downhill run, with a high empty dune ridge standing across the frame behind it. Root view of the far field. | 3 |
| `ENV_FAR_DUNE_FIELD_HORIZON` | Environment | `ENV_FAR_DUNE_FIELD_SLOPE` | The far dune field, looking back | Wide eye-level view back over rank after rank of orange dune crests receding to a flat far horizon — the ground the flag chain is planted across and the river later reaches. | 3, 6 |
| `ENV_BLACK_DUNE_DISTANT` | Environment | | The black dune, far out and alone | Eye-level view across open orange sand at the whole isolated black dune, with the loose ring of roughly twenty snapped, half-buried poles readable around its foot. Root view of the black dune. | 3 |
| `ENV_BLACK_DUNE_SUMMIT` | Environment | `ENV_BLACK_DUNE_DISTANT` | The black dune, on the summit | Eye-level on the broad flat black crown, running out to the crest where the slope falls away, with the ring of broken poles visible far below at the foot. | 4, 5 |
| `ENV_BLACK_DUNE_OVERHEAD` | Environment | `ENV_SUNKEN_FLATS_OVERHEAD` (camera geometry; also connect `ENV_BLACK_DUNE_SUMMIT` for grit colour) | The black dune summit, from above | Straight-down aerial onto the black crown, bore-hole dead centre, dark slopes falling to pale orange dune country in the frame corners. Must rhyme exactly with shot 1's framing. | 6 |
| `ENV_BLACK_DUNE_WATER_BURST` | Environment | `ENV_BLACK_DUNE_OVERHEAD` (also connect `ENV_SUNKEN_FLATS_SAND_BURST` so the two bursts match) | The black dune erupting | The same top-down frame at the instant of eruption: a column of water taller than the sand went, white core with a jade heart, blooming and falling back as shining rain across the full width. 16:9. Also the material reference for shot 5. | 6 (0:27–0:29), and material reference for 5 |
| `PRP_BORE_RIG` | Prop | | Rajan's bore-rig | Hand-cranked canvas-and-brass boring machine on a timber sledge: A-frame, guy ropes, brass-and-iron flywheel with a long walking crank arm, bevel gear, steel helical auger, waxed canvas hood, hemp tow-rope. Four views plus a scale mannequin. | 1, 2, 3, 4 |
| `PRP_BROKEN_AUGER_SHAFT` | Prop | `PRP_BORE_RIG` | the broken auger shaft | The lower section of the rig's auger after it snaps at 0:23 — same screw and chisel bit, now severed, with a bright torn break. Never repaired. | 4, 5 |
| `PRP_BANNER_POLE` | Prop | | a claim pole | Fresh claim marker: bare silvered timber shaft twice a man's height, brass collars, iron-shod driving point, blank bleached-crimson banner. Includes a row of five and a scale mannequin. | 2, 3 |
| `PRP_SNAPPED_POLES` | Prop | `PRP_BANNER_POLE` | the ring of snapped poles | The same poles long abandoned — splintered stumps, cracked silvered timber, tarnished brass, colourless cloth shreds, half-buried and leaning. Includes a loose broken circle of eight. | 3, 4 |
| `PRP_DUST_GOGGLES` | Prop | | Rajan's dust goggles | Brass-rimmed smoked-glass goggles with brown leather cups and a faded dust-grey canvas strap. Worn above his glasses, never instead of them; torn off by the water in shot 5. | 1, 2, 3, 4, 5 |

**Generation order implied by the base chain:**

1. `ENV_SUNKEN_FLATS_RIDGE` → `ENV_SUNKEN_FLATS_OVERHEAD` → `ENV_SUNKEN_FLATS_SAND_BURST`
2. `ENV_SUNKEN_FLATS_OVERHEAD` → `ENV_BLACK_DUNE_OVERHEAD` → `ENV_BLACK_DUNE_WATER_BURST`
3. `ENV_FAR_DUNE_FIELD_SLOPE` → `ENV_FAR_DUNE_FIELD_HORIZON`
4. `ENV_BLACK_DUNE_DISTANT` → `ENV_BLACK_DUNE_SUMMIT` (and before `ENV_BLACK_DUNE_OVERHEAD` if its
   second reference is being attached)
5. `PRP_BANNER_POLE` → `PRP_SNAPPED_POLES`
6. `PRP_BORE_RIG` → `PRP_BROKEN_AUGER_SHAFT`

`ENV_SUNKEN_FLATS_OVERHEAD` is the deepest root — three of the four top-down frames descend from it,
which is what holds the shot 1 / shot 6 rhyme together. Generate the sand burst before the water
burst so the water can be matched to it and made visibly taller.

**Shot-to-environment map, for the node's reference list:**

| Shot | Environment views |
| --- | --- |
| 1 | `ENV_SUNKEN_FLATS_SAND_BURST` (0:00–0:03), then `ENV_SUNKEN_FLATS_OVERHEAD` (as the dust clears) |
| 2 | `ENV_SUNKEN_FLATS_RIDGE` |
| 3 | `ENV_FAR_DUNE_FIELD_SLOPE`, then `ENV_FAR_DUNE_FIELD_HORIZON`, then `ENV_BLACK_DUNE_DISTANT` |
| 4 | `ENV_BLACK_DUNE_SUMMIT` |
| 5 | `ENV_BLACK_DUNE_SUMMIT`, with `ENV_BLACK_DUNE_WATER_BURST` for the water's material |
| 6 | `ENV_BLACK_DUNE_WATER_BURST` (0:27–0:29), then `ENV_BLACK_DUNE_OVERHEAD`, with `ENV_FAR_DUNE_FIELD_HORIZON` as the open flag-free ground the river runs into (no flags, poles, riders, or striders anywhere in shot 6, including the horizon — script revision 2026-08-15) |

**Downstream note for the script-prompt-engineer:** no profile or three-quarter reference of any
character exists on these sheets, by design. Rajan is seen front (body only), back, and front
close-up; the same for the riders and the strider. **Any side-on or three-quarter angle of a
character in a keyframe or in the node is an extrapolation, not a sourced view** — treat it as an
approximation. The riders have no face at any angle, which is a story lock, not a gap.

**Open format inconsistency:** the film is 16:9, but the seven environment views written before that
exception all specify vertical 9:16 in their prompt bodies. Only the two burst assets say 16:9. This
is known and deliberate for now; if those seven are ever regenerated, the aspect line is the one
thing in them that needs changing.

**Superseded names — never use:** `ENV_SUNKEN_FLATS`, `ENV_FAR_DUNE_FIELD`, `ENV_BLACK_DUNE`. These
were combined two-view sheets, split 2026-08-15 into single-view assets. Their files remain in
`environments/` as delete-me stubs only.

**Not given separate assets, by design:** Rajan's rimless glasses (locked inside `CHR_RAJAN`, and
they stay on his face all film — knocked askew in shot 3, pushed straight, never lost); the
jade-green river and the sprouting grass (a Seedance behaviour, not a physical object); shot 5's
close eruption (served by `CHR_RAJAN` plus `ENV_BLACK_DUNE_WATER_BURST`'s water material — see the
report); the bore-hole itself (fixed geometry inside the environment views that contain it); the
tow-rope (part of `PRP_BORE_RIG`); the sand-strider mounted with a rider (dropped to hold the
three-panel character lock).
