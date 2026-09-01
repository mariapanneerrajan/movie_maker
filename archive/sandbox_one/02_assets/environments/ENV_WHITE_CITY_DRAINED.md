**Output filename:** ENV_WHITE_CITY_DRAINED

**In-story name:** The White City, central plaza — drained
**Appears in shots:** 3 (and as the state Act Three reverses in shot 4)

**Naming note:** `naming.md` says not to split an environment by time of day, only where the
geometry actually differs — and the geometry here does *not* differ. I made this a separate asset
anyway, on the same reasoning that split `CHR_COLOSSUS_PALM` from `CHR_COLOSSUS`: what changes is
**material**, not light. Every leaf, vine, moss bed and grass blade in the city is a different
substance in this state, and no lighting instruction can turn living foliage ash-grey. That is an
asset question, not a grade question. Name kept inside the `ENV_WHITE_CITY_` family so the three
city assets read and sort together; the longer `ENV_WHITE_CITY_PLAZA_DRAINED` sits at exactly the
28-character ceiling with no margin for a hand-typing slip, which is a bad trade for a name Rajan
types three times.

**Scope:** the plaza and the terraces visible above it, framed identically to
`ENV_WHITE_CITY_PLAZA`. No drained variant of `ENV_WHITE_CITY_SKYLINE` — the tower terraces are
already in frame here, so the ash state is sourced at both scales, and the camera never leaves the
plaza for an aerial in the drained moment.

## Prompt

```
A wide, open, unroofed civic plaza in an invented glass-and-garden city, shown as an empty
architectural reference with no people in it. Every plant in it has lost its colour. The
architecture is completely undamaged — only the living material has changed.

The plaza is a large open clearing that sightlines run straight through, paved seamlessly in pale
stone and glass slabs with no kerbs and no steps. The paving is wet, with a smooth sheen and
shallow standing water in the joints. Shallow planted water channels and broad reflecting shelves
run across the plaza, edged with tall grasses. Moss beds and ferns grow between the paving slabs.
Mature broad-canopied trees stand directly in the plaza floor, in open ground, spaced apart.

Around and above it rise slender curved towers in warm low-iron glass, with floor-to-sky curtain
walls and terraced glass balconies stepping back as they climb, vines spilling down whole facades
and small forests of trees standing on the terraces and rooftops. Glass footbridges span between
towers overhead, hung underneath with trailing gardens. Light glass canopies on hairline steel
edge the plaza. At one edge stands a broad glass transit pavilion with a heavy steel blast shutter
recessed into its lintel. There are no stone columns, no colonnade, no arcade, no cement.

Every leaf, frond, vine, moss bed and grass blade is drained to ash-grey — a cool, dusty,
desaturated blue-grey with no green left in it at all, like fine ash settled through the tissue.
The foliage keeps its exact living shape: canopies stay full, leaves stay flat and whole, vines
stay hung, grasses stay upright. It is colourless, not dead — nothing is wilted, curled, shrivelled
or shed.

All surfaces are blank, with no signage, lettering, writing, logos, flags or numerals anywhere.

Render the whole space under flat, even, neutral white overcast illumination, uniform from every
direction, with no directional key, no rim and no cast shadows beyond soft ambient contact
shading. Keep geometry, materials and scale clearly readable, sharp and evenly focused edge to
edge.

Negative: no green anywhere in the foliage. No wilting, drooping, curling, browning, rot, decay,
bare branches, fallen leaves or leaf litter. No damage, cracks, rubble or destruction to any
building, glass panel or paving slab. No columns, arcades, arches, cement or stone piers. No
colour grade, film emulation, time of day, sunset, dusk, night, weather, fog, mist, atmosphere,
god rays, lens flare, bloom, vignette, depth-of-field blur, motion blur, directional dramatic
lighting or mood. No crushed blacks, no monochrome conversion of the architecture — the glass and
stone keep their normal colour. No people, crowds, creatures, vehicles. No glowing threads.
```
