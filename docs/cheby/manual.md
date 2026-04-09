# Cheby - Chebyshev Harmonic Generator

Harmonic waveshaper using Chebyshev polynomials for precise overtone control.

## Overview

Cheby generates harmonics from an input signal using Chebyshev polynomials. Each slider (H1–H8) controls the level of a specific harmonic order, allowing precise spectral shaping. A Dry/Wet knob blends the processed signal with the original. Optional soft clipping is available via the context menu.

## Parameters

**H1** (0.0–1.0, default 1.0)
- Fundamental (1st harmonic) level
- **Examples**:
  - **Value = 0.0**: No fundamental
  - **Value = 1.0**: Full fundamental

**H2** (0.0–1.0, default 0.0)
- 2nd harmonic level
- **Examples**:
  - **Value = 0.0**: No 2nd harmonic
  - **Value = 1.0**: Full 2nd harmonic

**H3** (0.0–1.0, default 0.0)
- 3rd harmonic level

**H4** (0.0–1.0, default 0.0)
- 4th harmonic level

**H5** (0.0–1.0, default 0.0)
- 5th harmonic level

**H6** (0.0–1.0, default 0.0)
- 6th harmonic level

**H7** (0.0–1.0, default 0.0)
- 7th harmonic level

**H8** (0.0–1.0, default 0.0)
- 8th harmonic level

**DRY/WET** (0.0–1.0, default 0.0)
- Blends between dry (original) and wet (harmonics) signal
- Uses equal-power crossfade
- **Examples**:
  - **Value = 0.0**: Dry only (bypass)
  - **Value = 0.5**: Equal blend
  - **Value = 1.0**: Wet only (harmonics only)

## I/O / CV

- **Audio In**: L/R. Polyphonic audio inputs are summed per side before processing. If the right input is unconnected, the summed left input is copied to the right side.
- **Audio Out**: Stereo L/R. Each output port always emits a single channel.
- **CV In**: None

## Context Menu

- **Soft Clip Outputs** — Toggle soft clipping on the output (default: OFF)
