# Organism Body

## Spec Requirements

> **From app spec — organism_body:**
> - Soft-body physics simulation with mass-spring or position-based dynamics
> - Distinct head region (bulbous, leading the movement)
> - Body region with smooth volume that follows the head
> - Trailing pseudopods/tentacles that stretch and thin out behind the body
> - Metaball/implicit surface rendering for fluid, blobby shape
> - Viscous drag physics — body follows head with realistic delay
> - Spurt-based locomotion — movement happens in organic bursts, not constant velocity
> - Idle animation — organism stays in place but continues to breathe/pulse/animate when no input
> - Realistic deformation when interacting with environment geometry
> - Stretching behavior when head moves away from body mass
>
> **Color Palette:**
> - Organism body: Deep burgundy/black (#1A0008 to #3D0015)
>
> **Implementation Phase 2:** Implement soft-body physics (mass-spring or PBD). Metaball/implicit surface rendering for blobby shape. Head, body, and pseudopod anatomy. Stretching and deformation behavior. Viscous drag and spurt-based locomotion.
>
> **Future Consideration:** Locomotion system should be flexible enough to support multiple organism instances later.

---

## Feature 13: Organism body renders as a dark blobby shape on the surface
**Priority:** 13 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 6

The slime organism must render as a visible dark burgundy/black blobby shape using metaball/implicit surface rendering, clearly distinct from the yellow background.

### Steps
1. Open the application and wait for rendering
2. Take a screenshot
3. Verify a dark shape (burgundy/black, RGB where R<100, G<30, B<30) is visible on the yellow surface
4. Verify the shape has smooth, organic blobby edges (not sharp geometric edges)
5. Verify the shape is clearly distinct from the background
6. Compare organism appearance with reference frames

---

## Feature 14: Organism has distinct head region
**Priority:** 14 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 13

The organism must have a visually distinct bulbous head region that leads movement, larger and more defined than the rest of the body.

### Steps
1. Open the application and move mouse to one side of the canvas
2. Wait for organism to begin moving toward the mouse
3. Take a screenshot during movement
4. Verify the leading edge of the organism (head) is bulbous/rounded and larger
5. Verify the head region is distinct from the trailing body
6. Compare head shape with reference frames showing organism in motion

---

## Feature 15: Trailing pseudopods stretch behind organism during movement
**Priority:** 15 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 13, 14

When the organism moves, trailing pseudopods/tentacles should stretch out behind the body, thinning as they extend.

### Steps
1. Open the application
2. Move mouse quickly to the opposite side of the canvas to create rapid movement
3. Wait 500ms for organism to respond
4. Take a screenshot
5. Verify thin, stretched trailing extensions visible behind the main body mass
6. Verify pseudopods are thinner than the main body
7. Verify pseudopods connect smoothly to the body (no disconnected fragments)
8. Compare with reference frames showing stretched organism

---

## Feature 16: Organism moves toward mouse position with spurt-based locomotion
**Priority:** 16 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 13

The organism head must move toward the mouse/cursor position using organic spurt-based locomotion - movement in bursts, not constant velocity.

### Steps
1. Open the application
2. Position mouse at center, wait for organism to settle
3. Move mouse to a new position (e.g., top-right corner)
4. Take rapid sequential screenshots (every 100ms for 2 seconds)
5. Analyze movement: verify organism moves in bursts/spurts, not at constant speed
6. Verify organism head reaches or approaches the mouse position
7. Verify movement looks organic, not linear/mechanical
8. Compare movement pattern with reference video locomotion style

---

## Feature 17: Viscous drag causes body to follow head with delay
**Priority:** 17 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 13, 16

The body mass should follow the head with a realistic viscous delay - the head leads and the body catches up over time, creating a stretching effect.

### Steps
1. Open the application, wait for organism to settle
2. Move mouse rapidly to a far position
3. Take a screenshot immediately (within 200ms) - body should still be near original position while head has moved
4. Take another screenshot after 1 second - body should have partially caught up
5. Take another screenshot after 3 seconds - body should be mostly caught up
6. Verify the stretch-and-contract behavior matches organic viscous motion
7. Compare with reference frames

---

## Feature 18: Idle animation plays when no input detected
**Priority:** 18 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 13

When no mouse/touch input is present, the organism should remain in place but display subtle idle animation (breathing, pulsing, slight movement) - not be completely static.

### Steps
1. Open the application and do NOT move the mouse
2. Wait 3 seconds for any initial animation to settle
3. Take screenshot A
4. Wait 2 more seconds without any input
5. Take screenshot B
6. Compare A and B - they must NOT be pixel-identical (organism should be animating)
7. Verify the organism stays approximately in the same position (not wandering)
8. Verify the animation is subtle (breathing/pulsing), not erratic movement
