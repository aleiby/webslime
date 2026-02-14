# Performance

## Spec Requirements

> **From app spec — performance:**
> - Stable 60fps on modern hardware
> - WebGL 2.0 compatibility across major browsers (Chrome, Firefox, Safari, Edge)
>
> **Success Criteria — Technical Quality:**
> - Stable 60fps on modern hardware
> - No visual glitches or rendering artifacts
> - Works across major browsers with WebGL 2.0
> - Single HTML file, no external dependencies at runtime
>
> **Implementation Phase 7:** Performance optimization to 60fps.
>
> **Implementation Phase 8:** Cross-browser testing (Chrome, Firefox, Safari, Edge). Final performance optimization pass.

---

## Feature 39: Simulation runs at stable 60fps on modern hardware
**Priority:** 39 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 13, 17

The WebGL simulation must maintain a stable 60fps framerate during normal interaction on modern hardware.

### Steps
1. Open the application in Playwright
2. Wait for initial render to stabilize (3 seconds)
3. Use requestAnimationFrame timing to measure FPS over 5 seconds of idle
4. Verify average FPS is >= 55 (allowing small variance from 60)
5. Move mouse to trigger organism movement and re-measure FPS for 5 seconds
6. Verify average FPS during movement is still >= 50
7. Verify no individual frame takes longer than 50ms (no major hitches)
8. Check console for any WebGL performance warnings

---

## Feature 40: No WebGL errors or warnings in console during operation
**Priority:** 40 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 13

The application must run without any WebGL errors, warnings, or context lost events during normal operation.

### Steps
1. Open the application and set up console message monitoring
2. Wait for initial render (3 seconds)
3. Perform normal mouse interactions for 10 seconds (moving, clicking)
4. Collect all console messages
5. Verify no WebGL error messages (INVALID_OPERATION, INVALID_VALUE, etc.)
6. Verify no shader compilation errors
7. Verify no context lost events
8. Verify no uncaught JavaScript exceptions
