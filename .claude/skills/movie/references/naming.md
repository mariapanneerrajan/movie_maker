# The naming contract

Read by: asset-designer, storyboard-artist, seedance-prompt-engineer, continuity-checker.

## Why this is a contract and not a convention

Every name in this pipeline is used in **three places**:

1. The filename of the prompt: `02_assets/characters/CHR_RAJAN.md`
2. The filename Rajan saves the generated image under: `CHR_RAJAN.png`
3. The reference string in a Seedance node's connect list: `- CHR_RAJAN`

Rajan types these by hand. A name that drifts by one character between the prompt file and the
node reference list produces a node that connects the wrong image, or no image. There is no
automated link to catch it — the string *is* the link.

**Never rename an existing asset.** If a name is wrong, it is fixed at the gate where it was
created, before any image has been generated from it, and every reference to it is updated in
the same pass.

## The rules

- `UPPER_SNAKE_CASE`
- ASCII letters, digits, and underscore only. No spaces, hyphens, apostrophes, or accents
- Maximum 28 characters including the prefix
- Unique across the entire film — a character and a prop may not share a name
- Descriptive of the thing, not of the shot it appears in

## The patterns

| Kind | Pattern | Examples |
| --- | --- | --- |
| Character | `CHR_<NAME>` | `CHR_RAJAN`, `CHR_ELDER_MIRA`, `CHR_TIN_SPARROW` |
| Environment | `ENV_<PLACE>_<QUALIFIER>` | `ENV_LIGHTHOUSE_INT`, `ENV_SALT_FLATS`, `ENV_WORKSHOP_EXT` |
| Prop | `PRP_<THING>` | `PRP_BRASS_LANTERN`, `PRP_SEED_VIAL` |
| Storyboard panel | `SB_N<node>_<nn>` | `SB_N1_01`, `SB_N3_02`, `SB_N6_03` |

Environment qualifiers: use `_INT` / `_EXT` where a space exists in both, or a distinguishing
word where the same place appears in two states the geometry actually differs in
(`ENV_TOWER_INTACT` / `ENV_TOWER_RUINED`). Do **not** create separate environments for the same
space at different times of day — time of day is Seedance's job, not the asset's.

Storyboard panels are numbered within their node, starting at `01`, in time order. `SB_N3_02` is
the second panel of node 3. Panel numbering never crosses nodes.

## Every prompt file declares its own name

The first field of every asset and storyboard prompt file, before anything else:

```markdown
**Output filename:** CHR_RAJAN.png
```

That line is what Rajan reads when saving the generated image. It must match the file's own
basename exactly.

## The protagonist name is fixed

Rajan plays the protagonist in every film in this workshop. The character asset is **always**
named `CHR_RAJAN`, regardless of what the character is called inside the story. If the script
names him Elias, the script says `ELIAS` and the asset is still `CHR_RAJAN` — with the in-story
name recorded in the asset file and in `ASSET_INDEX.md`, so the node prompts can use the story
name in dialogue while referencing the stable asset name.
