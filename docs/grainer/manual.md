# Grainer Manual

Real-time granular synthesis processor for VCV Rack.

## Key Features

- **Multi-Grain Engine**: Up to 64 simultaneous grains (default 32)
- **Real-time Processing**: Low-latency granular synthesis optimized for live performance
- **Advanced Modulation**: CV control over core parameters
- **High-Quality Audio**: Linear interpolation for pristine pitch shifting
- **Buffer Control**: 5-second circular buffer with Freeze/Reverse
- **Production Ready**: Built for serious music production and sound design

## Quick Start

1. **Connect Audio**: Patch audio source to AUDIO INPUT L/R
2. **Set Grain Length**: Adjust Grain Length (1.6ms - 1000ms)
3. **Control Density**: Set Density (0 - 50Hz display)
4. **Shape Sound**: Use Pitch / Position / Stereo Spread
5. **Mix Output**: Balance with Dry/Wet and Reverb

## Parameters

### Core Controls

- **Grain Length**: Duration of individual grains (1.6ms to 1000ms)
- **Density**: Rate of new grain creation (0 - 50Hz display)
- **Pitch**: Pitch shifting ratio (1/3x to 3x, center = 1x)
- **Position**: Playback position (0-100%: 0%=oldest, 100%=REC position)
- **Stereo Spread**: Random stereo positioning for spatial textures (0-1)

### Advanced Controls

- **Pitch Random**: Random pitch variation amount (0-3)
- **Pitch Quantize**: Quantize amount (0-1)
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