# 8-Bit NES Converter

Transform any audio track into authentic NES chiptune, directly in your browser. No upload, no signup — all processing stays on your device.

<img width="908" height="592" alt="Screenshot 2026-06-24 120110" src="https://github.com/user-attachments/assets/d7aaafaa-5a96-4da6-9a75-960a2061afd4" />

<img width="875" height="515" alt="Screenshot 2026-06-24 120130" src="https://github.com/user-attachments/assets/d387c6a6-33c2-4f41-a558-5a87eb600f21" />

## Features

- **Bitcrusher Mode** — Reduce bit depth (1–16 bit) and sample rate (2–44 kHz) for classic lo-fi crunch
- **NES Resynthesis Mode** — 4-channel NES 2A03-style resynthesis using pitch detection + waveform generation
- **4 Dedicated Channels:**
  - **UTAMA** (Lead) — Square 50%
  - **SEKUNDER** (Secondary) — Pulse 25% / 12.5%
  - **BASS** — Triangle wave
  - **DRUM** — Noise channel
- **Auto Analyze** — Detects instruments (vocal, guitar, bass, drum) via spectral analysis and auto-configures channels
- **Presets** — Mega Man 4, NES Basic, Game Boy, C64, Max Crush, Clean
- **Real-time Preview** — Playback with seek bar
- **WAV Export** — Download your 8-bit creation

## Usage

1. Open `index.html` in a browser (or serve via HTTP)
2. Drop/select an audio file (MP3, WAV, FLAC, OGG, M4A)
3. Click **ANALYZE** to auto-detect instruments and configure channels, or toggle **AUTO: ON** to run analysis automatically on upload
4. Click **PROCESS** to convert
5. Preview with **PLAY**, adjust channels, or **DOWNLOAD WAV**

## How It Works

All audio processing runs in a **Web Worker** (background thread) — the UI never blocks. The NES resynthesis splits audio into 4 frequency bands, detects pitch per band via autocorrelation, and generates authentic NES 2A03 waveforms (square, pulse, triangle, noise).

## Requirements

A modern browser with Web Audio API and Web Worker support. No server needed — open the file directly or serve with any HTTP server:

```
python -m http.server 8080
```
