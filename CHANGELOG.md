# Changelog - Ambivalent Instruments

All notable changes to Grainer and EQ8 plugins.

## [2.0.0] - 2024-12-27

### Grainer
- **Added**: Professional real-time granular synthesis processor
- **Features**: Multi-grain engine supporting up to 32 simultaneous grains
- **Parameters**: 
  - Grain Size: 0.01s to 2.0s grain duration
  - Grain Density: 0.1Hz to 100Hz grain creation rate
  - Pitch: ±2 octaves pitch shifting with 1V/oct CV
  - Spread: Random pitch variation for organic textures
  - Feedback: 0-95% resonant feedback system
  - Wet/Dry: Output level mixing
- **Modulation**: Full CV control for all parameters
- **Audio Quality**: Linear interpolation for high-quality pitch shifting
- **Envelope**: Hann window envelopes for smooth grain transitions

### EQ8  
- **Added**: Professional 8-band stereo parametric equalizer
- **Frequency Bands**: 60Hz, 170Hz, 310Hz, 600Hz, 1kHz, 3kHz, 6kHz, 12kHz
- **Gain Range**: ±12dB adjustment per band (slider center = 0dB)
- **Filter Type**: Biquad peaking filters with Q=1.0
- **Features**: 
  - Real-time coefficient calculation
  - Zero-latency processing
  - Independent L/R channel processing
  - Efficient parameter change detection
- **Optimized**: Music production workflow with fixed, musical frequency bands

## Technical Specifications

### Common Features
- **License**: Proprietary (Non-commercial freeware)
- **Platform**: VCV Rack 2.x compatible
- **SDK**: Built with VCV Rack SDK 2.6.6
- **Architecture**: macOS ARM64, macOS x64, Linux x64, Windows x64
- **Audio Range**: ±5V standard VCV Rack signal range
- **Sample Rate**: Supports all VCV Rack sample rates

### Build Information
- **Version**: 2.0.0
- **Build System**: VCV Rack plugin.mk framework
- **Dependencies**: DaisySP, Soundpipe, STK, FastNoise libraries
- **Distribution**: .vcvplugin packages via GitHub Actions