# Day 14 — Parallax Scrolling Page

![Preview](preview.png)

## Challenge

Build a page where background layers scroll slower than the content, creating a depth effect.

## What I Built

- 4 full-height parallax sections, each with its own speed
- Background moves at a fraction of scroll speed (`0.25` to `0.5`)
- Content section in between explaining how it works
- Dark overlay on each section so text stays readable
- Bouncing scroll indicator on the hero
- Sticky navbar with blur effect
- Responsive — works on all screen sizes

## Concepts Used

- `window.scrollY` — reads how many pixels the user has scrolled
- `element.offsetTop` — gets the distance of an element from the top of the page
- `data-speed` attribute — stores a custom speed value on each background element
- `style.transform = translateY(offset + 'px')` — moves the background layer
- `requestAnimationFrame()` — runs the update smoothly in sync with the screen refresh rate (60fps)
- `will-change: transform` — hints the browser to GPU-accelerate the background
- `position: absolute; inset: -30%` — makes the background larger than its container so it never shows gaps when shifted
- `overflow: hidden` on the section — clips the oversized background


## Time Taken

~125 minutes

## What I Learned

Parallax is just `translateY(scrollY * speed)` — that's it! The speed value controls the depth feeling. A speed of `1.0` means the background moves with the scroll (no effect). `0.5` means it moves half as fast (subtle). `0.0` means it doesn't move at all (pinned). The background needs to be bigger than its container (`inset: -30%`) so it never reveals empty space when it shifts. `requestAnimationFrame` makes the movement buttery smooth without janky jumps.

---

[⬅️ Day 13](../Day-13-CSS-Only-Accordion-FAQ/) · [Back to Main README](../README.md) · [Day 15 ➡️](../Day-15-Glassmorphism-Dashboard/)