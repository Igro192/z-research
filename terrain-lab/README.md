# Terrain Lab

An open-source, browser-based obstacle editor for the [TERRA](https://github.com/amathislab/terra) terrain format. Place boxes, four-step staircases and ramps; inspect the geometry in a projected scene and top-down map; download the authored obstacles as JSON. The public editor runs locally in the browser and needs no account, server, model weights or build step.

**[Try the working editor](https://z-research-engineering.igrothegreat.chatgpt.site/demos/terrain.html)** · [Silent editor showcase](https://z-research-engineering.igrothegreat.chatgpt.site/downloads/terrain-lab-demo.mp4) · [Project record](https://z-research-engineering.igrothegreat.chatgpt.site/projects/terra-terrain-lab.html) · [Z. Research](https://z-research-engineering.igrothegreat.chatgpt.site/)

![Genuine browser capture of Terrain Lab with four authored obstacles](https://z-research-engineering.igrothegreat.chatgpt.site/assets/terrain-editor.jpg)

The screenshot shows the actual browser editor, captured on 26 October 2026. The shapes are user-authored geometry; they are not a robot policy or a simulation of successful locomotion.

## Try it locally

Open `index.html` in a modern desktop browser. Choose an obstacle type and dimensions, then click the top-down map or **Add at center**. Drag in the large viewport to orbit. **Add example course** inserts four editable boxes. **Download terrain JSON** exports the current obstacle list.

The download contains `boxes`, each with a name, position, half-extents (`size`), yaw and pitch, plus provenance. X and Y are ground coordinates; Z is up. Stairs are four separate boxes. The editor caps a terrain at 80 obstacle boxes.

## What was verified

The earlier source audit passed six checks of the original Python validation/export code: half-extents, authored coordinates, nonfinite and bounds rejection, the 80-box limit, JSON round-trip and MuJoCo XML syntax. XML parsing is not a physics test. On 27 October 2026, a fresh browser run of the public editor added the four-box example and four staircase steps, downloaded JSON, and checked all eight exported records for positions, positive half-extents and unique sequential names. See [validation record](VALIDATION.md).

## Technology and provenance

This release contains the original Terrain Lab editor adapted into a dependency-free HTML/CSS/JavaScript application using Canvas 2D and JSON. It is MIT-licensed. The TERRA robot-learning research project is [separate upstream work](https://github.com/amathislab/terra); its algorithms, runtime and assets are not included or claimed as original Z. Research inventions.

## Limits

- The web page authors and exports geometry. It does not train, run or evaluate a humanoid policy.
- Compatible TERRA playback requires the separate upstream runtime, a suitable checkpoint and properly licensed motion assets.
- The projected viewport is an editor preview, not a physics simulation.
- The source release includes no model weights, private records or third-party game/research binaries.

For technical or editorial questions, [open a public Z. Research issue](https://github.com/Igro192/z-research/issues/new). Do not include private information in a public issue.
