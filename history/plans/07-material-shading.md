# Material Shading

## Spec Requirements

> **From app spec — material_shading:**
> - Wet, glossy surface appearance with high specularity
> - Specular highlights that shift as organism moves
> - Sub-surface scattering look for translucent fleshy appearance
> - Shadow casting from organism onto the yellow surface
> - Semi-transparency at thin edges (pseudopod tips, stretched regions)
>
> **Color Palette:**
> - Specular highlights: White/cream (#FFFFF0)
>
> **Visual Style:** Photorealistic rendering matching the cosmodernism video aesthetic. High contrast between the organic creature and the industrial surface. Wet, glistening, alive appearance throughout.
>
> **Reference Visual:** Wet, gelatinous surface with specular highlights
>
> **Implementation Phase 6:** Wet glossy PBR-style material for organism. Sub-surface scattering approximation. Semi-transparency at thin edges. Shadow casting onto surface. Specular highlight system.

---

## Feature 28: Organism has wet glossy surface appearance
**Priority:** 28 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 13

The organism must have a wet, glossy surface with visible specular highlights, matching the reference videos' glistening appearance.

### Steps
1. Open the application and take a screenshot
2. Examine the organism body surface for specular highlights (bright white/cream spots)
3. Verify at least one visible specular highlight on the body
4. Verify the surface appears wet/glossy (not matte or flat-shaded)
5. Verify specular highlights are in the correct color (#FFFFF0 range)
6. Compare glossiness with reference frames

---

## Feature 29: Specular highlights shift as organism moves
**Priority:** 29 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 17, 28

The specular highlights on the organism surface must shift position as the organism moves and deforms, demonstrating dynamic lighting interaction.

### Steps
1. Open the application and take screenshot A at rest
2. Note position of specular highlights on the organism
3. Move mouse to cause organism movement
4. Take screenshot B during movement
5. Verify specular highlight positions have changed relative to the organism body
6. Verify highlights appear natural and track lighting direction correctly

---

## Feature 30: Organism casts shadow onto yellow surface
**Priority:** 30 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 9, 13

The organism must cast a visible shadow onto the yellow pegboard surface beneath it, creating depth and grounding the creature in the scene.

### Steps
1. Open the application and take a screenshot
2. Examine the area on the yellow surface directly around/under the organism
3. Verify a darker shadow region exists on the surface near/under the organism
4. Verify the shadow is softer than a hard pixel-edge (some blur/falloff)
5. Verify shadow moves with the organism when it moves
6. Compare shadow quality with reference frames

---

## Feature 31: Semi-transparency at thin edges and pseudopod tips
**Priority:** 31 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 15, 28

At thin edges of the organism, especially pseudopod tips and stretched regions, the body should show semi-transparency where the yellow surface shows through.

### Steps
1. Open the application
2. Move mouse to stretch the organism creating thin pseudopods
3. Take a screenshot focusing on the thin trailing edges
4. Verify pseudopod tips are more transparent than the main body (surface shows through)
5. Verify the transition from opaque body to transparent tips is gradual, not abrupt
6. Compare with reference frames showing thin organism edges
