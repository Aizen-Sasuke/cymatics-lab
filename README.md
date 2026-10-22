# Cymatics Lab

Sound made visible: sand grains settle onto the nodal lines of a vibrating Chladni
plate, driven by real eigenmodes and by actual audio.

- **3D visualiser (main):** https://aizen-sasuke.github.io/cymatics-lab/
- **2D lab:** https://aizen-sasuke.github.io/cymatics-lab/lab.html

Both pages are single-file, dependency-free, and work offline from `file://`
(microphone and tab capture need a secure context).

## The 3D visualiser

A WebGL standing-wave plate you can orbit. The plate surface is displaced by the
eigenmode field while up to 45,000 sand grains migrate toward the nodal lines in a
CPU physics simulation; mode changes re-flow the sand in real time.

- Square (`cos mπx̃ · cos nπỹ`) and circular (`J_m(βr) · cos mθ`) eigenmodes,
  with a physical centre mount on the circular plate
- Orbit camera: drag to rotate, scroll to zoom, double-click to reset
- Audio sources: generated tone, microphone, audio file, or captured tab audio.
  Pitch selects the nearest mode; level drives plate amplitude and glow
- Circular modes with `m > 0` use a real centre hole, so the sand cannot pile up
  into a central blob
- Live readout of drive frequency, mode, and resonance affinity
- Presets (Lattice / Crystal / Bloom / Orbit), grain count, energy, and shape controls

Keyboard: `space` pause, `r` reset grains, `o` auto-orbit, `f` fullscreen, `h` hide UI.

## The 2D lab

The original top-down plate at [`lab.html`](lab.html): same physics, plus frequency
sweep, mode search, field/node overlays, and export. It links back to the 3D view.

## Legacy versions

The earlier "Cymatics - Live Chladni Patterns" builds are archived unmodified in
[`legacy/`](legacy/) for reference. They are not the live site.

## Running locally

No build step and no dependencies. Open `index.html` in a browser, or serve it:

```sh
python -m http.server 8000
```

Microphone and tab-capture sources require a secure context (`https://` or
`localhost`).

## Notes

Mode frequencies are ordered by the plate eigenvalue — `m² + n²` for the square
plate and `β²` (Bessel zeros) for the circular membrane — and scaled linearly
across the 50–1600 Hz drive band. Absolute Hz are therefore illustrative, while
the mode ordering, degenerate pairs, and spacing follow the plate. The mode
affinity readout reports how close the drive sits to the current mode's
resonance, reaching zero midway between neighbouring modes.
