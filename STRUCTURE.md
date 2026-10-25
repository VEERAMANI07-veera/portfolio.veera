# V7WORLD Structure

- `client/src/components/GameCanvas.tsx` — lifecycle-safe Babylon canvas host.
- `client/src/game/scene.ts` — scene creation, input, camera, gameplay loop, procedural arena, enemies, bullets, vehicle state, and cleanup.
- `client/src/pages/V7World.tsx` — game shell and HUD overlay.
- `client/src/App.tsx` — portfolio route plus `/v7world` game route.

The Babylon scene owns gameplay objects and rendering. React owns only the page shell and HUD subscription. The MVP uses procedural meshes and generated-art direction rather than large local model assets so it stays responsive in a browser.
