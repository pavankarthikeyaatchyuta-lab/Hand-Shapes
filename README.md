# Hand Particle Conductor v5.0

A real-time, webcam-driven particle art piece. Move your hand in front of your camera to control a 12,000-point particle system rendered in WebGL — no install required, runs entirely in the browser.

## How it works

- **MediaPipe Hands** tracks 21 hand landmarks from your webcam feed in real time.
- **Finger count** (0–5) morphs the particle field between six shapes: Sphere, Heart, Star, Saturn, Flower, and DNA — animated with GSAP for smooth transitions.
- **Pinch distance** (thumb tip to index tip) controls how spread out the particles are.
- **Hand depth** (distance from wrist to middle-finger base, as a proxy for how close your hand is to the camera) drives the camera zoom.
- Particle color shifts dynamically based on spread, and the whole field gently rotates.

## Tech Stack

- [Three.js](https://threejs.org/) — WebGL particle rendering
- [MediaPipe Hands](https://developers.google.com/mediapipe) — real-time hand landmark tracking
- [GSAP](https://gsap.com/) — smooth shape-morph animations
- Vanilla JavaScript, HTML, CSS — no build step

## Run It

This is a single self-contained `index.html` file with all dependencies loaded via CDN. Just open it in a browser (Chrome recommended) and grant camera access:

```bash
# Clone and open directly
git clone https://github.com/pavankarthikeyaatchyuta-lab/Hand-Shapes
cd Hand-Shapes
open index.html
```

Or serve it locally if your browser blocks webcam access on `file://`:

```bash
python -m http.server 8000
# then visit http://localhost:8000
```

## Gestures

| Gesture | Effect |
|---|---|
| Hold up 0–5 fingers | Morphs particle shape (Sphere → Heart → Star → Saturn → Flower → DNA) |
| Pinch thumb + index | Shrinks/expands particle spread |
| Move hand closer/farther | Zooms camera in/out |
