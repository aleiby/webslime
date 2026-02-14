# Turing Pattern

## Spec Requirements

> **From app spec — turing_pattern:**
> - Real-time reaction-diffusion simulation (Gray-Scott or similar model) running on GPU
> - GPU compute via fragment shaders with ping-pong framebuffer technique
> - Turing pattern mapped onto organism body surface in UV space
> - Organic color palette: pink/magenta pattern lines on dark burgundy/black body
>
> **Color Palette:**
> - Turing pattern: Pink/magenta lines (#C84080 to #E05090)
>
> **Reference Visual:** Coral-brain-like maze texture in pink/magenta on dark body
>
> **Implementation Phase 3:** Implement GPU reaction-diffusion simulation (ping-pong framebuffers). Map Turing pattern onto organism body in UV space. Tune parameters to match reference video pattern style. Animate pattern evolution in real-time.

---

## Feature 19: Reaction-diffusion Turing pattern visible on organism surface
**Priority:** 19 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 13

A visible reaction-diffusion (Turing) pattern must appear on the organism body - coral/maze-like pink/magenta lines on the dark body surface.

### Steps
1. Open the application and wait for rendering to stabilize
2. Take a close screenshot focusing on the organism body
3. Verify pink/magenta colored pattern lines visible on the dark organism body
4. Verify the pattern has a maze-like or coral-brain-like structure (not random noise)
5. Verify pattern colors match spec: pink/magenta (#C84080 to #E05090) on dark burgundy/black
6. Compare pattern style with reference frames showing Turing pattern detail

---

## Feature 20: Turing pattern animates and evolves in real-time
**Priority:** 20 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 19

The reaction-diffusion pattern must not be static - it should visibly animate and evolve over time as the GPU simulation runs.

### Steps
1. Open the application and wait for initial render
2. Take screenshot A of the organism body pattern
3. Wait 3 seconds without moving mouse
4. Take screenshot B of the organism body pattern
5. Compare pattern details between A and B - pattern lines should have shifted/evolved
6. Verify the pattern changes are smooth and organic, not flickering or random
7. Verify pattern maintains its coral/maze character while evolving

---

## Feature 21: Turing pattern uses GPU ping-pong framebuffer technique
**Priority:** 21 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 19

The reaction-diffusion simulation must run on the GPU using fragment shaders with ping-pong framebuffer technique for efficient computation.

### Steps
1. Open the application in Playwright
2. Check WebGL state: verify at least 2 framebuffer objects are created (for ping-pong)
3. Execute JS to inspect WebGL extension usage or shader program count
4. Verify source code contains fragment shader code for reaction-diffusion computation
5. Verify source code references framebuffer ping-pong or double-buffering pattern
6. Verify no CPU-side pixel manipulation for the pattern (all GPU-based)
