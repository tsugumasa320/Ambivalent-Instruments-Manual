# Grainer - Granular Synthesis Processor

Professional real-time granular synthesis plugin for VCV Rack.

## Overview

Grainer transforms audio input into granular textures through sophisticated grain manipulation. With support for up to 32 simultaneous grains, it offers unprecedented control over granular synthesis parameters.

## Key Features

- **Multi-Grain Engine**: Up to 32 simultaneous grains for rich, complex textures
- **Real-time Processing**: Low-latency granular synthesis optimized for live performance
- **Advanced Modulation**: Full CV control over all parameters
- **High-Quality Audio**: Linear interpolation for pristine pitch shifting
- **Professional Grade**: Built for serious music production and sound design

## Quick Start

1. **Connect Audio**: Patch audio source to AUDIO INPUT
2. **Set Grain Size**: Adjust GRAIN_SIZE_PARAM (0.01s - 2.0s)
3. **Control Density**: Set GRAIN_DENSITY_PARAM (0.1Hz - 100Hz)
4. **Shape Sound**: Use PITCH, SPREAD, and FEEDBACK controls
5. **Mix Output**: Balance with WET_PARAM

## Parameters

### Core Controls

- **Grain Size**: Duration of individual grains (10ms to 2 seconds)
- **Grain Density**: Rate of new grain creation (0.1Hz to 100Hz)
- **Pitch**: Pitch shifting in semitones (±2 octaves)
- **Spread**: Random pitch variation for natural textures
- **Feedback**: Amount of processed signal fed back to input
- **Wet/Dry**: Balance between processed and original signal

### CV Inputs

All parameters support CV modulation:
- Grain Size CV: ±1V = ±0.1s adjustment
- Density CV: ±1V = ±10Hz adjustment  
- Pitch CV: 1V/octave standard
- Spread CV: ±1V = ±10% variation

## Applications

### Sound Design
- Atmospheric textures and pads
- Rhythmic granular sequences
- Experimental sound manipulation

### Music Production
- Vocal processing and effects
- Drum and percussion enhancement
- Ambient and electronic music creation

### Live Performance
- Real-time audio transformation
- Dynamic texture generation
- Interactive granular instruments

## Technical Specifications

- **Buffer Size**: 2-second circular audio buffer
- **Grain Count**: Up to 32 simultaneous grains
- **Envelope**: Hann window for natural grain transitions
- **Sample Rate**: Supports all VCV Rack sample rates
- **Audio Range**: ±5V VCV Rack standard

## Tips & Tricks

1. **Start Simple**: Begin with longer grains and lower density
2. **Use Feedback Carefully**: High feedback can create resonant effects
3. **Modulate Density**: Create rhythmic patterns with CV modulation
4. **Combine with Filters**: Post-processing enhances granular textures
5. **Experiment with Spread**: Adds organic variation to static sounds

## Related Documents

- [Parameter Details](parameters.md)
- [User Guide](user-guide.md)