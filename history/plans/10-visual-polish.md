# Visual Polish

## Spec Requirements

> **From app spec — visual_polish:**
> - Color grading matching reference videos (yellow/burgundy/magenta palette)
> - Depth of field effect for cinematic look
> - Ambient occlusion where organism meets surface
> - Overall visual fidelity matching reference video frames
>
> **Implementation Phase 7:** Color grading pass. Depth of field. Ambient occlusion.
>
> **Implementation Phase 8:** Side-by-side comparison with reference frames using Playwright. Iterative tuning of colors, patterns, materials, physics.

---

## Feature 37: Color grading matches reference video palette
**Priority:** 37 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 6, 13, 19

The overall color grading of the scene must match the cosmodernism video reference - yellow/burgundy/magenta palette with warm lighting.

### Steps
1. Open the application and take a full-viewport screenshot
2. Compare overall color tone with reference frames from ./frames/video01/
3. Verify yellow background is in the correct saturation range (not washed out or neon)
4. Verify organism dark tones match reference (deep burgundy, not pure black)
5. Verify magenta/pink tones on Turing pattern match reference
6. Verify overall warm color temperature of the scene
7. Verify high contrast between organism and background matches reference

---

## Feature 38: Ambient occlusion where organism meets surface
**Priority:** 38 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 13, 30

There must be visible ambient occlusion darkening where the organism body contacts the pegboard surface, adding depth and grounding.

### Steps
1. Open the application and take a screenshot
2. Examine the contact area where organism meets the yellow surface
3. Verify a subtle darkening effect is visible at the contact region
4. Verify the darkening is gradual (not a hard shadow line)
5. Verify AO effect is consistent around the organism perimeter
6. Compare with reference frames showing organism-surface contact

---

## Feature 50: Depth of field effect for cinematic look
**Priority:** 50 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 13, 37

The rendered scene must include a depth of field effect that blurs elements at different depths, creating a cinematic, photographic look matching the reference videos.

### Steps
1. Open the application and take a screenshot
2. Examine the scene for depth-based blur effects
3. Verify areas at different depths from the camera have different sharpness levels
4. Verify the organism (at focal point) is sharp while distant or very close elements may be softly blurred
5. Verify the DOF effect is subtle and cinematic (not exaggerated or distracting)
6. Compare the overall cinematic quality with reference frames from ./frames/video01/
