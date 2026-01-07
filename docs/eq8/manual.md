# EQ8 Manual

8-band stereo parametric equalizer for VCV Rack, optimized for music production.

## Overview

EQ8 is a high-quality equalizer featuring eight carefully selected frequency bands specifically designed for musical applications. Each band provides precise ±12dB gain control, with a master gain function ranging from -70dB to +6dB.

## Key Features

- **8 Fixed Frequency Bands**: Musically optimized frequency selection
- **Stereo Processing**: Independent left/right channel processing
- **High-Quality Filters**: Low shelf/High shelf and peaking bands (Q=1.0)
- **Real-time Processing**: Zero-latency audio processing
- **Output Soft Clipping**: On/Off toggle from context menu
- **Mono Operation**: When right channel is unconnected, left channel is automatically copied to both sides
- **VU Meters**: Visual level display for each band and master output
- **Production Ready**: Optimized for music production workflows

## Quick Start

1. **Connect Audio**: Connect stereo source to LEFT/RIGHT inputs
   - When right channel is unconnected, left channel is automatically applied to both sides
2. **Adjust Bands**: Use frequency sliders to boost/cut
3. **Connect Output**: Connect LEFT/RIGHT outputs to mixer
4. **Fine-tune**: Adjust while listening to the full track
5. **Options**: Right-click to toggle soft clipping on/off

## Frequency Bands

### Low Frequencies
- **60 Hz**: Sub-bass control, fundamental low-end
- **170 Hz**: Bass warmth and punch
- **310 Hz**: Low-mid clarity and definition

### Mid Frequencies
- **600 Hz**: Mid-range presence and vocal clarity
- **1 kHz**: Critical midrange, vocal intelligibility
- **3 kHz**: Upper midrange, vocal presence

### High Frequencies
- **6 kHz**: High-frequency detail and clarity
- **12 kHz**: Air and sparkle, harmonic content

## Control Details

### Gain Control
- **Band Range**: ±12dB per band
- **Master Range**: -70dB to +6dB
- **Center Position**: 0dB (unity gain)
- **Resolution**: Smooth continuous adjustment
- **Response**: Musical peaking curve

### Filter Characteristics
- **Type**: 60Hz low shelf, 12kHz high shelf, 6 peaking bands
- **Q Factor**: 1.0 (musical bandwidth)
- **Phase Response**: Minimized for natural sound
- **Coefficient Calculation**: Real-time updates

## Applications

### Mixing and Mastering
- Track equalization and tonal shaping
- Bus processing and group EQ
- Master bus polishing and enhancement

### Sound Design
- Tonal sculpting of synthesized sounds
- Corrective EQ for recorded audio
- Creative sound manipulation

### Live Performance
- Real-time sound shaping
- Monitor mix adjustment
- Live instrument processing

## Instrument-Specific Applications

### Vocal Processing
- **170 Hz**: Reduce muddiness
- **600 Hz**: Control nasal range
- **3 kHz**: Enhance presence
- **12 kHz**: Add air and brightness

### Drum Processing
- **60 Hz**: Kick drum sub-bass
- **170 Hz**: Kick drum punch
- **1 kHz**: Snare attack
- **6 kHz**: Hi-hat presence

### Bass Guitar
- **60 Hz**: Low-end extension
- **170 Hz**: Fundamental warmth
- **600 Hz**: Note definition
- **3 kHz**: String noise and attack

### Acoustic Guitar
- **310 Hz**: Body warmth
- **1 kHz**: Note clarity
- **6 kHz**: String brightness
- **12 kHz**: Harmonic sparkle

## Technical Specifications

- **Band Count**: 8 fixed frequency bands
- **Gain Range**: ±12dB per band, master -70dB to +6dB
- **Filter Type**: Low/High shelves + peaking (Q=1.0)
- **Processing**: Real-time, zero-latency
- **Channels**: Stereo (independent left/right)
- **Sample Rate**: All VCV Rack sample rates supported
- **Soft Clipping**: Optional sine wave soft clipping
- **VU Meters**: Bandpass filter (Q=0.707) based level detection for each band

## Best Practices

1. **Cut First**: Cut problematic frequencies before boosting
2. **Musical Context**: Always adjust EQ within the context of the full mix
3. **Gentle Adjustments**: Small changes often yield better results
4. **Band Selection**: Each band targets specific musical elements
5. **Monitor Levels**: Use VU meters to monitor band activity levels
6. **Soft Clipping**: Enable when applying significant boosts to prevent distortion
7. **Mono Processing**: Mono sources can be processed using left input only