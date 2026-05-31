# Day 18 — CSS Grid Layout Builder

![Preview](preview.png)

## Challenge

Build an interactive CSS Grid playground where you can adjust settings and see the grid update live with generated CSS code.

## What I Built

- Live grid preview that updates instantly on every change
- **Columns & Rows** — increase/decrease with +/− buttons (1–6)
- **Column Size** selector — `1fr`, `auto`, `minmax()`, `auto-fit`
- **Justify Items** — stretch / start / center / end
- **Align Items** — stretch / start / center / end
- **Gap slider** — 0px to 40px with live preview
- **Generated CSS** — syntax-highlighted code output updates live
- **Copy CSS** button — copies the code to clipboard with ✓ feedback
- **Reset** button — returns to default settings
- Cells cycle through 6 different colours
- Responsive — controls stack below the preview on mobile

## Concepts Used

- `grid-template-columns: repeat(N, 1fr)` — creates N equal columns
- `grid-template-rows: repeat(N, 1fr)` — creates N equal rows
- `gap` — sets spacing between all grid cells
- `justify-items` — aligns items horizontally within their cell
- `align-items` — aligns items vertically within their cell
- `minmax(100px, 1fr)` — cell is at least 100px but can grow
- `auto-fit` — fills as many columns as fit in the container
- `style.gridTemplateColumns` — JS sets CSS grid properties directly
- `navigator.clipboard.writeText()` — copies text to clipboard
- Syntax highlighting — HTML `<span>` tags with colour classes inside `<pre>`


## Time Taken

~60 minutes

## What I Learned

You can apply CSS Grid properties directly in JavaScript using `element.style.gridTemplateColumns`, `element.style.gap`, etc. — just like any other CSS property. This makes it easy to build live interactive tools. `navigator.clipboard.writeText(text)` is the modern way to copy text programmatically — it returns a Promise so you can show a success state after it completes.

---

[⬅️ Day 17](../Day-17-Real-Time-Character-Counter/) · [Back to Main README](../README.md) · [Day 19 ➡️](../Day-19-Smooth-Page-Transition-SPA/)