# WebSlime — Project Specification

**Status:** 50/50 features passing (100%)

## Overview

An interactive real-time WebGL simulation that recreates the visual experience of the cosmodernism video series — a dark, glossy, slime-like organism with living Turing-pattern textures and multiple eyes crawling across a bright yellow industrial pegboard surface. The organism responds to mouse/touch input as an attractor, moving with organic spurt-based locomotion while flowing around, climbing over, and squeezing between environmental obstacles. The simulation must be visually indistinguishable from the reference videos. Reference frames are provided in `./frames/video01/` (453 frames) and `./frames/video02/` (676 frames) for visual comparison during development.

## Technology Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla JavaScript (no framework) |
| Rendering | WebGL 2.0 with GLSL shaders |
| Styling | Embedded CSS (single-file application) |
| Format | Single standalone HTML file with embedded JS/CSS |
| Backend | None — pure client-side application |
| Database | None — stateless application |
| API | None — no server communication |
| Visual Testing | Playwright for automated screenshot comparison against reference frames |
| Serving | Any simple static file server (e.g., `python -m http.server`, `npx serve`) |

## Prerequisites

- Modern browser with WebGL 2.0 support
- Node.js (for Playwright visual testing)
- Reference frames in `./frames/video01/` and `./frames/video02/`

## Implementation Steps

| Phase | Title | Key Tasks |
|-------|-------|-----------|
| 1 | Project Setup & Environment Rendering | WebGL 2.0 context, SDF pegboard surface, procedural generation, lighting, Playwright pipeline |
| 2 | Organism Body Simulation | Soft-body physics, metaball rendering, anatomy (head/body/pseudopods), viscous drag |
| 3 | Turing Pattern System | GPU reaction-diffusion (ping-pong FBOs), UV mapping, parameter tuning |
| 4 | Eye System | Glossy spherical eyes, organic cursor tracking, specular highlights |
| 5 | Surface Interaction | SDF collision detection, flow-around, climb-over, squeeze-between |
| 6 | Material & Shading | PBR wet/glossy material, SSS approximation, semi-transparency, shadow casting |
| 7 | Input, Camera & Polish | Mouse/touch attractor, auto-framing camera, color grading, DOF, AO, idle animation, 60fps |
| 8 | Visual Matching & Refinement | Playwright comparison, iterative tuning, cross-browser testing, final optimization |

## Success Criteria

**Functionality:**
- Organism responds to mouse/touch input with organic spurt-based movement
- Real-time reaction-diffusion Turing patterns animate on organism surface
- Eyes track cursor with organic, living movement
- Organism properly interacts with all environment geometry (flow, climb, squeeze)
- Idle animation plays when no input is detected
- Camera auto-frames organism appropriately

**User Experience:**
- Feels alive and organic — not mechanical or digital
- Movement is satisfying and matches the video reference
- Immediate response to input with appropriate organic delay
- Works with both mouse and touch input

**Technical Quality:**
- Stable 60fps on modern hardware
- No visual glitches or rendering artifacts
- Works across major browsers with WebGL 2.0
- Single HTML file, no external dependencies at runtime

**Design Polish:**
- Visually indistinguishable from reference cosmodernism videos
- Matching color palette, textures, lighting, and material quality
- Photorealistic wet/glossy appearance
- Living Turing pattern texture that evolves organically

## Reference Material

- `cosmodernism_01.mp4` — primary reference (453 frames → `./frames/video01/`)
- `cosmodernism_02.mp4` — additional context (676 frames → `./frames/video02/`)

**Key Visual Elements:**
- Reaction-diffusion / Turing pattern: coral-brain-like maze texture in pink/magenta on dark body
- Multiple compound eyes: glossy dark spheres with pink/magenta irises
- Wet, gelatinous surface with specular highlights
- Yellow perforated pegboard background with raised blocks and measurement markings
- Organic slug/amoeba-like movement with trailing pseudopods

## Future Considerations (Not In Current Scope)

These inform architectural decisions only (e.g., locomotion system should be flexible enough to support multiple instances later):
- Multiple organisms controlled by different players
- Collectible items (magenta orbs) on the surface
- Consuming smaller slimes to grow larger
- Camera zoom-out as organisms grow
- Network synchronization of physics state

## Feature Categories

| Category | Features | Status |
|----------|----------|--------|
| [Infrastructure](01-infrastructure.md) | 5 | ✅ All passing |
| [Environment Rendering](02-environment-rendering.md) | 7 | ✅ All passing |
| [Organism Body](03-organism-body.md) | 6 | ✅ All passing |
| [Turing Pattern](04-turing-pattern.md) | 3 | ✅ All passing |
| [Eye System](05-eye-system.md) | 3 | ✅ All passing |
| [Surface Interaction](06-surface-interaction.md) | 3 | ✅ All passing |
| [Material Shading](07-material-shading.md) | 4 | ✅ All passing |
| [Camera System](08-camera-system.md) | 2 | ✅ All passing |
| [Input System](09-input-system.md) | 3 | ✅ All passing |
| [Visual Polish](10-visual-polish.md) | 3 | ✅ All passing |
| [Performance](11-performance.md) | 2 | ✅ All passing |
| [Responsive Layout](12-responsive-layout.md) | 2 | ✅ All passing |
| [Error Handling](13-error-handling.md) | 2 | ✅ All passing |
| [State Persistence](14-state-persistence.md) | 2 | ✅ All passing |
| [Accessibility](15-accessibility.md) | 1 | ✅ All passing |
| [Visual Fidelity](16-visual-fidelity.md) | 2 | ✅ All passing |

## Dependency Graph (Summary)

Features 1–5 (Infrastructure) are foundational — all other features depend on them. From there:
- **Environment** (6–12) depends on Infrastructure
- **Organism Body** (13–18) depends on Infrastructure + Environment base (6)
- **Turing Pattern** (19–21) depends on Organism (13)
- **Eye System** (22–24) depends on Organism + Head (13, 14)
- **Surface Interaction** (25–27) depends on Organism + Environment blocks/SDF (8, 12, 13, 17)
- **Material Shading** (28–31) depends on Organism + Lighting
- **Camera** (32–33) depends on Organism + Viscous drag (17)
- **Input** (34–36) depends on Organism
- **Visual Polish** (37–38, 50) depends on multiple visual systems
- **Visual Fidelity** (48–49) depends on most visual systems
