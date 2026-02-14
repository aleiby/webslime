# Input System

## Spec Requirements

> **From app spec — input_system:**
> - Mouse position acts as attraction force on organism head
> - Touch input acts as attraction force on organism head
> - Attraction force model produces organic spurt-like response
> - No interaction = organism remains in place with idle animation (does not wander)
>
> **Success Criteria — User Experience:**
> - Feels alive and organic — not mechanical or digital
> - Immediate response to input with appropriate organic delay
> - Works with both mouse and touch input
>
> **Implementation Phase 7:** Mouse and touch attractor input.

---

## Feature 34: Mouse position acts as attraction force on organism
**Priority:** 34 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 13

The mouse cursor position must act as an attraction point, pulling the organism head toward it.

### Steps
1. Open the application, organism at rest in center area
2. Move mouse to top-right quadrant of canvas
3. Wait 3 seconds
4. Take a screenshot
5. Verify organism has moved toward the top-right (closer to mouse position)
6. Move mouse to bottom-left quadrant
7. Wait 3 seconds
8. Take another screenshot
9. Verify organism has moved toward bottom-left

---

## Feature 35: Touch input acts as attraction force on organism
**Priority:** 35 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 34

Touch input (simulated via Playwright) must act as an equivalent attraction force to mouse input.

### Steps
1. Open the application on a simulated touch device viewport
2. Simulate a touch event at the top-right corner of the canvas
3. Wait 3 seconds
4. Take a screenshot
5. Verify organism has moved toward the touch position
6. Simulate a touch at the bottom-left corner
7. Wait 3 seconds
8. Take a screenshot
9. Verify organism has moved toward the new touch position

---

## Feature 36: No input results in organism staying in place with idle animation
**Priority:** 36 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 18, 34

When no mouse or touch input is detected, the organism must stay in its current position (not wander) while still showing idle animation.

### Steps
1. Open the application
2. Move mouse to position organism at a specific location
3. Wait 2 seconds for organism to settle
4. Record organism center position (screenshot A)
5. Move mouse completely outside the canvas window (or to a neutral position)
6. Wait 5 seconds without any input
7. Record organism center position (screenshot B)
8. Verify organism center position has not significantly moved (stayed in place)
9. Verify organism is still animating (not static - idle animation playing)
