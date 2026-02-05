# XFMN-01 - Cross-FM Noise Synthesizer

Cross-FM synthesizer combining noise and modulation.

## Overview

Two-operator FM synth with delay and filter. Use algorithm, octave, and filter modes to shape the sound.

## Parameters

**DELAY TIME** (0.0–1.0, default 0.05)
- Delay time (displayed as 0.001–5.0s)
- **Examples**:
  - **Value = 0.0**: 0.001s
  - **Value = 1.0**: 5.0s

**DELAY FEEDBACK** (0.0–0.95, default 0.3)
- Delay feedback
- **Examples**:
  - **Value = 0.0**: No repeats
  - **Value = 0.9**: Long repeats

**DELAY MIX** (0.0–1.0, default 0.35)
- Delay mix
- **Examples**:
  - **Value = 0.0**: Dry only
  - **Value = 1.0**: Delay only

**INDEX 1** (0.1–5.0, default 4.0)
- OP1 FM index
- **Examples**:
  - **Value = 0.1**: Light modulation
  - **Value = 5.0**: Heavy modulation

**INDEX 2** (0.1–5.0, default 2.0)
- OP2 FM index
- **Examples**:
  - **Value = 0.1**: Light modulation
  - **Value = 5.0**: Heavy modulation

**OUTPUT GAIN** (-24 to +24dB, default 0dB)
- Output gain
- **Examples**:
  - **Value = -24dB**: Low level
  - **Value = +24dB**: High level

**RATIO 1** (0.1–15.0, default 1.0)
- OP1 ratio
- **Examples**:
  - **Value = 0.1**: Low ratio
  - **Value = 15.0**: High ratio

**RATIO 2** (0.1–15.0, default 1.0)
- OP2 ratio
- **Examples**:
  - **Value = 0.1**: Low ratio
  - **Value = 15.0**: High ratio

**FILTER Q** (0.2–6.0, default 0.8)
- Filter resonance
- **Examples**:
  - **Value = 0.2**: Wide peak
  - **Value = 6.0**: Sharp peak

**PITCH 1** (1–1000Hz, default 440Hz)
- OP1 frequency
- **Examples**:
  - **Value = 1Hz**: Low
  - **Value = 1000Hz**: High

**PITCH 2** (1–1000Hz, default 440Hz)
- OP2 frequency
- **Examples**:
  - **Value = 1Hz**: Low
  - **Value = 1000Hz**: High

**FILTER CUTOFF** (20–12000Hz, default 12000Hz)
- Filter cutoff
- **Examples**:
  - **Value = 20Hz**: Closed
  - **Value = 12000Hz**: Open

**ALGORITHM** (Chaos / Wide / Pure, default Pure)
- FM mode
- **Examples**:
  - **Value = Chaos**: Unstable texture
  - **Value = Pure**: Clean FM

**OCTAVE MODE** (Sub Oct / Bypass / Upper Oct, default Bypass)
- Octave mode
- **Examples**:
  - **Value = Sub Oct**: Lower
  - **Value = Upper Oct**: Higher

**FILTER MODE** (LP / BP / HP, default LP)
- Filter mode
- **Examples**:
  - **Value = LP**: Low-pass
  - **Value = HP**: High-pass

## I/O / CV

- **Audio In**: None
- **Audio Out**: L/R
- **CV In**: Delay Mix, Output Gain, Op1 Freq, Op1 Ratio, Op1 Index, Op2 Freq, Op2 Ratio, Op2 Index, Delay Time, Filter Cutoff

## Context Menu

- No additional items
