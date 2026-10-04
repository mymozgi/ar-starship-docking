# AR Starship Docking

A mobile AR prototype: dock a small spacecraft with a floating space station, seen through your phone's camera.

**Flow:** START → SCAN → DETECTED → APPROACH → ALIGN → DOCK → SUCCESS (~30–45 s)

- Live rear camera feed with 3DoF tracking from the phone's gyroscope (works in iPhone Safari, no app install)
- The camera image drives the scene lighting and becomes a soft reflection map on the hull
- **Approach:** hold Thrust to fly, release to retro-brake; enter the brake zone too fast and you bounce back
- **Alignment:** the ship drifts; drag to correct, twist with two fingers to level; hold ≥95% for a moment to capture
- Fuel is spent by thrust, braking and every RCS correction; the final score is computed from time, arrival speed, precision and fuel
- Spatial UI: anchored labels with leader lines, scan wave, guidance chevrons, docking reticle with a boresight ring, off-screen indicators
- Procedural WebAudio sound (engine hum, RCS puffs, capture lock, docking clamps), no audio files
- Falls back to a 3D preview (drag to look) when the camera or motion sensors are unavailable

Desktop controls: Space / ↑ thrust, arrow keys move, Q / E roll, Enter for the main button.

Single `index.html`, three.js from a CDN. Ship and station are ported from the Spline design scene.

## Run

Camera and motion access need HTTPS (or `localhost`):

```
python -m http.server 8765
```

URL options: `?demo` auto-plays the whole flow (handy for recording), `?nocam` skips the camera.
