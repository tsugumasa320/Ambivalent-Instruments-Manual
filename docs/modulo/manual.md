# Modulo - Modulo Operator Utility Module

Modulo operator utility module with fixed gain scaling and dry/wet mixing.

## Overview

Modulo applies modulo operation to input signals for waveform folding effects. With dry/wet mixing and output gain control, it supports subtle waveform shaping to dramatic sound design.

## Quick Start

1. Connect audio source to AUDIO INPUT
2. Adjust MODULO knob to control waveform folding
   - Lower values: More folding
   - Higher values: Less folding
3. Use MIX knob to balance between dry and processed signal
   - 0.0: 100% dry (original signal)
   - 1.0: 100% wet (modulo processed signal only)
4. Use GAIN knob to adjust output level

## Parameters

### Main Controls

**GAIN** (0.0〜4.0, default 2.0)
- Output gain (wet signal only)
- 0.0: Muted
- 2.0: Standard (+6dB)
- 4.0: Maximum (+12dB)
- CV input supported (±10V range)

**MODULO** (0.01〜1.0, default 1.0)
- Modulo divisor value
- Lower values produce more waveform folding
- CV input supported (±10V range)

**MIX** (0.0〜1.0, default 1.0)
- Dry/Wet mix ratio
- 0.0: 100% dry (original signal)
- 1.0: 100% wet (modulo processed signal)
- Equal-power crossfade used
- CV input supported (±10V range)

## Signal Processing Flow

1. Input signal scaled to standard audio level (-5V~+5V → -1.0~+1.0)
2. Modulo operation applied for waveform folding (std::fmod)
3. Result scaled back to standard voltage level (-1.0~+1.0 → -5V~+5V)
4. Equal-power crossfade for dry/wet mixing
5. Output gain applied (wet signal only)

## Applications

- Waveform shaping and texture generation
- Rhythmic and groove manipulation
- Experimental sound design
- Sub-oscillator usage
