# Rajan — protagonist likeness notes

Rajan plays the protagonist in every film made in this workshop. This folder holds his raw
character sheet and the likeness locks that carry from film to film.

**These notes are read by `asset-prompt-engineer` on every film** when it writes `CHR_RAJAN.md`. What is
written here is what stays constant about him across every story; everything else — wardrobe, hair
treatment, era, world detail — is restyled per film.

---

## The raw sheet

**File:** `protagonist/RAJAN_RAW.png` — 2048×1152, three panels on grey.

Views present: a full-body **standing front** figure (cropped above the neck — no head in this
panel), a full-body **standing back** figure (head included), and a **close-up front headshot**.
No height scale is present. There is no left/right 3/4, no profile, and the standing front panel
carries no face — the headshot panel is the only frontal face reference, and the standing back
panel is the only source for hair at the crown and back of the head.

*(Sheet content replaced 2026-08-14 — the file name stays `RAJAN_RAW.png`, unchanged, since that is
the name every reference in the workflow points to. The new sheet has three panels, down from the
old seven-view layout, and drops the height scale. Because no profile or 3/4 angle exists on this
sheet, any film needing a side view of Rajan's face has to extrapolate from the front headshot and
back-of-head panel — flag that explicitly in the asset prompt rather than assuming a profile
reference exists.)*

Every film's `CHR_RAJAN` prompt is written as an **image-to-image restyle** declaring this file as
its input, so the model preserves the real likeness rather than inventing a face.

---

## Likeness locks

Stated as declarative fact in every film's character prompt. This is what holds the face together
across every reference image and the film's single Seedance generation.

- **Apparent age:** late 30s
- **Build and height:** 5 ft 10 in (178 cm). Lean and slender — narrow shoulders, slim frame, no
  bulk. Slight, wiry rather than athletic
- **Skin tone:** medium-deep South Asian brown, warm undertone, even
- **Face shape:** long oval, tapering to a defined chin. High forehead. Cheeks slightly hollow
  below prominent cheekbones
- **Eyes:** dark brown, deep-set, level and steady. Moderate lid exposure, faint under-eye shadow
- **Eyebrows:** thick, dark, straight and low-set, with a slight natural arch at the outer third
- **Nose:** straight bridge, medium-broad, softly rounded tip, moderate nostril width
- **Mouth and jaw:** medium-width mouth, neutral straight set, fuller lower lip. Jaw defined but
  not heavy; chin rounded
- **Hair — colour, texture, default cut:** naturally curly, dense and voluminous, medium length,
  worn swept up and back off the forehead with height on top. Base colour near-black; **heavily
  salt-and-pepper**, with grey concentrated at the temples, sides, and front hairline and dark
  curls persisting at the crown and back. Hairline slightly receded at the temples
- **Facial hair:** short, even stubble across the moustache area, jaw, and chin — days-old growth,
  never a full beard. Lightly flecked with grey
- **Glasses or habitual accessories:** **always wears glasses.** Rectangular lenses, **fully
  rimless** — no frame visible at top or bottom, just thin dark metal temple arms meeting the lens
  edge directly. Low-profile and understated. A faint blue-violet anti-reflective sheen catches in
  the lenses. No other habitual accessories
- **Distinguishing marks:** none prominent. The combination that reads as *him* is the salt-and-
  pepper curls with height, the thin rimless rectangular glasses, and the lean long-jawed face
- **Resting expression:** calm, level, unsmiling but not stern. Direct gaze. Composed and watchful
- **Posture and bearing:** upright and relaxed, shoulders level and easy, weight evenly set. In the
  standing views, arms relaxed at his sides. Still rather than restless

## Wardrobe in the reference sheet — *not* a lock

The raw sheet shows a **black short-sleeve polo with a three-button placket, black tapered
trousers, and black low-top sneakers.** This is neutral reference clothing, not part of his
identity. Wardrobe is restyled per film to suit the world and era. Do not carry the polo forward
unless a film calls for it.

## Voice

This workshop's films carry no dialogue, voiceover, or on-screen text (wordless film, set
2026-08-14). Rajan's voice is never generated or specified in a Seedance prompt.

*(Removed 2026-08-14: previously locked age, timbre, accent, and pace for dialogue continuity
across nodes — filled by Rajan 2026-08-12. Moot once the format went dialogue-free.)*

## Things to avoid

Anything the generators consistently get wrong about him — note it here as it is discovered, so
every future film's prompt can exclude it up front.

*Anticipated from the likeness, to be confirmed or removed after the first film:*

- Straightening the hair, or rendering it as a flat uniform grey instead of dark curls with grey
  concentrated at the temples and sides
- Ageing him into a full grey head, or de-ageing him by removing the grey entirely
- Thickening the glasses into a heavy full-rim or horn-rim frame, or dropping them altogether
- Growing the stubble into a full beard or a clean shave
- Broadening the build — he is slender, and models tend to fill out a leading man
- Adding a smile to the resting expression

---

## In-story naming

The asset is **always** named `CHR_RAJAN`.

**The in-story name is also `Rajan` by default — in every film, unless Rajan asks for a different
one.** Do not invent a character name for him. If a story genuinely needs a different in-story name,
ask first; otherwise he is called Rajan on screen.

*(Set 2026-08-12, on film one. The first draft of THE FIFTH STONE named him "Arul" and Rajan
corrected it — the head writer had assumed the in-story name was free to invent, because this file
previously said only that the asset name stays stable.)*

The in-story name is still recorded per film in that film's `CHR_RAJAN.md` and in its
`ASSET_INDEX.md`, so any future exception stays traceable.
