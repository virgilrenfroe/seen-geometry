# Seen Geometry

Interactive WebGL pictures for a classroom. Each page shows one idea about geometric transforms, so a student can see the picture change when the numbers change.

## Who made this

An educator directed AI agents to build these pages. The author is not a software engineer and does not hold a mathematics appointment. Treat the demos as teaching aids: classroom pictures with plain captions, not a textbook and not a credentialed math text.

## Lessons

| Page | What a student should see |
| --- | --- |
| [Hub](index.html) | The table of contents. |
| [01 Instanced field](demos/01-instanced-field.html) | One box, many matrices, one draw call. Tap a block and read its matrix. |
| [02 Morph targets](demos/02-morph-targets.html) | Two blend shapes, spike and squash, added with sliders. |
| [03 Order of transforms](demos/03-compose-transforms.html) | The same translate, rotate, and scale, multiplied in three orders. |
| [04 Point vs direction](demos/04-point-vs-direction.html) | One arrow as a point (w = 1) and as a direction (w = 0). Translation moves only the point. |
| [05 Shear](demos/05-shear.html) | A shear slider. The area of the unit square stays 1 while the corner angle changes. |
| [06 Determinant and reflection](demos/06-determinant.html) | Drag i and j. The area of the image is \|det\|. A negative determinant mirrors the F. Zero flattens it onto a line. |
| [07 Fold](demos/07-fold.html) | Drag a crease. One half folds over the line. The reflection has determinant −1, so the mark flips. An offset line is a slide, a reflection, and a slide back. |
| [08 Rotation](demos/08-rotation.html) | Drag a point on the unit circle. The rotation matrix has determinant 1. Two folds make that turn: twice the angle between the creases. |
| [09 Projection](demos/09-projection.html) | A house drops onto a plane. Switch among top, front, and side. One row of the matrix is zeros and the determinant stays 0. Tilt the plane and the determinant stays 0. |
| [10 Perspective](demos/10-perspective.html) | Move the eye closer or farther. Read one corner before the divide by w and after it. Depth lines meet at a vanishing point on the horizon. |
| [11 Inverse](demos/11-inverse.html) | Apply a shear, a turn, or a scale, then apply the inverse. The product is the identity. Flatten: the determinant is 0, so there is no inverse. |
| [12 Eigenvectors](demos/12-eigenvectors.html) | A field of arrows under a 2×2 matrix. Red arrows stay on their line and stretch by λ. The stretch preset has λ = 3 and λ = 1. A turn has no real eigenvector. |
| [13 Dot product](demos/13-dot-product.html) | Drag arrows a and b. Read a·b = \|a\|\|b\|cos θ, the angle, and the shadow of a on b. With a = (3, 0) and b = (2, 2), the dot product is 6 and the angle is 45°. At 90° the dot product is 0. |
| [14 Cross product](demos/14-cross-product.html) | Drag arrows a and b in the plane. The red arrow is a × b and stands perpendicular to both. Its length is the area \|a\|\|b\|sin θ. With a = (3, 0, 0) and b = (0, 2, 0), the cross product is (0, 0, 6) and the area is 6. Swap the arrows and it becomes (0, 0, −6). |
| [15 Orthonormal basis](demos/15-orthonormal.html) | Start with u = (3, 1) and v = (1, 2). Gram-Schmidt keeps a unit arrow along u, subtracts the shadow of v, and normalizes the remainder. |e1| and |e2| are 1, and e1 · e2 is 0. Add e3 = e1 × e2 for a right-handed frame. |
| [16 Change of basis](demos/16-change-of-basis.html) | v = (3, 1) stays fixed. Turn the frame. At 45°, the page pair is (3, 1) and the frame pair is about (2.83, −1.41). The squares of the frame coordinates add up to \|v\|². At 0° the two pairs match. |

Each lesson has a short note, “Where this is used.” It names fields and jobs where the idea appears.

On a wide screen, demo 03 can show all three orders at once. The tail positions are listed either way. Demo 04 can show the point and the direction side by side.

A useful order for a class:

1. In demo 01, orbit the camera and notice the matrix of a selected block does not change. Then tap a different block.
2. In demo 02, set one slider to 0 and sweep the other. Then let both sit in the middle.
3. In demo 03, sweep the rotation while watching the dark origin dot. With `T · R · S`, the tail stays on the X axis. The other products move the tail off that axis.
4. In demo 04, sweep translate X. The point arrow’s tip moves. The direction arrow, w = 0, stays on the origin. Then add a little rotation and watch both arrows turn.
5. In demo 05, sweep the shear. The area stays 1. The corner angle changes. Then switch the shear from X to Y.
6. In demo 06, press Reflect across Y. The determinant turns negative and the F reads backwards. Press Squash to a line. The determinant becomes 0 and the F lies on that line.
7. In demo 07, watch the sheet fold. The determinant stays −1, so the mark flips. Then move the crease off the origin and read the three-step product.
8. In demo 08, drag the point around the circle. The determinant stays 1. Turn on two folds. The turn is twice the angle between the creases.
9. In demo 09, switch among Top, Front, and Side. One row of the matrix is zeros and the determinant stays 0. Then tilt the plane. The determinant stays 0.
10. In demo 10, move the eye closer and farther. Read one corner before the divide and after it. A larger w makes a smaller image on the sheet.
11. In demo 11, leave the slider at M and read the product. It is the identity. Slide to the end and watch the F return. Then press Flatten. The determinant is 0, so there is no inverse.
12. In demo 12, read λ for the stretch preset: 3 and 1. The red arrows stay on those lines. Then press Turn. Every arrow leaves its line.
13. In demo 13, leave the arrows at a = (3, 0) and b = (2, 2). The dot product is 6 and the angle is 45°. Then drag b until the arrows are perpendicular. The dot product becomes 0 and the angle mark turns red.
14. In demo 14, leave the arrows at a = (3, 0, 0) and b = (0, 2, 0). The cross product is (0, 0, 6) and the area is 6. Press Swap a and b. The red arrow flips and the cross product is (0, 0, −6). Then line the arrows up. The area and the cross product both become 0.
15. In demo 15, leave the arrows at u = (3, 1) and v = (1, 2). Press Orthonormal frame. |e1| and |e2| are 1, and e1 · e2 is 0. The arrows are red. Then press Add e3 and watch the third arrow stand up.
16. In demo 16, leave v at (3, 1) and the frame at 45°. Read both coordinate pairs. The squares of the frame coordinates add up to the square of the length of v. Slide the angle to 0°. The two pairs match.

## Run locally

The pages use ES modules. Open them through a small local server. Opening the HTML files directly will not load them.

```bash
python3 -m http.server 8080
```

Then visit [http://localhost:8080/](http://localhost:8080/).

Any static server is fine. The requirement is `http://`, not `file://`.

## GitHub Pages

Pages is live from the `main` branch at the repository root: [https://virgilrenfroe.github.io/seen-geometry/](https://virgilrenfroe.github.io/seen-geometry/). `.nojekyll` is in the root so Pages serves the HTML as written.

## Railway

A root `Dockerfile` serves the same files with nginx. `railway.toml` tells Railway to build that image and check `/`.

## How the pictures are drawn

[three.js r170](https://github.com/mrdoob/three.js/tree/r170) (`three@0.170.0`) is loaded in the browser from unpkg through an import map. It is not copied into this repo, so the project stays small and a network connection is required when you open a demo. Each demo creates one `WebGLRenderer`.

- Pixel ratio is capped at 2.
- Narrow screens use fewer instances in demo 01, a coarser sphere in demo 02, and fewer arrows in demo 12.
- If the operating system asks for reduced motion, demo 02 does not play on its own, and camera damping stays off. Orbit and sliders still work.
- If the picture cannot load, the page says so instead of sitting on a blank canvas.

Type is [Bricolage Grotesque](https://fonts.google.com/specimen/Bricolage+Grotesque), [Instrument Sans](https://fonts.google.com/specimen/Instrument+Sans), and [Space Mono](https://fonts.google.com/specimen/Space+Mono), with a system-font fallback. Each lesson is one HTML file under `demos/`, so the source of a single page is the whole lesson.

## Design

The pages are a drafting plate. The ground is graph paper. Titles, arcs, and dimension marks sit on that grid in ink, with one red for the measure. The hub is one plate of sixteen lessons. A crease is a construction line. The unit circle is a compass arc.
