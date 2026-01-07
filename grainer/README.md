\page grainer_manual Grainer - Granular Synthesis Processor

# Grainer - Granular Synthesis Processor

Real-time granular synthesis plugin for VCV Rack.

## Overview

Grainer is a real-time granular synthesis processor with advanced randomization that transforms live audio through controllable grain manipulation. Control pitch, size, position, and density while introducing organic variations that reveal unexpected textures and sounds.

With support for up to 64 simultaneous grains (32 by default) and a 5-second recording buffer, Grainer balances precise control with creative unpredictability for live performance and sound design.

This VCV Rack module is based on the original Max for Live grainer plugin: https://tsugumasa320.gumroad.com/l/grainer

## Key Features

- **Multi-Grain Engine**: Up to 64 simultaneous grains (default 32)
- **Real-time Processing**: Low-latency granular synthesis optimized for live performance
- **Advanced Modulation**: CV control over core parameters
- **High-Quality Audio**: Linear interpolation for pristine pitch shifting
- **Buffer Control**: 5-second circular buffer with Freeze/Reverse
- **Intuitive UI**: Optimized slider designs and visual feedback without distracting tooltips
- **Production Ready**: Built for serious music production and sound design

## Quick Start

1. **Connect Audio**: Patch audio source to AUDIO INPUT L/R
2. **Set Grain Length**: Adjust Grain Length (50ms - 1000ms, default 525ms)
3. **Control Density**: Set Density (0 - 50Hz display)
4. **Shape Sound**: Use Pitch / Position / Stereo Spread
5. **Mix Output**: Balance with Dry/Wet and Reverb

## Parameters

### Core Controls

- **Grain Length**: Duration of individual grains (50ms to 1000ms, default 525ms)
- **Density**: Rate of new grain creation (0 - 50Hz display)
- **Pitch**: Pitch shifting ratio (1/3x to 3x, center = 1x)
- **Position**: Playback position (0-100%: 0%=oldest, 100%=REC position)
- **Stereo Spread**: Random stereo positioning for spatial textures (0-1)

### Advanced Controls

- **Pitch Random**: Random pitch variation amount (0-3)
- **Pitch Quantize**: Quantize amount (0-1, default 1.0, double-click resets to 1.0)
  - **Range**: 0 = no quantization, 1 = full quantization
  - **Algorithm**: Searches for best-fit rational pitch ratios (1/1, 1/2, 2/3, 3/4, etc.) up to denominator 8
  - **Activation threshold**: 0.02 (2%) - below this value, quantization is completely inactive
  - **Full activation**: 0.08 (8%) - above this value, quantization operates at full strength
  - **LED brightness**: Indicates how well the current parameter value matches a clean rational ratio
    - Bright LED = parameter value is close to a simple ratio (e.g., 0.5 = 1/2, 0.33 = 1/3)
    - Dim LED = parameter value is between ratios or quantization is weak
    - Off LED = quantization inactive (value ≤ 2%) or no good ratio match found
- **Window Shape**: Hann shape bias (-1 to +1)
- **Position Random**: Random position variation (0-1)
- **Input Gain**: Input gain (0-1 linear)
- **Dry/Wet**: Balance between original and processed signal (0-1)
- **Reverb**: Built-in reverb amount (0-1)

### Transport Controls

- **Forward/Reverse**: Toggle playback direction (button)
- **Freeze**: Freeze current buffer content (button/CV gate)

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
- **Pitch Quantization**: Advanced rational number algorithm
  - Searches denominators 1-8 for best-fit pitch ratios
  - Includes error weighting (40x scale factor) and complexity penalty (0.2x per denominator)
  - Smooth activation curve between 2% and 8% parameter values
  - LED brightness reflects quantization effectiveness and ratio proximity
