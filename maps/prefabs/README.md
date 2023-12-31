# Easy Bone Merge
by FrostSource

> ### Allows quick and easy bone merging to a combine so you can have citizens or zombies firing guns as soon as possible.

> The prefab has some basic functionality for spawning and assigning squad, but for full functionality in a map the prefab should be collapsed or saved as a new prefab with the desired settings. The `Fade Corpse` spawnflag has been unticked to avoid a [known issue](#known-issues), it is recommended to clean up dead bodies through map I/O.

---

## Assets required

- maps\prefabs\npc\easy_bonemerge\easy_bonemerge.vmap
- scripts\vscripts\prefabs\npc\easy_bonemerge.lua

---

## Properties

| Property | Description |
| - | - |
| Bonemerge Model | The model that should be merged with the invisible combine. This model must have the same skeletal structure as a combine in order to be merged (most characters have this).
| NPC Name | The targetname of the combine NPC. This should be unique from all other entities for the bonemerge to work! Use this to directly reference the npc instead of the prefab.
| NPC Name Again | Should be exactly the same as `NPC Name` in order for the merging to work.
| Squad Name | NPCs that are in the same squad (i.e. have matching squad names) will share information about enemies, and will take turns attacking and covering each other.
| Override Advance Range | Minimum range to the player the combine is allowed to be when advancing for a LOS. 0 sets to default.
| Combine Type | The type of combine to merge to. `Grunt`, `Officer`, `Charger` or `Suppressor`.
| Start Spawned | If the NPC should started spawned in the map. This also disables the `ForceSpawn` input.
| Use Combine Voice | Set to `Yes` if you want to hear the combine voice communicating.

---

## Input / Output

|| Name | Description |
| -: | - | - |
| **Inputs**
|| ForceSpawn | Spawns the NPC at its original position.
| **Outputs**
|| OnDeath | Fired when this NPC is killed.

---

## Known Issues

When the engine decides to remove the ragdoll body it will create a new entity with a visible combine model (or the model of the npc you're bonemerging to) for a few seconds. This is more noticeable on lower settings.

---
