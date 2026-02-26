# AutoPanTremolo - Stereo Auto-Pan & Tremolo

Stereo auto-pan and tremolo with morphable LFO waveforms and tempo sync.

## Overview

AutoPanTremolo applies rhythmic stereo movement (Pan mode) or volume modulation (Tremolo mode) to a stereo input. The LFO shape can be smoothly morphed between Sine, Triangle, Saw Up, and Sample & Hold. Tempo sync is available via an external clock input or manual Time Mode switch.

## Parameters

**MODE** (switch: Tremolo / Pan, default Pan)
- Selects the effect type
- **Examples**:
  - **Pan**: Stereo auto-panning — signal moves left/right
  - **Tremolo**: Volume modulation — signal pulses in amplitude

**AMOUNT** (0–100%, default 100%)
- Depth of the effect
- **CV In**: Amount CV (±5V)
- **Examples**:
  - **Value = 0%**: No effect
  - **Value = 50%**: Moderate movement
  - **Value = 100%**: Full depth

**FREQ** (0.01–20.0 Hz, default 1.0 Hz)
- LFO rate in free-running (Freq) mode
- In Sync mode with a clock connected, rate locks to the clock tempo
- **CV In**: Freq CV (±5V)
- **Examples**:
  - **Value = 0.5 Hz**: Slow sweep
  - **Value = 5.0 Hz**: Fast wobble

**SHAPE** (0.0–1.0, default 0.0)
- Controls the waveshaping curve of the LFO output
- **Examples**:
  - **Value = 0.0**: Linear response
  - **Value = 1.0**: Shaped / curved response

**WAVEFORM MORPH** (0.0–3.0, default 0.0)
- Smoothly blends between four LFO waveforms
- **Examples**:
  - **Value = 0.0**: Sine
  - **Value = 1.0**: Triangle
  - **Value = 2.0**: Saw Up
  - **Value = 3.0**: Sample & Hold
  - **Value = 0.5**: Blend between Sine and Triangle

**TIME MODE** (switch: Freq / Sync, default Freq)
- Selects free-running or tempo-synced operation
- When a Clock cable is connected, Sync mode is automatically enabled regardless of switch position
- **Examples**:
  - **Freq**: LFO runs at the Freq knob rate
  - **Sync**: LFO locks to external clock

**PHASE** (infinite encoder, default 180°)
- Adjusts the phase offset between left and right channels
- Long-press the Phase knob to toggle Invert
- **CV In**: Phase CV (±5V, maps 0–360°)
- **Examples**:
  - **Phase = 0°**: Both channels in phase (mono movement)
  - **Phase = 180°**: Opposite phase (classic stereo pan)

**INVERT** (toggle via Phase knob long-press)
- Inverts the LFO polarity

## I/O / CV

- **Audio In**: L/R (right unconnected copies left)
- **Audio Out**: L/R
- **CV In**: Amount CV, Freq CV, Phase CV, Clock

## Context Menu

- **AutoPanTremolo**
    - Freq Curve — Adjust the exponential curve for the Freq knob response (presets: 1.40 – 4.00, or ±0.10 step)
