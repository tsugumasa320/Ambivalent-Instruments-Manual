# Grainer - Granular Synthesis Processor

Real-time granular processor for shaping live audio textures.

## Overview

Grainer processes incoming audio with up to 128 grains and a 5-second buffer. Pitch, position, density, and randomization controls enable a wide range of textures.

## Parameters

**GRAIN LENGTH** (50–1000ms, default 525ms)
- Grain duration
- **Examples**:
  - **Value = 50ms**: Short grains
  - **Value = 1000ms**: Long grains

**DENSITY** (0.0–100.0, default 50.0)
- Grain rate (displayed as 0–50Hz)
- **Examples**:
  - **Value = 0.0**: No grains
  - **Value = 100.0**: High density

**PITCH** (-1.0–1.0, default 0.0)
- Playback pitch (displayed as 1/3x–3x)
- **Examples**:
  - **Value = 0.0**: 1x
  - **Value = 1.0**: 3x

**PITCH RANDOM** (0.0–3.0, default 0.0)
- Random pitch range (±octaves)
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

- Soft clip
- Reverb stereo
- Reverb stereo mod
- Reverb decorrelate
- Reverb stereo mod depth (ms)
- Reverb stereo mod rate (Hz)
- Density gain compensation
- Density compensation strength
- Grain voices (4/8/16/32/48/64/96/128)
- Window shape strength
