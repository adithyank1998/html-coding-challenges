# Day 17 — Real-Time Character Counter

![Preview](preview.png)

## Challenge

Build a textarea that counts characters, words, lines, and read time in real time as the user types.

## What I Built

- Live stats that update on every keystroke: **Characters, Words, Lines, Read Time**
- **SVG ring progress** — fills up as you approach the character limit
- **Progress bar** — visual fill below the textarea
- **Colour feedback** — purple → amber → red as you approach/exceed limit
- **Platform presets** — No Limit / Twitter (280) / Instagram (2,200) / LinkedIn (500)
- **Limit message** — shows remaining characters, turns red if over limit
- **Clear button** — resets everything
- Active preset highlights in purple

## Concepts Used

- `textarea.addEventListener('input', fn)` — fires on every keystroke
- `text.length` — counts characters
- `text.trim().split(/\s+/).length` — splits by whitespace to count words
- `text.split('\n').length` — counts newlines for line count
- **Read time formula:** `(words / 200) * 60` — assumes 200 words per minute
- `stroke-dasharray` + `stroke-dashoffset` — the SVG ring trick
  - `dasharray` = total circumference (2π × radius)
  - `dashoffset` = how much of the stroke is hidden (decreases as % goes up)
- `Math.min(chars / limit, 1)` — clamps percentage between 0 and 1
- `dataset.limit` — reads custom data from HTML `data-` attributes
- `regex /\s+/` — matches one or more whitespace characters

## Time Taken

~50 minutes

## What I Learned

The SVG ring counter uses `stroke-dashoffset` — a clever trick where the stroke of a circle is set to exactly the circumference length, and the offset controls how much of it is "hidden". Setting offset to 0 shows the full ring; setting it to the full circumference hides it completely. The `input` event fires for every single keystroke, paste, or delete — making it perfect for real-time updates without any delay.

---

[⬅️ Day 16](../Day-16-Animated-SVG-Icon-Set/) · [Back to Main README](../README.md) · [Day 18 ➡️](../Day-18-CSS-Grid-Layout-Builder/)