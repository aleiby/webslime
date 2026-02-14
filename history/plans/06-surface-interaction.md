# Surface Interaction

## Spec Requirements

> **From app spec — surface_interaction:**
> - Organism flows around obstacles like liquid when encountering blocks
> - Organism climbs over smaller blocks (3D interaction)
> - Organism squeezes between gaps in the environment
> - Interaction with pegboard holes (body surface deforms around bumps)
> - Proper collision response — no clipping through geometry
>
> **Implementation Phase 5:** Collision detection between organism and environment SDF geometry. Flow-around behavior for large obstacles. Climb-over behavior for small blocks. Squeeze-between behavior for gaps. Deformation around pegboard bumps.

---

## Feature 25: Organism flows around large obstacles
**Priority:** 25 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 8, 12, 13, 17

When the organism encounters large rectangular blocks, it should flow around them like a liquid rather than clipping through them.

### Steps
1. Open the application
2. Identify a large block in the environment
3. Move mouse to the other side of the block, forcing organism to navigate around it
4. Take sequential screenshots during navigation
5. Verify organism body flows around the block (not through it)
6. Verify no body mass clips or penetrates the block geometry
7. Verify the flowing motion looks organic and fluid
8. Compare with reference video showing obstacle interaction

---

## Feature 26: Organism squeezes between gaps in environment
**Priority:** 26 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 13, 25

The organism should be able to squeeze through gaps between blocks, deforming its body to fit through narrow spaces.

### Steps
1. Open the application
2. Identify a gap between two blocks
3. Move mouse to guide organism through the gap
4. Take screenshots during the squeeze maneuver
5. Verify organism body deforms to fit through the gap
6. Verify organism body thins/narrows in the gap area
7. Verify no clipping through the block geometry
8. Verify organism reforms its shape after passing through the gap

---

## Feature 27: No clipping through any environment geometry
**Priority:** 27 | **Status:** ✅ Passing | **Dependencies:** 1, 2, 3, 4, 5, 13, 25

The organism body must never clip through or penetrate any environment geometry - blocks, bumps, or surface edges.

### Steps
1. Open the application
2. Move mouse rapidly in various directions to create dynamic movement
3. Take 10 screenshots at 500ms intervals during rapid movement
4. Examine each screenshot for any body penetration through blocks
5. Verify no organism pixels overlap with block interior pixels
6. Test near edges of the environment
7. Test near tightly packed blocks
8. Verify collision response is consistent across all interactions
