# Day 23 — 3D CSS Cube

![Preview](preview.png)

## Challenge

Build a 3D rotating cube using only CSS 3D transforms — no WebGL, no canvas, no library.

## What I Built

- A full 6-faced 3D cube auto-spinning with a CSS animation
- **Drag to rotate** with mouse and touch support
- **Pause / Play** button
- **Speed controls** — Slow / Normal / Fast
- **Size slider** — resize the cube from 100px to 260px live
- Live CSS code block explaining the technique
- 3 mini cubes showing Slow / Fast / Y-axis only rotation

## Concepts Used

- `transform-style: preserve-3d` — tells the browser children exist in 3D space (not flat)
- `perspective: 600px` — distance from viewer to the z=0 plane; smaller = more dramatic
- `translateZ(100px)` — pushes the front face forward by half the cube size
- `rotateY(180deg) translateZ(100px)` — flips and pushes the back face backward
- `rotateY(±90deg) translateZ(100px)` — positions left and right faces
- `rotateX(±90deg) translateZ(100px)` — positions top and bottom faces
- `@keyframes autoSpin` — rotates the whole cube on Y-axis
- `animation-play-state: paused` — freezes animation at current frame
- `getBoundingClientRect` is not needed — mouse delta (`dx`, `dy`) updates `rotX` and `rotY` directly

## The Core Formula

Every face starts at the same position (overlapping). Then each face is:
1. **Rotated** to face its direction
2. **Pushed out** by `translateZ(half-size)`

```
Cube size = 200px → each face is pushed out 100px
```

## Time Taken

~60 minutes

## What I Learned

`transform-style: preserve-3d` is the key — without it, all children are flattened onto a 2D plane and the cube disappears. `perspective` on the parent container sets how "deep" the 3D effect looks. The drag interaction works by accumulating `dx` and `dy` from `mousemove` events into rotation angles, then applying them with `style.transform`. Stopping `animation` on drag prevents conflicts between the CSS animation and JS-driven rotation.

---

[⬅️ Day 22](../Day-22-Infinite-Marquee-Ticker/) · [Back to Main README](../README.md) · [Day 24 ➡️](../Day-24-Accessible-Modal-System/)