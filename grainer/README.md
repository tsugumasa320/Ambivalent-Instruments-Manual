# Grainer - Granular Synthesis Processor

Real-time granular synthesis plugin for VCV Rack.

## Overview

Grainer is a real-time granular synthesis processor with advanced randomization that transforms live audio through controllable grain manipulation. Control pitch, speed, size, and density while introducing organic variations that reveal unexpected textures and sounds.

With support for up to 32 simultaneous grains, Grainer balances precise control with creative unpredictability, enabling musicians to discover new sounds during live performance and sound design.

## Key Features

- **Multi-Grain Engine**: Up to 32 simultaneous grains for rich, complex textures
- **Real-time Processing**: Low-latency granular synthesis optimized for live performance
- **Advanced Modulation**: Full CV control over all parameters
- **High-Quality Audio**: Linear interpolation for pristine pitch shifting
- **Production Ready**: Built for serious music production and sound design

## Quick Start

1. **Connect Audio**: Patch audio source to AUDIO INPUT
2. **Set Grain Size**: Adjust GRAIN_LENGTH_PARAM (1.6ms - 1000ms)
3. **Control Density**: Set DENSITY_PARAM (0.1Hz - 100Hz)
4. **Shape Sound**: Use PITCH, SPREAD controls
5. **Mix Output**: Balance with DRY_WET_PARAM

## Parameters

### Core Controls

- **Grain Length**: Duration of individual grains (1.6ms to 1000ms)
- **Density**: Rate of new grain creation (0.1Hz to 100Hz)
- **Pitch**: Pitch shifting ratio (1/3x to 3x, center = 1x)
- **Position**: Delay from REC position (0-100%: 100%=REC position, 0%=maximum delay)
- **Stereo Spread**: Random stereo positioning for spatial textures (0-1)

### Advanced Controls

- **Pitch Random**: Random pitch variation amount (0-3)
- **Pitch Quantize**: Pitch quantization to musical intervals (0-1)
- **Position Random**: Random position variation within grain placement (0-1)
- **Volume**: Input gain control (-60dB to +6dB, center = 0dB)
- **Dry/Wet**: Balance between original and processed signal (0-1)
- **Reverb**: Built-in reverb amount (0-1)

### Transport Controls

- **Forward/Reverse**: Toggle playback direction (button) - Light illuminates in Reverse mode
- **Freeze**: Freeze current buffer content (button/CV gate) - Light illuminates when frozen

### CV Inputs

All parameters support CV modulation:
- Grain Size CV: ±1V = ±0.1s adjustment
- Density CV: ±1V = ±10Hz adjustment  
- Pitch CV: 1V/octave standard
- Spread CV: ±1V = ±10% variation

## Applications

- Atmospheric textures and pads
- Rhythmic granular sequences
- Experimental sound manipulation

## Technical Specifications

- **Buffer Size**: 2-second circular audio buffer
- **Grain Count**: Up to 32 simultaneous grains
- **Envelope**: Hann window for natural grain transitions
- **Sample Rate**: Supports all VCV Rack sample rates
- **Audio Range**: ±5V VCV Rack standard