# Grainer - Granular Synthesis Processor

Real-time granular synthesis plugin for VCV Rack.

## Overview

Grainer is a real-time granular synthesis processor with advanced randomization that transforms live audio through controllable grain manipulation. Control pitch, size, position, and density while introducing organic variations that reveal unexpected textures and sounds.

With support for up to 64 simultaneous grains (32 by default) and a 5-second recording buffer, Grainer balances precise control with creative unpredictability for live performance and sound design.

This VCV Rack module is based on the original Max for Live grainer plugin: https://tsugumasa320.gumroad.com/l/grainer

The built-in reverb is based on the high-quality implementation from Mutable Instruments Clouds.

## Key Features

- **Multi-Grain Engine**: Up to 64 simultaneous grains (default 32)
- **Real-time Processing**: Low-latency granular synthesis optimized for live performance
- **Advanced Modulation**: CV control over core parameters
- **High-Quality Audio**: Linear interpolation for pristine pitch shifting
- **Buffer Control**: 5-second circular buffer with Freeze/Reverse

## Quick Start

1. **Connect Audio**: Patch audio source to AUDIO INPUT L/R
2. **Set Grain Length**: Adjust Grain Length (50ms - 1000ms, default 525ms)
3. **Control Density**: Set Density (0 - 50Hz display)
4. **Shape Sound**: Use Pitch / Position / Stereo Spread
5. **Mix Output**: Balance with Dry/Wet and Reverb

## Parameters

### Core Controls

- **Grain Length**: Duration of individual grains (50ms to 1000ms, default 525ms)
  - **GUI Display**: Shows current value in milliseconds (e.g., "525ms")
  - **Double-click**: Resets to default 525ms
- **Density**: Rate of new grain creation (0 - 50Hz display)
  - **GUI Display**: Shows frequency in Hz (e.g., "25.0Hz")
  - **Range**: Internal processing supports higher values, display capped at 50Hz for clarity
- **Pitch**: Pitch shifting ratio (1/3x to 3x, center = 1x)
  - **GUI Display**: Shows pitch multiplier (e.g., "1.50x", "0.67x")
  - **Center Position**: 1.00x (original pitch)
  - **Double-click**: Resets to 1.00x
- **Position**: Playback position (0-100%: 0%=oldest, 100%=REC position)
  - **GUI Display**: Shows percentage (e.g., "75%")
  - **0%**: Oldest recorded audio in buffer
  - **100%**: Most recent recording position
- **Stereo Spread**: Random stereo positioning for spatial textures (0-1)
  - **GUI Display**: Shows percentage (e.g., "50%")
  - **0%**: Mono/center positioning (all grains panned center)
  - **50%**: Moderate stereo spread (±25% pan range around center)
  - **100%**: Full stereo width randomization (grains can appear anywhere in stereo field)

### Advanced Controls

- **Pitch Random**: Random pitch variation amount (0-3)
  - **GUI Display**: Shows decimal value (e.g., "1.25")
  - **0**: No pitch randomization (all grains use exact pitch setting)
  - **1**: ±1 octave random variation (2^-1 to 2^+1 = 0.5x to 2.0x)
  - **2**: ±2 octaves random variation (2^-2 to 2^+2 = 0.25x to 4.0x) 
  - **3**: ±3 octaves random variation (2^-3 to 2^+3 = 0.125x to 8.0x)
- **Pitch Quantize**: Controls how much pitch values are quantized to specific pitch ratios (0-1, default 1.0, double-click resets to 1.0)
  - **GUI Display**: Shows percentage (e.g., "100%" for full quantization, "0%" for none)
  - **LED Display**: Color-coded brightness indicating proximity to musical intervals
  - **Behavior Examples**:
    - **Quantize = 0**: Continuous pitch changes (no quantization)
    - **Quantize = 0.5**: Pitch snaps to 0.5x, 1.0x, 1.5x, 2.0x... multiples
    - **Quantize = 1.0**: Complete quantization to integer ratios (1.0x, 2.0x, 3.0x...)
  - **Use Cases**: Helpful for creating harmonic relationships in musical contexts
  - **LED Brightness**: Uses rational number calculation to indicate proximity to simple musical ratios (octaves, fifths, etc.)
    - Bright LED = current pitch value is close to a simple musical ratio (e.g., 0.5 = octave down, 0.33 = fifth + octave down)
    - Dim LED = pitch value is between musical ratios
    - Off LED = no clear musical ratio match
  - **Musical Behavior**:
    - When quantize = 0: Pitch changes smoothly and continuously
    - When quantize = 1: Pitch jumps in discrete steps, creating more pronounced pitch transitions
    - Intermediate values blend between smooth and stepped behavior
- **Window Shape**: Hann shape bias (-1 to +1)
  - **GUI Display**: Shows decimal value (e.g., "0.25", "-0.50")
  - **-1**: Left-biased window shape
  - **0**: Symmetric Hann window (center position)
  - **+1**: Right-biased window shape
- **Position Random**: Random position variation (0-1)
  - **GUI Display**: Shows percentage (e.g., "30%")
- **Input Gain**: Input gain (0-1 linear)
  - **GUI Display**: Shows percentage (e.g., "75%")
  - **0%**: No input signal
  - **100%**: Full input gain
- **Dry/Wet**: Balance between original and processed signal (0-1)
  - **GUI Display**: Shows percentage (e.g., "50%")
  - **0%**: 100% dry (original signal only)
  - **100%**: 100% wet (processed signal only)
- **Reverb**: Built-in reverb amount (0-1) - based on Mutable Instruments Clouds reverb implementation
  - **GUI Display**: Shows percentage (e.g., "25%")
  - **0%**: No reverb
  - **100%**: Maximum reverb effect

- **Forward/Reverse**: Toggle playback direction (button)
  - **GUI Display**: Button shows current direction with arrow icon
  - **Forward**: Normal playback direction (default)
  - **Reverse**: Reversed playback direction
- **Freeze**: Freeze current buffer content (button/CV gate)
  - **GUI Display**: Button illuminated when active
  - **Off**: Normal recording mode (buffer continuously updates)
  - **On**: Buffer content frozen (no new recording, existing content preserved)

### CV Inputs

Core parameters support CV modulation (±5V bipolar):
- Grain Length CV
- Density CV
- Pitch CV (1V/oct option in context menu)
- Pitch Random CV
- Position CV
- Position Random CV
- Stereo Spread CV
- Input Gain CV
- Dry/Wet CV
- Reverb CV
- Window Shape CV

## Applications

- Atmospheric textures and pads
- Rhythmic granular sequences
- Experimental sound manipulation

## Technical Specifications

- **Buffer Size**: 5-second circular audio buffer (at 44.1kHz)
- **Grain Count**: Up to 64 simultaneous grains (default 32)
- **Envelope**: Hann window for natural grain transitions
- **Sample Rate**: Supports all VCV Rack sample rates
- **Audio Range**: ±5V VCV Rack standard
- **Pitch Quantization**: Step-based algorithm that discretizes pitch parameter values
  - Applies quantization steps to create discrete pitch intervals
  - LED brightness uses rational number algorithm (denominators 1-8) for visual feedback
  - LED calculation includes error weighting and complexity penalty for musical interval detection
- **Reverb**: High-quality reverb engine based on Mutable Instruments Clouds implementation
  - Provides atmospheric spatial processing for granular textures
