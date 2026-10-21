# Cymatics Lab

An interactive, single-file Chladni plate lab. Grains are driven by a mathematical
standing-wave field, vibrate where the plate is active, and migrate toward the
nodes where it is still.

Live: https://aizen-sasuke.github.io/cymatics-lab/

## Features

- Square and circular plate geometry with adjustable modes M × N
- Up to 45,000 simulated grains with tunable energy, damping, friction, and speed
- Audio sources: generated tone, microphone, audio file, or captured tab audio
- Frequency sweep, curated mode presets, and a "find something interesting" search
- Field and node overlays, learn panel, and a live readout

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

The mode affinity readout is a normalized heuristic for interactive exploration,
not a material-calibrated resonance measurement.
