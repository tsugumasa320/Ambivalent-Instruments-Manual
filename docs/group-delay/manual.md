# GroupDelay - All-Pass Disperser

All-pass filter disperser for phase-based effects.

## Overview

Creates frequency-dependent phase delay to shape transients and spatial feel. Adjust FREQ/AMOUNT/PINCH to control the effect. It is easy to hear on sources like kick drums. Inspired by Kilohearts Disperser.

## Parameters

**FREQ** (0.0–1.0, default 0.5)
- Center frequency (displayed as 20Hz–20kHz)
- **Examples**:
  - **Value = 0.0**: Around 20Hz
  - **Value = 1.0**: Around 20kHz

**FREQ CV DEPTH** (-1.0–1.0, default 0.0)
- CV depth for FREQ
- **Examples**:
  - **Value = 0.0**: CV off
  - **Value = 1.0**: Full depth

**AMOUNT** (0.0–32.0, default 4.0)
- Number of stages
- **Examples**:
  - **Value = 0**: Minimal effect
  - **Value = 32**: Maximum effect

**AMOUNT CV DEPTH** (-1.0–1.0, default 0.0)
- CV depth for AMOUNT
- **Examples**:
  - **Value = 0.0**: CV off
  - **Value = 1.0**: Full depth

**PINCH** (0.5–16.0, default 5.15)
- Q (resonance)
- **Examples**:
  - **Value = 0.5**: Wide peak
  - **Value = 16.0**: Sharp peak

**PINCH CV DEPTH** (-1.0–1.0, default 0.0)
- CV depth for PINCH
- **Examples**:
  - **Value = 0.0**: CV off
  - **Value = 1.0**: Full depth

## I/O / CV

- **Audio In**: L/R
- **Audio Out**: L/R
- **CV In**: Frequency, Amount, Pinch (±10V)

## Context Menu

- Freq CV Filter (toggle CV smoothing)
