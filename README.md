# CRK Map Art Planner

A browser-based tool for planning map art in Cookie Run Kingdom: turn a reference photo into a grid of matching path tiles and decorations, or build one by hand.

<img width="2559" height="1257" alt="Opera Снимок_2026-07-09_054003_pirat3571 github io" src="https://github.com/user-attachments/assets/20eb0d9b-856f-4bc6-b14c-2868ad8b1bc5" />


**Live tool:** https://pirat3571.github.io/crkmapart/

## What it does

Map art in Cookie Run Kingdom means arranging path tiles and decorations on your kingdom map to form a picture. This tool handles the color-matching part automatically and gives you manual tools for the rest.

Upload a photo, position it over the grid, and it samples the colors and picks the closest matching tile for each cell. Decorations get sampled too, on their own finer sub-grid, with a threshold slider controlling how readily they get placed. Before matching, you can adjust photo effects, since a straight color match doesn't always look right once it's actually broken into tiles.

For manual work there's a draw/erase/fill toolset, undo/redo, and an optional alignment grid. A running count on the side tracks how many of each tile and decoration the current map uses.

When you're done, export a high-resolution PNG for reference, or save the project as XML to keep editing it later. The interface is available in Russian and English.

## Usage

1. Open the [live tool](https://pirat3571.github.io/crkmapart/).
2. Upload a photo and drag/resize it over the grid, then click "Apply image", (you can also adjust the photo even after application).
3. Tune brightness, contrast, and the decoration threshold, or switch to the draw/erase/fill tools and touch things up by hand.
4. Check the usage panel on the right to see the tile/decoration count and click on objects to show only them.
5. Save to XML if you're not finished.

## Running it locally

It's a single HTML file, no build step, no dependencies. The default tiles and decorations load via `fetch()` from `./tiles/` and `./decorations/`, which doesn't work over `file://` in most browsers, so serve the folder instead of opening it directly:

```
git clone https://github.com/pirat3571/crkmapart.git
cd crkmapart
python3 -m http.server
```

Then open `http://localhost:8000`.


Or you can use [live server extension for VS Code](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)

## Notes

- Runs entirely client-side. Photos are processed locally with the Canvas API and never leave your browser.
- Uses CSS custom properties and other reasonably modern CSS, so a current browser is recommended.
- Fan-made tool, not affiliated with Devsisters or Cookie Run Kingdom.

## License

[![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE)
