# Resonance Creator

Real-time resonance art in the browser. Thousands of glowing particles settle onto the nodal lines of vibrating waves, the way sand gathers on a Chladni plate, then get mirrored into a kaleidoscope with trails, glow and chromatic split. Built for live projection.

Everything is one file, `index.html` (WebGL2 + Web Audio, no build step, no dependencies).

## Run it
- **Locally:** double-click `index.html` and it opens in your browser.
- **Online:** host it with GitHub Pages (see below). The microphone only works on `https://` or `localhost`, which GitHub Pages provides.

Needs a browser with WebGL2: current Chrome, Edge, Firefox or Safari.

## The math
| Field | Equation |
|---|---|
| Plate (Chladni) | ψ = cos θ · cos(nπx)cos(mπy) + sin θ · cos(mπx)cos(nπy) |
| Drum (circular membrane) | ψ = Jₙ(k r) · cos(nθ ± ωt), Bessel functions of the first kind |
| Ripples (point sources) | ψ = Σᵢ sin(k\|r − sᵢ\| − ωt) |
| Quasicrystal (plane waves) | ψ = Σᵢ cos(k r·ûᵢ + ωt) |

Particles move toward ψ = 0 (or |ψ| = contour level) by Newton steps along the gradient. A polar fold gives the kaleidoscope symmetry.

## Controls
| Key | Action |
|---|---|
| H | Hide / show interface |
| F or double-click | Fullscreen |
| Space | Autopilot on / off |
| R | Randomize |
| 1–4 | Plate, Drum, Ripples, Quasicrystal |
| ← → / ↑ ↓ | Change n / m |
| M | Still / moving |
| [ ] | Slower / faster |
| P | Save a PNG snapshot |

**Sound:** *Tone* plays the plate's resonant frequency f = f₀·√(n² + m²). Load an audio file or use the mic to make the pattern react to bass, mids and highs. Options let the pitch choose the mode or beats jump it. *Strobe on beat* produces flashing light; leave it off around anyone with photosensitive epilepsy.

**Output:** snapshot (PNG) and record (WebM video with sound). Settings are remembered in your browser.
