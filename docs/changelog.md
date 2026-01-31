# Changelog - Ambivalent Instruments

## [2.0.1] - 2026-01-31

### Delay Module

#### Added
- **Octave Mode**: New delay mode replacing Fade mode
  - Granular pitch shifting for smooth pitch interval transitions
  - Based on Clouds-style resampling
  - No artifacts during transitions
- **DelayExpander Module**: Extended CV control for Delay module
  - CV inputs for Time, Feedback, Mix parameters
  - LED indicators for parameter values

#### Changed
- Replaced Fade mode with Octave mode

### All Modules

#### Added
- **Bypass Support**: All modules with audio input can be bypassed
  - Right-click menu "Bypass" option
  - Audio passes through unprocessed when bypassed
- **Polyphonic Input Support**: All modules now handle polyphonic inputs correctly
  - All polyphonic channels are summed to mono output

### Grainer Module

#### Added
- **Waveform Display Numerical Values**
  - Quant value displayed when adjusted
  - Pitch value displayed when adjusted
  - Real-time visual feedback

---

## [2.0.0] - 2025-01-19

### Initial Release

#### Modules Included
- **Delay** - Digital delay with 4 modes (Repitch/Octave/Reverse/Ping-pong)
- **Grainer** - Real-time granular synthesis processor
- **EQ8** - 8-band stereo parametric equalizer
- **XFMN01** - Cross-FM noise synthesizer
- **Modulo** - Modulo operator effect/utility
- **GroupDelay** - Group delay effect using cascaded all-pass filters

#### Delay Module Features
- **4 Delay Modes**:
  - Repitch: Pitch changes when delay time is modulated
  - Octave: Granular pitch shifting with smooth transitions
  - Reverse: Reverse playback delay
  - Ping-pong: Left-right alternating delay
- **High-Quality DSP**:
  - Hermite interpolation for smooth sample reading
  - Granular pitch shifting in Octave mode
- **Controls**:
  - Time: 1ms to 5 seconds (12 o'clock = 2.5 seconds)
  - Feedback with cross-channel routing
  - Dry/Wet mix control
  - Mode selection
- **CV Inputs**: Time, Feedback, Mix modulation

#### Grainer Module Features
- Granular synthesis with pitch quantization
- LED blinking based on harmonic score
- Advanced randomization controls

#### Technical Highlights
- Clean, professional audio quality
- Low CPU usage
- Stereo processing throughout
- CV modulation support
