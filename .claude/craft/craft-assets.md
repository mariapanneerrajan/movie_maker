# craft-assets

Read by: asset-designer. Read `CRAFT.md` first.

## Founding principles

### What an asset render is for

These images are **reference inputs to Seedance 2.5**, not deliverables. Seedance does the
lighting, the grade, the atmosphere, and the mood. An asset image exists to answer exactly one
question: *what does this thing look like?*

Every drop of mood baked into an asset image is mood Seedance must fight against. A character
sheet lit with dramatic rim light will drag that rim light into every shot of the film, including
the ones set at noon.

### The neutral rule — non-negotiable, every asset, every film

Every asset prompt must specify:

- Seamless **mid-grey background (#808080)**, flat and uniform.
- **Flat, even, neutral white lighting** — soft frontal fill, no key/rim separation, no shadows
  beyond soft contact shadow.
- **No colour grade, no film emulation, no time of day, no weather, no atmosphere.**
- No lens flare, no bloom, no vignette, no depth-of-field blur, no motion blur.
- No environmental context — the subject alone against the grey.
- Sharp, evenly focused, full subject in frame.

And an explicit negative clause naming those exclusions, because these models add drama unbidden.

### Characters

A character sheet is a turnaround. Specify:

- **Row 1:** full body, A-pose, front / three-quarter / profile / back — consistent scale.
- **Row 2:** head and shoulders, front / three-quarter / profile.
- **Hard locks:** age, build, height relative to other characters, skin tone, hair, facial
  structure, wardrobe piece by piece with colours named, footwear, and any distinguishing mark.
  Write these as declarative fact, not suggestion — they are what holds the character together
  across six independently generated nodes.
- Neutral expression on the sheet. Expression is the film's job.

### `CHR_RAJAN` is always an image-to-image restyle

The protagonist is Rajan, and his likeness is real. His prompt is never a description that
invents a face — it declares `protagonist/RAJAN_RAW.png` as its input image and instructs the
model to preserve the face, head shape, and proportions exactly while restyling wardrobe, hair
treatment, era, and world-appropriate detail. The likeness locks in
`protagonist/RAJAN_NOTES.md` are read and carried into every film's version.

### Environments

An environment plate is the space with the drama removed: correct architecture, correct
materials, correct scale, correct props in place — under flat neutral illumination, no time of
day, no weather, no atmosphere, no colour grade. A clean, empty, well-described room.

Where a full grey seamless makes no sense for a space, hold the *intent*: neutral overcast-flat
illumination, no directional drama, no grade, no mood. The geometry and the materials are what
Seedance needs; the light is what it will supply.

### Props

Clean multi-angle views on the same grey — front, three-quarter, and any angle that reveals a
mechanism the story uses. Name the materials and their finish. Include scale reference when size
matters to the story.

### Scope discipline

Only assets that actually appear in the script get a file. Every asset that appears in the script
gets a file — an unlisted character or prop becomes an inconsistency in the node prompts. Sweep
the whole script; do not stop at the first pass.

### Prompt style for image models

GPT Image 2 and Nano Banana both respond better to plain declarative description than to keyword
soup. Write full sentences. Front-load the subject, then structure, then materials, then the
neutral-render clause, then the negative clause. Keep it under roughly 250 words — past that,
these models begin dropping early detail.

---

## Lessons

*(none yet — the first retrospective will add here)*
