\page eq8_manual EQ8 - 8-Band Parametric Equalizer

# EQ8 - 8-Band Parametric Equalizer

8-band stereo parametric equalizer optimized for music production in VCV Rack.

## Overview

EQ8 provides high-quality equalization with eight carefully selected frequency bands designed for musical applications. Each band offers precise ±12dB gain control with Butterworth characteristics (Q=0.707) biquad filters, plus a master gain stage from -70dB to +6dB.

## Key Features

- **8 Fixed Frequency Bands**: Musically optimized frequency selection
- **Stereo Processing**: Independent left/right channel processing
- **High-Quality Filters**: Low/High shelves with peaking bands (Q=0.707)
- **Real-time Processing**: Zero-latency audio processing
- **Output Soft Clip**: Optional sine soft clip from the context menu
- **Production Ready**: Optimized for music production workflows

## Control Details

### Gain Control
- **Band Range**: ±12dB per band
- **Master Range**: -70dB to +6dB
- **Center Position**: 0dB (unity gain)
- **Resolution**: Smooth continuous adjustment
- **Response**: Musical peaking curve

### Filter Characteristics
- **Type**: 60Hz low shelf, 12kHz high shelf, 6 peaking bands
- **Q Factor**: 0.707 (Butterworth characteristics)
- **Phase Response**: Minimized for natural sound
- **Coefficient Calculation**: Real-time updates

## Technical Specifications

- **Bands**: 8 fixed frequency bands
- **Gain Range**: ±12dB per band, master -70dB to +6dB
- **Filter Type**: Low/High shelves + peaking (Q=0.707)
- **Processing**: Real-time, zero-latency
- **Channels**: Stereo (independent L/R)
- **Sample Rate**: All VCV Rack sample rates supported
