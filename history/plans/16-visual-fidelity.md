# Visual Fidelity

## Spec Requirements

> **Design System — Color Palette:**
> - Background/Surface: Bright saturated yellow (#D4C800 to #E8D800 range)
> - Organism body: Deep burgundy/black (#1A0008 to #3D0015)
> - Turing pattern: Pink/magenta lines (#C84080 to #E05090)
> - Eyes: Dark glossy black with magenta/pink iris (#D03070)
> - Surface grime: Muted olive/brown tones
> - Specular highlights: White/cream (#FFFFF0)
> - Ambient: Warm yellow-orange lighting
>
> **Visual Style:** Photorealistic rendering matching the cosmodernism video aesthetic. High contrast between the organic creature and the industrial surface. Wet, glistening, alive appearance throughout.
>
> **Success Criteria — Design Polish:**
> - Visually indistinguishable from reference cosmodernism videos
> - Matching color palette, textures, lighting, and material quality
> - Photorealistic wet/glossy appearance
> - Living Turing pattern texture that evolves organically
>
> **Reference Frames:** `./frames/video01/` (453 frames), `./frames/video02/` (676 frames)
>
> **Implementation Phase 8:** Side-by-side comparison with reference frames using Playwright. Iterative tuning of colors, patterns, materials, physics.

---

## Feature 48: Organism color palette matches reference: burgundy/black body
**Priority:** 48 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 13, 37

The organism body color must match the reference videos - deep burgundy/black (#1A0008 to #3D0015), not flat black or bright colors.

### Steps
1. Open the application and take a screenshot
2. Sample pixels from the darkest regions of the organism body
3. Verify dominant body color is in the deep burgundy range (R: 20-70, G: 0-20, B: 5-25)
4. Verify body is NOT pure black (#000000)
5. Verify body is NOT flat single-color (should have tonal variation from lighting)
6. Compare body color with reference frames

---

## Feature 49: Overall scene matches reference frame visual quality
**Priority:** 49 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 6, 13, 19, 22, 28, 30, 37

The complete rendered scene (environment + organism + lighting) must achieve visual fidelity comparable to the reference cosmodernism video frames.

### Steps
1. Open the application and take a full-viewport screenshot
2. Load a reference frame from ./frames/video01/frame_0100.jpg
3. Compare overall composition: yellow background, dark organism, raised blocks
4. Verify color palette similarity (yellows, burgundies, magentas)
5. Verify lighting quality (directional light, shadows, highlights)
6. Verify organism visual quality (glossy, wet, Turing pattern visible, eyes visible)
7. Verify environment quality (pegboard texture, block details, shadows)
8. Rate overall visual similarity - scene should be recognizably similar to reference
9. Document any major visual discrepancies for future refinement
