# Violet Ribbons shader

A full-screen, animated WebGL shader: a black page with glowing blue-violet
ribbons and silk-like folds along the bottom edge.

Open `index.html` in any modern browser. It has no dependencies and no build step.

- `?t=12.5` freezes the animation at a given time, which is handy for screenshots.
- It respects `prefers-reduced-motion` by rendering a single still frame.
- To use it as a page background, keep the `<canvas id="shader">` (it's `position: fixed`)
  and put your content above it with a higher `z-index`.

Shapes are defined in the fragment shader (`#fs`): the left loop is an elliptical arc,
the waves are `v = f(u)` curves, and the sharp folds are line segments. Colors come from
the tone map near the end (`vec3(0.30, 0.17, 1.45)`). Raise the blue value for a bluer
glow, or the red value for a more purple one.
