# LittleCraft

A Minecraft-style voxel sandbox that runs entirely in the browser. One HTML file, no build step, no assets — textures, terrain, and sound are all generated procedurally at runtime. Rendering uses [three.js](https://threejs.org) loaded from a CDN.

## Run

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

Any static file server works (`npx serve`, etc.). Opening `index.html` directly via `file://` also works in Chrome.

## Features

- Infinite procedural terrain: continents, mountains, beaches, oceans, snow caps, caves with lava pools, trees, and ore veins (coal, iron, gold, diamond)
- Chunked meshing with face culling and baked ambient occlusion
- Realistic lighting: directional sun/moon with real-time PCF soft shadows, hemisphere ambient, soft fill light for shaded faces, ACES filmic tone mapping
- Flowing water simulation: Minecraft-style fluid levels — water falls, spreads with decreasing depth, drains when cut off; sloped surface rendering by level; currents push the player; placeable water source blocks (inventory)
- Custom shaders: gradient sky dome with sun disc, dusk glow, moon and stars; animated water with waves, scrolling texture, sun specular and fresnel transparency
- Emissive blocks (glowstone, lava) render full-bright
- Natural foliage: leaf blocks are double-sided cutouts with gaps that let light and sky through, casting dappled shadows, and sway gently in the wind
- Tools: iron pickaxe, axe, and sword — hold left click to mine with per-block hardness, crack overlay shows progress; each tool is ~5x faster on its materials (pickaxe → stone/ores, axe → wood, sword → leaves/wool); held-item view with swing animation
- Inventory (`E`) with tools and 31 placeable block types; break / place / pick (middle click)
- First-person physics: walking, sprinting, jumping, swimming, fly mode (double-tap Space or `F`)
- Day/night cycle, drifting clouds, fog, underwater tint + dense underwater fog
- Procedural sound effects (Web Audio)
- World edits persist in `localStorage` per seed

## Controls

| Input | Action |
|---|---|
| Mouse | Look |
| W A S D | Move |
| Space | Jump / swim up / fly up |
| Double-tap Space | Toggle fly (also `F`) |
| Shift | Sprint (descend in fly mode) |
| E | Open / close inventory |
| Left / Right click | Break / place block |
| Middle click | Pick block |
| 1–0 or wheel | Select hotbar slot |
| R | Teleport to surface |
| Esc | Pause |

## Seeds

Append `?seed=12345` to the URL for a different world. Edits are saved per seed; the pause menu has a reset button.
