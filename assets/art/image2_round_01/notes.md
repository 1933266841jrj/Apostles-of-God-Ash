# Image2 Round 01 Notes

Source plan: 17_IMAGE2_ART_GENERATION_PLAN.md

Generation mode: built-in image generation tool, one prompt per asset group.

## Deliverables

### art_key/
- `art_key_low_whispering_field_1920_v01.png`
- Purpose: Low Whispering Field visual key art reference.
- Status: selected.
- Notes: Good overall mood, palette, wheat / barn / ritual material direction.

### backgrounds/
- `bg_field_room_baseline_1920_v01.png`
- Purpose: Godot 2D Hades-like 3/4 combat room background reference.
- Status: selected.
- Notes: Strong 3/4 room perspective, clear central walkable space, readable boundaries and edge props.

### characters/
- `concept_player_echo_turnaround_v01.png`
- Purpose: player sprite concept sheet for Unrhymed Echo.
- Status: selected draft.
- Notes: Four-pose sheet on simple background, suitable for later 96x96 cleanup.

- `concept_enemy_empty_one_v01.png`
- Purpose: basic melee enemy sprite concept sheet.
- Status: selected draft.
- Notes: Famine / empty-bowl symbolism without gore, suitable for later 96x96 cleanup.

- `concept_enemy_famine_farmer_v01.png`
- Purpose: mid-range famine farmer enemy sprite concept sheet.
- Status: selected draft.
- Notes: Seed / farm-tool attack identity is clear. Sheet came out wider than requested, but usable as concept reference.

### boss/
- `concept_boss_barn_king_phases_v01_has_labels.png`
- Purpose: first Barn King boss phase sheet.
- Status: reference only.
- Notes: Has generated text labels, so it should not be used as selected final.

- `concept_boss_barn_king_phases_v02.png`
- Purpose: Barn King three-phase boss sheet.
- Status: selected.
- Notes: No text labels, clear phase progression, readable exposed red core weak point.

### icons/
- `icon_memory_shard_variants_v01.png`
- Purpose: memory shard / log fragment icon variant sheet.
- Status: selected draft.
- Notes: Five-ish shard variants, readable silhouettes, good archive / crystal direction. Needs later cutout and 48x48 readability test.

### ui/
- `ui_archive_concept_1920_v01.png`
- Purpose: Sacred Casket log UI concept.
- Status: selected.
- Notes: Clear left fragment list, right paper text area, bottom truth assembly progress. Text is mostly placeholder marks.

### selected/
Contains the current recommended candidate for each P0 group.

## Technical Check

The built-in image generation tool did not strictly output every requested size:

- 16:9-style assets are mostly `1672x941`.
- Some concept sheets are `1536x1024`.
- Some concept sheets are `1774x887`.

These are acceptable for first-round art direction review, but should be resized or re-cropped before direct Godot pipeline use:

- key art / room / UI: crop or upscale to `1920x1080`
- character sheets: normalize to `1536x1024`, then extract poses into `96x96`
- boss sheet: crop or upscale to `2048x1152`
- icon sheet: crop or regenerate square before extracting `48x48`, `64x64`, `128x128`

## Validation Summary

Passed:
- No side-scrolling platformer room view in selected background.
- Selected background is Hades-like 3/4 room composition.
- Selected background has clear walkable combat space.
- Character and enemy sheets are concept-level gameplay sprites, not front poster art.
- Selected Boss v02 has three readable phases and a clear red-core weak point.
- UI concept communicates archive / Sacred Casket mood and has clear functional zones.

Needs follow-up:
- Generate additional v02-v03 variants for each P0 group if the team wants the full 14-18 image candidate pack from the plan.
- Remove / chroma-key backgrounds for character, enemy, boss, and icon assets if they need transparent PNGs.
- Normalize image sizes for Godot pipeline.
- For final sprite work, manually extract and redraw frames rather than using these concept sheets directly.
