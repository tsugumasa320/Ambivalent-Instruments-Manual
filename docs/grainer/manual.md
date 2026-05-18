# Grainer - Granular Synthesis Processor

Real-time granular processor for shaping live audio textures.

## Overview

Grainer processes incoming audio with up to 128 grains and a 6-second buffer. Pitch, position, density, and randomization controls enable a wide range of textures.

## Parameters

**GRAIN LENGTH** — how long each grain’s read spans in the buffer (**0–100%** on panel).

**DENSITY** — **%** chance each voice fires a grain when its cycle wraps.

**PITCH** (-1.0–1.0, default 0.0)
- Playback pitch (displayed as 1/3x–3x)
- **Live-tracked**: turning the knob/CV updates **currently playing grains immediately**. The random/quantize ratio relative to the base pitch is locked per grain.
- **Examples**:
  - **Value = 0.0**: 1x
  - **Value = 1.0**: 3x

**PITCH RANDOM** (0.0–3.0, default 0.0)
- Random pitch range (±octaves)
- The random offset is sampled at trigger time and locked for the duration of the grain.
- **Examples**:
  - **Value = 0.0**: No randomization
  - **Value = 3.0**: Large randomization

**PITCH QUANTIZE** (0.0–1.0, default 1.0)
- Pitch quantization amount (snaps to ratios)
- LED brightness shows closeness to simple ratios
- **Examples**:
  - **Value = 0.0**: Free pitch
  - **Value = 0.5**: Partial snapping (e.g. 1.0x/1.5x/2.0x)
  - **Value = 1.0**: Strong ratio snapping
- **Interval guide (upward direction)**:

| Quant value (`q`) | Common upward ratios | Semitones (approx.) | Interval feel (rough) |
|---|---|---:|---|
| `1.0` | `2.0x`, `3.0x` | `+12.00`, `+19.02` | Octave / Octave + perfect fifth |
| `0.5` | `1.5x`, `2.0x`, `2.5x`, `3.0x` | `+7.02`, `+12.00`, `+15.86`, `+19.02` | Perfect fifth to octave+fifth range |
| around `0.333` | `1.333x`, `1.666x`, `2.0x`, `2.666x` | `+4.98`, `+8.84`, `+12.00`, `+16.98` | Perfect fourth / near minor seventh / octave / near 11th |
| `0.25` | `1.25x`, `1.5x`, `1.75x`, `2.0x` | `+3.86`, `+7.02`, `+9.69`, `+12.00` | Near major third / fifth / near major sixth / octave |

- **Notes**:
  - Internally this is step quantization: `ratio = floor(rawRatio / q) * q` (not fixed semitone quantization).
  - Semitone conversion uses `12 * log2(ratio)`.

**WINDOW SHAPE** (-1.0–1.0, default 0.0)
- Hann window bias
- **Examples**:
  - **Value = -1.0**: Fast attack bias
  - **Value = 1.0**: Slow attack bias

**POSITION** (0–100%, default 100%)
- Read position
- **Examples**:
  - **Value = 0**: Oldest
  - **Value = 100**: Newest
- **Note**: When pitch is significantly increased and Grain Length is large, the actual read position may differ from the displayed knob value by a small amount (up to ~8%) to avoid click artifacts caused by reading across the ring buffer seam.

**POSITION RANDOM** (0.0–1.0, default 0.5)
- Position random amount
- **Examples**:
  - **Value = 0.0**: No randomization
  - **Value = 1.0**: Full randomization

**STEREO SPREAD** (0.0–1.0, default 0.5)
- Stereo width
- **Examples**:
  - **Value = 0.0**: Mono
  - **Value = 1.0**: Full width

**REVERB** (0.0–1.0, default 0.0)
- Reverb amount
- **Examples**:
  - **Value = 0.0**: Off
  - **Value = 1.0**: Max

**INPUT GAIN** (0.0–1.0, default 0.5)
- Input gain (displayed as -18dB to +6dB)
- **Examples**:
  - **Value = 0.0**: Mute
  - **Value = 1.0**: Max

**DRY/WET** (0.0–1.0, default 0.5)
- Dry/wet mix
- **Examples**:
  - **Value = 0.0**: Dry only
  - **Value = 1.0**: Wet only

**REVERSE** (button)
- Toggle reverse playback
- **Live-tracked**: toggling mid-playback flips the direction of currently playing grains on the next sample.
- **Examples**:
  - **OFF**: Forward
  - **ON**: Reverse

**FREEZE** (button)
- Freeze buffer
- **Examples**:
  - **OFF**: Recording
  - **ON**: Frozen

## I/O / CV

- **Audio In**: L/R
- **Audio Out**: L/R
- **CV In**: Grain Length, Density, Pitch(1V/oct), Pitch Random, Position, Position Random, Stereo Spread, Volume, Dry/Wet, Reverb, Window Shape

## Context Menu

Top-level entries, in order:

- **Soft clip** — Toggle soft clipping on the output (default: OFF)
- **Grain Voices** ▶ — Submenu to pick polyphony count (4 / 8 / 16 / 32 / 48 / 64 / 96 / 128). The right-side hint shows the current value
- **SSD1306 preview** ▶ — Submenu for the OLED preview used when porting to Daisy
    - **Enable SSD1306 128x32 preview**: turn the on-panel preview on/off
    - **Tint** (White / Blue / Amber / Yellow/Blue (2-color)): preview color
