# Delay - Stereo Delay Module

Stereo delay with switchable Repitch / Octave / Reverse / Ping-Pong modes.

## Overview

Stereo delay with 0.001–5.0s time range, feedback, tone, and modulation. Use the MODE button to cycle four delay behaviors.

## Parameters

**TIME** (0.0–1.0, default 0.5)
- Delay time (displayed as 0.001–5.0s)
- **Examples**:
  - **Value = 0.0**: 0.001s
  - **Value = 1.0**: 5.0s

**FEEDBACK** (0.0–0.95, default 0.5)
- Feedback amount
- **Examples**:
  - **Value = 0.0**: No repeats
  - **Value = 0.9**: Long repeats

**WET** (0.0–1.0, default 0.5)
- Dry/wet mix
- **Examples**:
  - **Value = 0.0**: Dry only
  - **Value = 1.0**: Wet only

**TONE** (0.0–1.0, default 0.5)
- Feedback tone (0.0 = dark, 1.0 = bright)
- **Examples**:
  - **Value = 0.0**: Low-pass tilt
  - **Value = 1.0**: High-pass tilt

**MOD** (0.0–1.0, default 0.0)
- Modulation depth
- **Examples**:
  - **Value = 0.0**: No modulation
  - **Value = 1.0**: Strong movement

**MODE** (button, default Repitch)
- Cycles Repitch / Octave / Reverse / Ping-Pong

## I/O / CV

- **Audio In**: L/R
- **Audio Out**: L/R
- **CV In**: Time, Tone, Feedback, Wet (±10V)

## Context Menu

- No additional items
