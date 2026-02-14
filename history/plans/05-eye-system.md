# Eye System

## Spec Requirements

> **From app spec — eye_system:**
> - Multiple glossy spherical eyes clustered on head region
> - Eyes organically track cursor position (smooth, living movement — not mechanical)
> - Reflective specular highlights on eye surfaces
> - Dark iris/pupil with magenta/pink coloring matching reference
> - Eyes maintain organic arrangement as body deforms
>
> **Color Palette:**
> - Eyes: Dark glossy black with magenta/pink iris (#D03070)
>
> **Reference Visual:** Multiple compound eyes: glossy dark spheres with pink/magenta irises
>
> **Implementation Phase 4:** Render multiple glossy spherical eyes on head region. Implement organic cursor tracking. Specular highlights and reflections on eye surfaces. Maintain eye arrangement during body deformation.

---

## Feature 22: Multiple eyes render on organism head region
**Priority:** 22 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 13, 14

Multiple glossy spherical eyes must be visible on the organism's head region, creating a cluster of dark glossy spheres.

### Steps
1. Open the application and wait for rendering
2. Take a screenshot focusing on the organism head area
3. Identify multiple circular/spherical eye shapes on the head region
4. Verify at least 3 eyes are visible
5. Verify eyes have glossy/reflective specular highlights (bright spots)
6. Verify eyes are dark/black with pink/magenta iris coloring
7. Compare eye appearance and arrangement with reference frames

---

## Feature 23: Eyes track cursor position with organic movement
**Priority:** 23 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 22

The eyes must track/follow the mouse cursor position with smooth, organic, living movement - not mechanical snapping.

### Steps
1. Open the application and position mouse at center
2. Take screenshot A showing eye orientations
3. Move mouse to the left side of the canvas
4. Wait 500ms for eyes to respond
5. Take screenshot B
6. Verify eye orientations have changed to look toward the new mouse position
7. Move mouse to the right side
8. Wait 500ms
9. Take screenshot C
10. Verify eyes are now oriented toward the right
11. Verify eye movement appears smooth and organic, not instant/mechanical

---

## Feature 24: Eyes maintain arrangement as body deforms
**Priority:** 24 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 17, 22

As the organism body deforms during movement, the eyes must maintain a sensible organic arrangement on the head, not scatter randomly or clip through the body.

### Steps
1. Open the application, wait for organism to settle
2. Take screenshot showing eyes at rest
3. Move mouse rapidly to stretch the organism
4. Take screenshots during deformation
5. Verify eyes remain clustered on the head region (not scattered across body)
6. Verify no eyes clip through or float outside the body surface
7. Verify eye cluster deforms organically with the head shape
