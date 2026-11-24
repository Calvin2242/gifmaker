# GIF Slideshow Maker

A small, private take on ezgif's "GIF maker": turn several images into an animated slideshow GIF.
Everything runs in the browser, so no images are uploaded anywhere. It's one `index.html` file with no dependencies, no build step and no CDN.

## Features

- Add images by drag & drop, file picker, or paste (Ctrl/⌘+V)
- Reorder by dragging (or ← →), duplicate, remove, sort by file name, reverse
- Per-frame delay (in 1/100 s, like ezgif), plus "set all"
- Loop count (0 = forever)
- Optional crossfade transitions (number of fade frames, fade speed, fade back to the first image)
- Canvas size: first, smallest or largest image, or a custom size
- Fit modes: fit with borders, fill and crop, stretch, or no resizing
- Background color or transparency
- Color count (2–256), Floyd–Steinberg dithering, and frame-difference optimization for smaller files
- Encoding runs in a Web Worker, with a progress bar and a cancel button
- Remembers your options between visits (localStorage)

## Host it on GitHub Pages

1. Create a new repository on GitHub (it can be private if your plan supports Pages for private repos; otherwise make it public).
2. Upload `index.html` to the root of the repository (via **Add file → Upload files**, or `git push`).
3. Go to **Settings → Pages**. Under **Build and deployment**, set **Source** to *Deploy from a branch*, pick `main` and `/ (root)`, then **Save**.
4. After a minute your tool is live at `https://<your-username>.github.io/<repo-name>/`.

You can also just double-click `index.html` to use it locally. It works offline.

## Notes

- GIF input files only use their first frame.
- HEIC photos only work in browsers that can decode them (Safari).
- Very large canvases with many crossfade frames make big files. Shrink the canvas, lower the color count, or turn off dithering to reduce size.
