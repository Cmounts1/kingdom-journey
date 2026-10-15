# Kingdom Journey: 3D Conversion Plan

## Goal
Build a separate, testable Three.js prototype in a stylized storybook world with a third-person character-follow camera. Keep the existing 2D game untouched on `main`; this branch is a sandbox.

## Prototype branch
- Branch: `feature/3d-inn-prototype`
- Starting point: `main`
- Prototype entry: `3d-prototype/index.html`
- GitHub Pages still serves the existing 2D game at the root URL. The `3d-prototype/` folder is also copied to the existing Pages branch for a separate preview URL; no publishing setting was changed.

## Phase 1: prove the 3D feel
Implemented in the first prototype:
- Procedural storybook inn exterior, path, cottages, trees, lanterns and rolling hills.
- Low-poly traveler character built from Three.js primitives, with a satchel.
- Smooth third-person follow camera.
- Desktop movement with WASD and arrow keys.
- Touch joystick and large mobile action buttons.
- Inn-door proximity check and a simple entry interaction.
- Responsive layout, safe-area padding and capped device pixel ratio for mobile performance.

## Phase 2: core 3D game systems
Implemented in the prototype code, pending live browser testing:
- Player path choice: Traveler, Helper or Mystery Seeker.
- Bethlehem market stall, three Scripture scrolls, shepherd, manger/stable and star.
- Chapter 1 shepherd quiz and Chapter 2 manger quiz with XP rewards.
- Three path-exclusive side quests, collectible quest items, rewards and keepsakes.
- XP, level, inventory, equipment effects, market purchases and traveler journal.
- Separate 3D save key so the existing 2D save is not overwritten.
- Enterable inn and cottages, with the HUD writing hidden while indoors.
- Desktop keyboard interaction, mobile joystick, run toggle and action controls.
- Collision checks, fixed-angle third-person camera and walking animation.

## Phase 3: harden and test
1. Test on an iPhone and desktop; adjust touch sensitivity, movement speed and camera distance.
2. Verify all doors, interior views, market, scrolls, both chapter quizzes and all three side quests in a live browser.
3. Check browser console for module/CDN or WebGL failures and repair any runtime errors.
4. Add sound toggles and a quality setting if mobile frame rate needs help.

## Phase 4: save compatibility and polish
- The 3D prototype currently uses a separate save key to protect existing 2D progress.
- Do not migrate or overwrite 2D saved progress without an explicit migration and recovery plan.
- Keep game rules and rendering modular as the 3D world grows.

## Phase 5: expand carefully
1. Deepen building interiors with interactable objects and resident NPCs.
2. Add richer story animations, conversations, sound and environmental details.
3. Continue performance and accessibility improvements for mobile.

## Acceptance checklist
- `main` and the current published 2D game are unchanged.
- Prototype source is maintained on `feature/3d-inn-prototype`; a copy under `3d-prototype/` is available on the existing Pages branch for preview.
- Player moves in four directions on keyboard and touch.
- Camera follows smoothly without overtaking the character.
- Inn doorway interaction works at close range.
- Layout fits a phone screen in portrait and landscape.
- The 3D game uses a separate save key and does not overwrite 2D progress.
- All major 2D story decisions are represented in the 3D prototype code; full browser/mobile behavior still needs testing.

## Important publishing note
GitHub Pages currently publishes from `fix/inn-interactions`, not `main`. Do not change that setting or merge this prototype into the published branch until the 3D version has been reviewed and explicitly approved.

## 2D decisions carried into the 3D world

The 3D branch now includes a first playable mapping of the existing 2D game's decisions and progression:

- **Core route and locations:** inn, village cottages, Bethlehem market, hillside shepherd, three Scripture scrolls, and the manger/stable under the guiding star.
- **Three player paths:** Traveler, Helper, and Mystery Seeker. The choice shapes quest guidance and selects one exclusive side quest.
- **Chapter 1:** Shepherd conversation and Luke 2:8–20 quiz, awarding 25 XP.
- **Collectibles:** three Scripture scrolls, each awarding 5 XP and contributing a journal note.
- **Chapter 2:** unlocks after the shepherd quiz and all three scrolls; Luke 2:12–16 manger quiz awards 30 XP.
- **Exclusive side quests:** The Missing Road Marker (Mara, 20 XP and Wayfinder's Compass); Bread for the Shepherds (Eli, 25 XP and Token of Kindness); The Torn Prophecy (Natan, 30 XP and Sealed Clue).
- **Market and gear:** Traveler's Lantern (15 XP), Festival Cloak (25 XP), and Swift Traveler Boots (30 XP). The inventory has eight slots; gear can be equipped or unequipped.
- **Journal and save:** XP, chapter flags, path choice, scroll collection, inventory/equipment, side-quest state, keepsakes, and player position are saved under a 3D-specific local-storage key. This intentionally does not overwrite the 2D game's save.
- **Controls:** keyboard and mobile joystick, run toggle, interaction button, fixed third-person follow camera, and building entry/exit.

## Preservation rule

The original 2D game remains available on `main` and its current Pages publishing setup is not changed by this conversion. Treat the 3D version as a separate implementation of the same design decisions. Test and tune each 3D feature before considering the 2D game for retirement.
