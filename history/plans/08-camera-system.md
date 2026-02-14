# Camera System

## Spec Requirements

> **From app spec — camera_system:**
> - Auto-framing that keeps entire organism visible
> - Smooth zoom-out as organism elongates/stretches
> - Smooth zoom-in as organism contracts/settles
>
> **Implementation Phase 7:** Auto-framing camera with zoom.

---

## Feature 32: Auto-framing keeps entire organism visible
**Priority:** 32 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 13, 17

The camera system must automatically frame to keep the entire organism visible at all times - no parts should be cut off at canvas edges.

### Steps
1. Open the application
2. Move mouse to center - verify organism fully visible
3. Move mouse to top-left corner - wait for organism to follow
4. Verify entire organism is still within the visible canvas (no parts cut off)
5. Move mouse to bottom-right corner - wait
6. Verify entire organism still fully visible
7. Move mouse to stretch organism across a large area
8. Verify camera zooms out enough to keep all parts visible

---

## Feature 33: Camera zooms smoothly during organism stretch and contract
**Priority:** 33 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 32

The camera must smoothly zoom out when the organism stretches/elongates and zoom back in when it contracts, with no jarring jumps.

### Steps
1. Open the application, organism at rest
2. Take screenshot A (initial zoom level)
3. Move mouse far from organism to cause stretching
4. Take screenshot B (should be zoomed out more)
5. Verify visible area in B is larger than A (zoomed out)
6. Return mouse near organism center
7. Wait for organism to contract
8. Take screenshot C (should zoom back in)
9. Verify zoom transitions are smooth (no sudden jumps between screenshots)
