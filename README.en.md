<div align="center">

<img src="assets/N-Labeler.ico" width="96" alt="N-Labeler">

# N-Labeler

**A monophone label editor for NNSVS / singing voice databases**

A Windows desktop app for editing phoneme boundaries in `.lab` files (HTK format)
by mouse, while viewing the waveform, spectrogram, F0 and power on a synchronized
time axis.

[English](README.en.md) · [日本語](README.md)

[![Download](https://img.shields.io/badge/⬇_Download_latest-Releases-2ea44f?style=for-the-badge)](../../releases/latest)

</div>

![N-Labeler screenshot](docs/screenshot.png)

---

## Download / Install

1. Download `N-Labeler-x.y.z-win64.zip` from [**Releases**](../../releases/latest)
2. Extract it anywhere
3. Run `N-Labeler/N-Labeler.exe`

No Python installation is required (it runs standalone).

> The build is unsigned, so Windows SmartScreen may warn you on first launch.
> Click **More info** → **Run anyway** to start it.

**Requirements:** Windows 10 / 11 (64-bit)

## Features

- **Multi-pane synchronized view** — power / F0 (VUV) / waveform / spectrogram /
  time ruler / labels / overview, all locked to one time axis. Scroll horizontally
  with the wheel, zoom with Ctrl+wheel or buttons.
- **Boundary editing** — drag boundaries on the label pane (clamped to neighbors),
  add/remove them via double-click or the right-click menu. Edited boundaries are
  shown with a distinct color and a ▼ marker. Ctrl+left-click warps the nearest
  boundary; Ctrl+drag on a boundary shifts all following labels together (handy for
  fixing head-alignment drift).
- **Label-name presets** — assign common phonemes (`pau`, `cl`, `GlottalStop`,
  `Edge`, …) with one click from the right-click menu. Presets are fully editable.
- **Spectrogram settings** — change FFT size / window function / dynamic range /
  upper frequency / colormap (magma / inferno / viridis / jet / grayscale) from the
  right-click menu. Zooming in recomputes only the visible range at high resolution
  in real time.
- **Playback** — Space to play/stop, play a selected range or a single label
  segment, with a real-time playhead.
- **Tempo grid** — display a grid from BPM / note value / offset. If a `.ust` with
  the same name exists, the tempo is picked up automatically.
- **Automatic label generation** — opening a `.wav` without a `.lab` can auto-draft
  phoneme labels using the bundled inference model (boundary detection + phoneme
  recognition). The result is loaded unsaved; press Ctrl+S to write the `.lab`.
- **Close-boundary warning** — boundaries closer than a threshold are highlighted
  in red.
- **Work-state saving** — edited flags, view range and tempo settings are saved to
  a `.work` file and restored next time. Analysis results (F0 / spectrogram) are
  cached to avoid recomputation.
- **Undo/Redo** (Ctrl+Z / Ctrl+Y), dark / light theme, drag-resizable pane heights.

## Usage

1. **File → Open** (Ctrl+O) and pick a `.lab` or `.wav`. A `.wav`/`.lab` pair with
   the same name is loaded together automatically (you can also drag & drop a
   `.lab`/`.wav` onto the app, or pass it as a launch argument).
2. Click the waveform or spectrogram to place the playback start (magenta vertical
   line), then press **Space** to play.
3. Drag boundaries on the label pane to adjust them. Double-click to add a boundary;
   right-click to add/remove or rename.
4. Press **Ctrl+S** to save in place.

### Key shortcuts

| Key | Action |
|---|---|
| Space | Play / Stop |
| Ctrl+O | Open |
| Ctrl+S / Ctrl+Shift+S | Save / Save As |
| Ctrl+Z / Ctrl+Y | Undo / Redo |
| Ctrl + `+` / `-` / `0` | Zoom in / out / fit |
| Wheel / Ctrl+Wheel | Horizontal scroll / Zoom |
| F1 | Show the manual |

## Label format

Reads and writes HTK-style `.lab` files (`start end phoneme`, space-separated,
times as integers in 100 ns units). Boundary continuity is validated on load and
any discontinuity is reported.

## License

The application itself is under the [MIT License](LICENSE). The distributed build
bundles PySide6 (Qt) / NumPy / SciPy / soundfile (libsndfile) / sounddevice
(PortAudio) / pyqtgraph / pyworld (WORLD) / ONNX Runtime; see
[THIRD_PARTY_LICENSES.md](THIRD_PARTY_LICENSES.md) and [`licenses/`](licenses/) for
their respective licenses. Qt and libsndfile are provided under the LGPL.
