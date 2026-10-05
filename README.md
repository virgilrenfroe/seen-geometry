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

On a wide screen, demo 03 can show all three orders at once. The tail positions are listed either way.

A useful order for a class:

1. In demo 01, orbit the camera and notice the matrix of a selected block does not change. Then tap a different block.
2. In demo 02, set one slider to 0 and sweep the other. Then let both sit in the middle.
3. In demo 03, sweep the rotation while watching the dark origin dot. With `T · R · S`, the tail stays on the X axis. The other products move the tail off that axis.

## Run locally

The pages use ES modules. Open them through a small local server. Opening the HTML files directly will not load them.

```bash
python3 -m http.server 8080
```

Then visit [http://localhost:8080/](http://localhost:8080/).

Any static server is fine. The requirement is `http://`, not `file://`.

## GitHub Pages

The site is ready to publish from the `main` branch at the repository root (`index.html` is the hub). The address is [https://virgilrenfroe.github.io/seen-geometry/](https://virgilrenfroe.github.io/seen-geometry/).

That address is not serving yet. Enabling Pages needs repository administration. The token used to push this repo can update `main`, and GitHub rejected the Pages API with “Resource not accessible by integration” (it requires `pages=write` and `administration=write`).

A repository admin can turn it on in one step: **Settings → Pages → Build and deployment → Deploy from a branch → Branch `main`, folder `/ (root)` → Save.** `.nojekyll` is already in the root so Pages will serve the HTML as written.

## How the pictures are drawn

[three.js r170](https://github.com/mrdoob/three.js/tree/r170) (`three@0.170.0`) is loaded in the browser from unpkg through an import map. It is not copied into this repo, so the project stays small and a network connection is required when you open a demo. Each demo creates one `WebGLRenderer`.

- Pixel ratio is capped at 2.
- Narrow screens use fewer instances in demo 01 and a coarser sphere in demo 02.
- If the operating system asks for reduced motion, demo 02 does not play on its own, and camera damping stays off. Orbit and sliders still work.
- If the three.js file cannot be loaded, the page says so instead of sitting on a blank canvas.

Type is [Bricolage Grotesque](https://fonts.google.com/specimen/Bricolage+Grotesque), [Instrument Sans](https://fonts.google.com/specimen/Instrument+Sans), and [Space Mono](https://fonts.google.com/specimen/Space+Mono), with a system-font fallback. Each lesson is one HTML file under `demos/`, so the source of a single page is the whole lesson.
