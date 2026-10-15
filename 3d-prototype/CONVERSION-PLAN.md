# Kingdom Journey: 3D Conversion Plan

## Goal
Build a separate, testable Three.js prototype in a stylized storybook world with a third-person character-follow camera. Keep the existing 2D game untouched on `main`; this branch is a sandbox.

## Prototype branch
- Branch: `feature/3d-inn-prototype`
- Starting point: `main`
- Prototype entry: `3d-prototype/index.html`
- This branch is not configured as the live GitHub Pages branch. The existing public game stays as-is.

## Phase 1: prove the 3D feel
Implemented in the first prototype:
- Procedural storybook inn exterior, path, cottages, trees, lanterns and rolling hills.
- Low-poly traveler character built from Three.js primitives, with a satchel.
- Smooth third-person follow camera.
- Desktop movement with WASD and arrow keys.
- Touch joystick and large mobile action buttons.
- Inn-door proximity check and a simple entry interaction.
- Responsive layout, safe-area padding and capped device pixel ratio for mobile performance.

## Phase 2: harden the prototype
1. Test on an iPhone and desktop; adjust touch sensitivity, movement speed and camera distance.
2. Add collision boundaries for walls, trees and props, plus a clear walkable path.
3. Add an interaction prompt that appears only when the player is near the door.
4. Add sound toggles and a quality setting if mobile frame rate needs help.
5. Check browser console for module/CDN or WebGL failures.

## Phase 3: reconnect the game
Keep game rules separate from rendering. Extract or wrap shared state for:
- player-selected story path and exclusive side quest
- chapter unlocks, shepherd and manger quizzes
- Scripture scrolls, XP, equipment and inventory
- journal, reflections and saved progress

Use an adapter layer so the 3D scene calls the same quest actions as the 2D game rather than creating a second source of truth. Preserve save keys and test existing progress before migration.

## Phase 4: expand carefully
1. Inn exterior and entry transition.
2. Inn interior and player spawn.
3. Bethlehem path and market.
4. NPC proximity interactions and quest markers.
5. Bring over chapters and side quests one at a time.
6. Add accessible controls, performance checks and a fallback message for unsupported WebGL.

## Acceptance checklist
- `main` and the current published 2D game are unchanged.
- Prototype exists only on `feature/3d-inn-prototype`.
- Player moves in four directions on keyboard and touch.
- Camera follows smoothly without overtaking the character.
- Inn doorway interaction works at close range.
- Layout fits a phone screen in portrait and landscape.
- Quest state is not migrated until it can be tested without losing existing saves.

## Important publishing note
GitHub Pages currently publishes from `fix/inn-interactions`, not `main`. Do not change that setting or merge this prototype into the published branch until the 3D version has been reviewed and explicitly approved.
