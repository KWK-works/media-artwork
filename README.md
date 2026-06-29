# Departure

*A computational artwork that translates a piano composition into space, motion, and light.*

![status](https://img.shields.io/badge/type-media%20art-9cc4e4) ![stack](https://img.shields.io/badge/p5.js-Web%20Audio-6fd6d0)

---

## Overview

**Departure** is a browser-based, audio-reactive media-art system. It is not a lyric
video or a conventional music visualizer. The visuals *emerge from* the music rather
than illustrate a narrative — a living field that reacts to sound, time, silence, and
dynamics. It runs as an interactive WebGL/Canvas artwork and can be recorded as a
music video.

## Concept

The work sits between **generative art, audiovisual installation, creative coding,
and algorithmic composition**. The viewer is asked to perceive relationships between
sound, time, space, motion, light, and silence — not characters or storytelling.

Musical structure becomes visual language through a direct mapping:

| Musical feature        | Visual response                          |
|------------------------|------------------------------------------|
| Piano attack (onset)   | Particles emerge                         |
| Sustain / energy       | Expansion, larger motion                 |
| Silence                | Near-complete stillness, long diffusion  |
| High frequencies       | Thin flowing lines                       |
| Low frequencies        | Large, slow spatial movement             |
| Dynamics (RMS)         | Brightness                               |
| Onset rate (tempo)     | Camera drift / breath                    |

Motion is designed to feel calm, immersive, and reflective — closer to **breathing,
ocean currents, wind, and ink diffusion** than to EDM or gaming aesthetics.

**Palette:** black · white · gray, accented with pale blue (`#9cc4e4`) and soft cyan
(`#6fd6d0`). No saturated rainbow.

## Technologies

- **p5.js** — rendering loop and 2D compositing
- **p5.sound (Web Audio API)** — FFT, amplitude, spectral centroid / energy bands
- **HTML5 / CSS** — minimal installation-style interface
- Adaptive **spectral-flux onset detection** (mean + k·σ threshold) for piano attacks
- **Perlin-noise flow field** for organic, ink-like particle and line motion
- **MediaRecorder** — in-browser `.webm` capture (visuals + audio)

> Optional future layers: Three.js / GLSL shaders / Tone.js (see roadmap).

## Installation

The artwork is a single self-contained `index.html` and needs **no build step**.

```bash
git clone <your-repo-url> departure
cd departure
```

Optional — a Vite dev server for live-reload while developing:

```bash
npm install
npm run dev
```

## Run instructions

**Zero-build:** serve the folder, then open it (serving is needed so the bundled
`audio/departure.mp3` can load):

```bash
npx serve .        # or: python3 -m http.server
```

`index.html` auto-loads `audio/departure.mp3` and waits on a **Begin Departure**
tap — browsers require a user gesture before audio can start. Drag any audio file
anywhere to replace the track.

> Want a single file with the music inside? Open **`departure-embedded.html`** —
> it plays with no external file (you can even open it directly, no server needed).

Controls: `Space` play/pause · `F` fullscreen/exhibition · `H` hide UI ·
aspect toggle (16:9 / 9:16 for vertical shorts) · `Record` exports a `.webm`.

**Deploy:** push to GitHub and enable **GitHub Pages** (root) — the artwork is live as-is.

## Output targets

- **GitHub** — source code
- **YouTube** — record `.webm`, transcode to mp4 (`ffmpeg -i in.webm out.mp4`)
- **TikTok** — switch to 9:16 before recording
- **Personal site** — embed the interactive WebGL/Canvas artwork directly

## Future roadmap

- [ ] Real-time microphone / line input
- [ ] MIDI input mapping
- [ ] Multiple compositions / playlist
- [ ] GLSL shader post-processing & WebGL renderer
- [ ] Interactive controls panel (parameter sliders)
- [ ] Exhibition / installation mode (kiosk, auto-advance)

## License

MIT — see [LICENSE](./LICENSE).

---

*Departure — where music becomes space, motion, and light.*
