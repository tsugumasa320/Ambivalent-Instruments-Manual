# XFMN-01 - Cross-FM Noise Synthesizer

Cross-FM noise synthesizer with advanced modulation capabilities for VCV Rack

## Overview

XFMN-01 is an experimental synthesizer module that combines Cross-FM (frequency modulation) with chaotic noise generation. Through oscillator cross-modulation, organic noise algorithms, and non-linear distortion processing, it creates unique sonic textures that transcend traditional FM synthesis boundaries.

### Key Features

- **Dual FM Operators**: Two independently controllable FM operators
- **3 FM Modes**: Chaos, Wide, Pure different FM characteristics
- **Delay Effects**: High-quality delay processing
- **3-Mode Filter**: LP/BP/HP filtering
- **Octave Mode**: Sub Oct/Bypass/Upper Oct 3-stage range
- **Comprehensive CV Control**: Full CV control over all parameters
- **Real-time Processing**: Zero-latency audio processing optimized for performance

## Quick Start

1. **Set Base Frequency**: Set operator 1 fundamental with PITCH 1
2. **FM Modulation**: Create FM timbre with RATIO 1 and INDEX 1
3. **FM Mode Selection**: Choose Chaos/Wide/Pure with top switch
4. **Add Delay**: Adjust delay effects with TIME, FEEDBACK, MIX
5. **Apply Filter**: Filter with CUTOFF and Q controls
6. **Adjust Volume**: Set final volume with OUTPUT GAIN

## Parameters

### Operator 1

#### **PITCH 1**: Base Frequency (approx 20Hz - 1kHz)
- **Display**: Logarithmic frequency display in Hz
- **CV Control**: 1V/Oct standard, ±5 octaves range
- **Musical Examples**:
  - **Center (440Hz)**: A4 standard pitch - musical reference frequency
  - **Low (110Hz)**: A2 bass register - deep, rich fundamental
  - **High (1760Hz)**: A6 treble register - bright, transparent tone
- **Applications**: Key setting, basslines, lead melody fundamentals
- **CV Response**: Exponential (musical), high-precision 1V/Oct tracking

#### **RATIO 1**: Modulator Frequency Ratio (0.1 - 15.0, default: 1.0)
- **Display**: Floating-point ratio display
- **Musical Examples**:
  - **1.0**: 1:1 ratio - Pure sine wave, cleanest possible tone
  - **2.0**: 1:2 ratio - Bright, metallic, classic FM bell sound
  - **3.14**: π ratio - Non-integer complex harmonics, experimental textures
  - **0.5**: 1:0.5 ratio - Sub-harmonic bass, warm undertones
- **Applications**: Timbral character control, harmonic structure shaping
- **Features**: Non-integer ratios enable non-harmonic overtone generation

#### **INDEX 1**: FM Modulation Index (0.1 - 5.0, default: 4.0)
- **Display**: Linear modulation depth indicator
- **Sonic Examples**:
  - **0.0**: No modulation - Pure sine wave carrier
  - **1.0**: Moderate modulation - Balanced FM timbre
  - **5.0**: Heavy modulation - Complex, aggressive harmonics
  - **10.0**: Extreme modulation - Noise-like dense overtones
- **Applications**: Timbral complexity control, dynamics expression, percussive attacks
- **Technical**: Bessel function-based predictable sideband generation

### Operator 2

#### **PITCH 2**: Secondary Frequency (approx 20Hz - 1kHz)
- **Function**: Independent second FM voice for cross-modulation
- **CV Control**: 1V/Oct standard, ±5 octaves range
- **Applications**: Harmony, unison detuning, cross-modulation source
- **Features**: Receives cross-modulation from Operator 1

#### **RATIO 2 / INDEX 2**: Operator 2 Ratio & Modulation Index
- **RATIO 2**: 0.1 - 15.0 (default: 1.0)
- **INDEX 2**: 0.1 - 5.0 (default: 2.0)
- **Interaction**: Creates complex FM interaction with Operator 1

### FM Mode Selection

#### **FM Mode**: 3 FM characteristics (Chaos/Wide/Pure)
- **Chaos**: Chaotic and complex overtone structure
- **Wide**: Rich timbre with wide frequency range
- **Pure**: Clean and clear FM sound

### Delay Section

#### **TIME**: Delay Time (0.001 - 5 seconds)
- **Exponential characteristic**: Musical control from short to long times

#### **FEEDBACK**: Delay Feedback (0.0 - 0.95)
- **Function**: Feedback of delay signal to input
- **Sonic Effect**: Echo, reverb-like spatial sense

#### **MIX**: Delay Mix (0.0 - 1.0)
- **0.0**: Completely dry (original signal only)
- **1.0**: Completely wet (delay signal only)

### Octave Mode

#### **Octave Mode**: Frequency Range Adjustment (Sub Oct/Bypass/Upper Oct)
- **Sub Oct**: Low frequency focus, bass range
- **Bypass**: Standard frequency range
- **Upper Oct**: High frequency focus, lead range

### Filter Section

#### **CUTOFF**: Filter Cutoff (200Hz - 12kHz)
- **Function**: Filter frequency setting

#### **Q**: Filter Resonance (0.2 - 6.0)
- **Function**: Emphasis around cutoff frequency

#### **Filter Mode**: 3 filter types (LP/BP/HP)
- **LP (Low Pass)**: High frequency cut, warm timbre
- **BP (Band Pass)**: Band-pass filtering, telephone voice effect
- **HP (High Pass)**: Low frequency cut, clear and bright timbre

### Output

#### **OUTPUT GAIN**: Master Output Gain (-24dB - +24dB)
- **Standard**: VCV Rack standard ±5V output
- **Headroom**: Soft clipping with tanh limiting

## Signal Flow

```
[OP1] ──┬── [FM ENGINE] ──┬── [DELAY] ── [FILTER] ── [OUTPUT GAIN] ── [OUTPUT L/R]
        │                │
[OP2] ──┴────────────────┘
        │
   [FM MODE]
```

## CV Inputs

Main parameter CV modulation support (±5V):
- **OP1/2 FREQ CV**: Operator frequency CV (1V/Oct)
- **OP1/2 RATIO CV**: Frequency ratio CV
- **OP1/2 INDEX CV**: FM modulation depth CV
- **DELAY TIME CV**: Delay time CV
- **DELAY MIX CV**: Delay mix CV
- **FILTER CUTOFF CV**: Filter cutoff CV
- **OUTPUT GAIN CV**: Output gain CV