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
- Narrow screens use fewer instances in demo 01 and a coarser sphere in demo 02.
- If the operating system asks for reduced motion, demo 02 does not play on its own, and camera damping stays off. Orbit and sliders still work.
- If the picture cannot load, the page says so instead of sitting on a blank canvas.

Type is [Bricolage Grotesque](https://fonts.google.com/specimen/Bricolage+Grotesque), [Instrument Sans](https://fonts.google.com/specimen/Instrument+Sans), and [Space Mono](https://fonts.google.com/specimen/Space+Mono), with a system-font fallback. Each lesson is one HTML file under `demos/`, so the source of a single page is the whole lesson.

## Design

The pages are a drafting plate. The ground is graph paper. Titles, arcs, and dimension marks sit on that grid in ink, with one red for the measure. The hub is one plate of eight lessons. A crease is a construction line. The unit circle is a compass arc.
