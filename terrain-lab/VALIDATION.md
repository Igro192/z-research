# Validation record — Terrain Lab

Checked 27 October 2026 against the public browser editor at https://z-research-engineering.igrothegreat.chatgpt.site/demos/terrain.html.

1. Loaded the actual editor: no sign-in was required.
2. Chose **Add example course**. The interface displayed four obstacles.
3. Selected **Staircase (4 steps)** and chose **Add at center**. The interface displayed eight obstacles.
4. Chose **Download terrain JSON**. A real `terrain.json` download completed.
5. Parsed the downloaded file and checked that it contained eight `boxes`; every box had a three-coordinate `pos`, three positive half-extents in `size`, and a unique sequential name `studio_1` through `studio_8`.

The example's first box exported `pos: [-3, -2, 0.175]` and `size: [0.9, 0.9, 0.175]`. The first stair step exported `size: [0.175, 0.7, 0.0375]`.

Earlier 26 October checks of the original Python validation/export functions: six passed, covering half-extents, authored coordinates, nonfinite/bounds rejection, the 80-box cap, JSON round-trip and XML syntax. Neither test set establishes trained robot movement or terrain compatibility across every upstream runtime version.
