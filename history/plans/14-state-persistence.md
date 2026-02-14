# State Persistence

## Feature 45: Organism state survives page visibility change
**Priority:** 45 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 13

When the page loses and regains visibility (e.g., switching tabs), the simulation should resume smoothly without resetting the organism position.

### Steps
1. Open the application and move organism to a specific position
2. Take screenshot A (organism position noted)
3. Trigger page visibility change event to simulate tab switch
4. Wait 2 seconds
5. Restore visibility
6. Take screenshot B
7. Verify organism is approximately at the same position (not reset to origin)
8. Verify rendering resumes without artifacts or errors

---

## Feature 46: Animation loop handles requestAnimationFrame correctly
**Priority:** 46 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5

The animation loop must use requestAnimationFrame properly with delta-time, so the simulation runs at the same speed regardless of frame rate variations.

### Steps
1. Open the application
2. Examine source code for requestAnimationFrame usage
3. Verify delta-time (time since last frame) is calculated and used in physics updates
4. Verify the animation loop does not use setInterval or setTimeout for rendering
5. Verify physics simulation is framerate-independent (uses dt, not fixed step without dt)
6. Verify the animation loop properly handles long frame gaps (e.g., after tab switch)
