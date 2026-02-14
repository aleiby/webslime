# Responsive Layout

## Spec Requirements

> **From app spec — ui_layout:**
> - Canvas fills entire browser viewport
> - Responsive to window resize
> - Maintains aspect ratio appropriate to organism framing
>
> **Full-viewport WebGL canvas with no UI chrome.** The entire browser window is the simulation viewport. No menus, buttons, or overlays — pure immersive visual experience.

---

## Feature 41: Canvas resizes correctly on window resize
**Priority:** 41 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5

When the browser window is resized, the WebGL canvas must resize to fill the new viewport dimensions without distortion or black bars.

### Steps
1. Open the application at 1920x1080
2. Verify canvas fills viewport
3. Resize window to 1280x720
4. Verify canvas width now equals 1280 and height equals 720
5. Verify no black bars or unused space around the canvas
6. Verify WebGL viewport is updated (no stretched/distorted rendering)
7. Resize to 800x600
8. Verify same correct behavior at smaller size
9. Verify rendering is not distorted or cropped after resize

---

## Feature 42: Simulation renders correctly at mobile viewport (375x667)
**Priority:** 42 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 41

The simulation must render correctly on mobile-sized viewports without errors, distortion, or performance degradation.

### Steps
1. Open the application at 375x667 viewport (iPhone SE size)
2. Verify canvas fills the viewport
3. Verify organism is visible and correctly rendered
4. Verify no rendering distortion or aspect ratio issues
5. Verify the simulation runs without console errors
6. Verify touch interaction works at this viewport size
