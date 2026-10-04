# AR Starship Docking

A mobile AR prototype: dock a small spacecraft with a floating space station, seen through your phone's camera.

**Flow:** START → SCAN → DETECTED → APPROACH → ALIGN → DOCK → SUCCESS (~30–45 s)

- Live rear camera feed with 3DoF tracking from the phone's gyroscope (works in iPhone Safari, no app install)
- Spatial UI: anchored labels with leader lines, scan wave, guidance chevrons, docking reticle with a boresight ring, off-screen indicators
- Touch alignment: drag to center the ship, twist pad to level it, magnetic lock at ≥95%
- Falls back to a 3D preview (drag to look) when the camera or motion sensors are unavailable

Single `index.html`, three.js from a CDN. Ship and station are ported from the Spline design scene.

## Run

Camera and motion access need HTTPS (or `localhost`):

```
python -m http.server 8765
```

URL options: `?demo` auto-plays the whole flow (handy for recording), `?nocam` skips the camera.
