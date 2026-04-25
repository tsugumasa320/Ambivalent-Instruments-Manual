# Changelog - Ambivalent Instruments

## [2.0.6] - 2026-04-20

### New Modules

- **Feedback EQ8**: Stereo 8-band parametric EQ with a bipolar Feedback Amount control that sends part of the EQ output back into the input. Push any band up to color the feedback and drive the module into resonance or self-oscillation, with built-in limiting keeping the loop stable.

### Improved

- **EQ8, Delay, Modulo, Cheby, AutoPan**: Polyphonic inputs with per-channel expansion.
- **Group Delay**: Smoothed modulated parameter updates to reduce zipper noise.
- **Grainer**: Fixed a bug where pressing Freeze reset the reverb state.

## [2.0.5] - 2026-04-04

### New Modules

- **NØ!SE//ERR**: Dual-output noise oscillator with switchable `SIN/SAW` and `RECT/RAND` banks, band-pass shaping, wavefold, drive, and paired outputs for moving between harmonic tone and unstable noise.

### Improved

- **Grainer**: Reduced seam clicks and improved sub-unity pitch quantize behavior.
- **Grainer**: Refined DSP state handling, persistence, and Rack adapter behavior for more consistent patch restore and runtime control.
- **AutoPanTremolo**: Polyphonic audio inputs are now summed per side while the stereo outputs stay fixed at one channel per port.
- **Cheby**: Polyphonic stereo inputs now follow the same summed-input path consistently, with both outputs fixed at one channel per port.

## [2.0.4] - 2026-03-14

### Improved

- **AutoPanTremolo**: The built-in waveform screen is easier to read at high Amount settings, with cleaner spacing inside the display.
- **Seq8**: The output jack layout now matches the panel labeling, with CV on the left and Gate on the right, and the panel artwork has been updated to reflect the final layout.

## [2.0.3] - 2026-02-24

### New Modules

- **AutoPanTremolo**: Stereo auto-pan and tremolo effect with morphable LFO waveforms (Sine/Triangle/Saw/S&H), tempo sync via external clock, and adjustable stereo phase
- **Cheby**: Chebyshev harmonic generator with 8 independent harmonic sliders (H1–H8), dry/wet mix, and optional soft clip output
- **Seq8**: 8-step CV/Gate sequencer with internal tempo (40–200 BPM) and external clock sync (0.25x / 0.5x / 1x / 2x / 4x multiplier)

### Fixed

- **Grainer**: Fixed implementation bug that was converting input audio to mono.
- **Delay**: Fixed typo in panel labeling.
- **All**: Reduced processing load through optimization.


## [2.0.2] - 2026-02-04

### Delay Module

#### Changed
- **Smoother mode switching**: Reduced clicks when changing delay modes
- **Reverse playback refinement**: Cleaner reverse repeats and time changes
- **Modulation updates**:
  - Reverse mode adds chorus-style movement
  - Octave mode uses tremolo-style movement

#### Improved
- **Mode button tooltip**: Shows MOD knob behavior for each mode

#### Fixed
- **DelayExpander clock**: Stable clock pulses at very short delay times

### Grainer Module

#### Added
- **Freeze buffer persistence**: Frozen sample buffer is now saved with your patch and restored on reload

#### Improved
- **Parameter tooltips**: Hover over knobs to see descriptions

#### Fixed
- **Startup stability**: Fixed a crash on startup/exit

### Modulo Module

#### Improved
- **Parameter tooltip**: Modulo Value knob shows formula

---

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

## [2.0.0] - 2026-01-19

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
