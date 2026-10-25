# Game Plan: V7WORLD

## Risk Tasks

### 1. Third-person camera follow
- **Why isolated:** A readable action camera must follow the player without losing the vehicle or enemies.
- **Approach:** Use a controlled ArcRotateCamera with input disabled; update its target and radius around the player each frame.
- **Verify:** Player movement, vehicle proximity, and enemy targets remain visible without camera clipping.

### 2. Vehicle enter/exit state
- **Why isolated:** The game needs a clear handoff between on-foot movement and driving without introducing complex physics.
- **Approach:** Use a lightweight state machine with arcade steering, speed clamping, and a proximity-based E interaction.
- **Verify:** E enters/exits near the vehicle, controls switch visibly, and the camera follows both modes.

### 3. Projectile and enemy feedback
- **Why isolated:** Shooting needs a clear response in a browser-friendly loop.
- **Approach:** Use pooled-style transient projectile meshes, distance collision checks, health bars, and simple drone patrol motion.
- **Verify:** Click fires, ammo decreases, hits remove drones, and the objective counter updates.

## Main Build

- **Assets needed:** Generated V7WORLD visual target, procedural desert-industrial arena, tactical player proxy, off-road vehicle proxy, hostile drone proxies, cyan/amber emissive lights, HUD.
- **Verify:**
  - WASD movement, Shift sprint, F melee, click shooting, E vehicle interaction.
  - Arcade vehicle driving works in the compact open-world arena.
  - HUD remains readable without overlap on desktop and mobile.
  - No missing textures or obvious fallback assets.
  - `?demo` renders a deterministic gameplay state for screenshot verification.
  - No browser console errors during capture.
  - Color palette, camera angle, scale and visual density stay aligned with the generated reference.

This is an accessible browser MVP, not a native AAA open-world release. The architecture leaves room for larger maps, imported models, audio, missions and physics upgrades.
