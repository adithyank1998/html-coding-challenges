# Day 22 — Infinite Marquee / Ticker

![Preview](Preview1.png)

## Challenge

Build a seamless infinite scrolling marquee with multiple rows going in different directions.

## What I Built

4 marquee rows, each with a different style:

| Row | Content | Direction |
|-----|---------|-----------|
| 1 | Tech skill tags with coloured dots | → Left |
| 2 | Big bold outlined words (dark background) | ← Right |
| 3 | Brand / tool chips with icons | → Left |
| 4 | Testimonial quote cards | ← Right |

- **Hover any row to pause** it
- Fade edges on left and right with `linear-gradient`
- All rows are pure CSS animation — no JavaScript scroll events

## Concepts Used

- `animation: marquee 22s linear infinite` — constant speed, no easing, loops forever
- `translateX(-50%)` — the seamless loop trick (see below)
- `width: max-content` — track is as wide as all its children combined
- `overflow: hidden` — clips content outside the marquee container
- `animation-play-state: paused` on hover — freezes the marquee
- `::before` / `::after` on the section — fade masks on both edges
- `linear-gradient(to right, color, transparent)` — the fade edge
- `-webkit-text-stroke` — outlined/hollow text effect for row 2
- JS `fill()` helper renders each item **twice** for the seamless loop

## The Seamless Loop Trick

```
Items rendered: [A B C D A B C D]  ← duplicated!

Animation moves left by 50% of total width:
Start: [A B C D | A B C D]  ← shows first half
End:   [A B C D | A B C D]  ← shows second half (looks identical!)
Then CSS resets to start position → no visible jump
```

## Time Taken

~45 minutes

## What I Learned

The seamless loop works because you render all items **twice**, then animate `translateX` from `0` to `-50%` of the total width. When it reaches `-50%`, it snaps back to `0` — but since both halves are identical, the viewer never sees the jump. `animation: linear infinite` with no easing ensures constant speed with no acceleration at the reset point.

---

[⬅️ Day 21](../Day-21-Custom-Video-Player/) · [Back to Main README](../README.md) · [Day 23 ➡️](../Day-23-3D-CSS-Cube/)