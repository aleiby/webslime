# Infrastructure

## Spec Requirements

> **Technology:** Vanilla JavaScript, WebGL 2.0 with GLSL shaders, single standalone HTML file with embedded JS/CSS. No framework, no backend, no external runtime dependencies.
>
> **UI Layout:** Full-viewport WebGL canvas with no UI chrome. The entire browser window is the simulation viewport. No menus, buttons, or overlays — pure immersive visual experience. Canvas fills entire browser viewport, responsive to window resize, maintains aspect ratio appropriate to organism framing.
>
> **Implementation Phase 1:** Set up single HTML file with WebGL 2.0 context. Playwright screenshot comparison pipeline against reference frames.

---

## Feature 1: Static file server serves index.html
**Priority:** 1 | **Status:** ✅ Passing | **Dependencies:** None

Verify that a static file server can serve the single HTML file application and it loads in the browser without 404 errors.

### Steps
1. Start a static file server (e.g., npx serve or python -m http.server) in the project directory
2. Navigate to http://localhost:<port>/index.html in Playwright
3. Verify HTTP 200 response
4. Verify page title or `<canvas>` element exists in DOM
5. Verify no console errors on load

---

## Feature 2: WebGL 2.0 context initializes successfully
**Priority:** 2 | **Status:** ✅ Passing | **Dependencies:** None

Verify that the application creates a WebGL 2.0 rendering context on the canvas element without falling back to WebGL 1.0 or failing.

### Steps
1. Open the application in Playwright
2. Execute JS: `document.querySelector('canvas').getContext('webgl2') !== null`
3. Verify the result is true (WebGL 2.0 context exists)
4. Check console for any WebGL context creation errors
5. Verify no 'webgl' (v1) fallback warnings in console

---

## Feature 3: Application is a single standalone HTML file
**Priority:** 3 | **Status:** ✅ Passing | **Dependencies:** None

Verify the entire application is contained in a single HTML file with embedded JavaScript and CSS - no external JS/CSS file dependencies at runtime.

### Steps
1. Check that index.html exists in the project root
2. Verify index.html contains script tags with inline JavaScript (not src= external files)
3. Verify index.html contains style tags with inline CSS (not href= external stylesheets)
4. Open the application and check network requests - no .js or .css file requests should appear
5. Verify the HTML file is self-contained (all shaders, styles, and logic embedded)

---

## Feature 4: No mock data or placeholder patterns in codebase
**Priority:** 4 | **Status:** ✅ Passing | **Dependencies:** None

Verify the codebase does not contain mock data patterns, TODO stubs, or placeholder implementations.

### Steps
1. Run grep for mockData, fakeData, sampleData, dummyData, placeholder in HTML and JS files
2. Run grep for TODO real, TODO implement, STUB, MOCK, FIXME implement in HTML and JS files
3. Run grep for hardcoded, fake data, dummy texture in HTML and JS files
4. ALL grep commands must return empty (exit code 1)
5. If any returns results, investigate and fix before passing

---

## Feature 5: Canvas fills entire viewport with no UI chrome
**Priority:** 5 | **Status:** ✅ Passing | **Dependencies:** None

Verify the WebGL canvas fills the full browser viewport with no visible UI elements, menus, buttons, or overlays - pure immersive simulation.

### Steps
1. Open the application in Playwright at 1920x1080
2. Verify a canvas element exists
3. Verify canvas width equals window.innerWidth
4. Verify canvas height equals window.innerHeight
5. Verify no other visible DOM elements (buttons, menus, headers, footers) exist outside the canvas
6. Verify body margin/padding is 0
7. Verify no scrollbars appear
