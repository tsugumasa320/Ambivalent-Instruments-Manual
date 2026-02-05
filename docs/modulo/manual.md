# Modulo - Modulo Operator Utility Module

Modulo-based waveform folding utility.

## Overview

Applies modulo processing to a mono input signal, with dry/wet mix and output gain for shaping the result.

## Parameters

**GAIN** (0.0–2.0, default 0.5)
- Output gain (wet signal)
- **Examples**:
  - **Value = 0.0**: Mute
  - **Value = 2.0**: Max

**MODULO** (0.01–1.0, default 0.5)
- Modulo value
- **Examples**:
  - **Value = 0.01**: Heavy folding
  - **Value = 1.0**: Light folding

**MIX** (0.0–1.0, default 0.5)
- Dry/wet mix
- **Examples**:
  - **Value = 0.0**: Dry only
  - **Value = 1.0**: Wet only

## I/O / CV

- **Audio In**: Mono
- **Audio Out**: Mono
- **CV In**: Gain, Modulo, Mix (±10V)

## Context Menu

- No additional items
