# Changelog - Ambivalent Instruments

## [2.0.6] - 2026-01-31

### Delay Module

#### Added
- **Octave Mode**: New delay mode with granular pitch shifting
  - Smooth pitch interval transitions without artifacts
  - Based on Clouds-style granular resampling
- **DelayExpander Module**: Extended CV control for Delay module
  - CV inputs for Time, Feedback, Mix parameters
  - LED indicators for parameter values

#### Changed
- Replaced Fade mode with Octave mode
- Improved pitch shifting quality with double-buffer implementation

### All Modules

#### Added
- **Bypass Support**: All modules with audio input now support bypass
  - Right-click menu "Bypass" option
  - Audio passes through unprocessed when bypassed
- **Polyphonic Input Support**: All modules now properly handle polyphonic inputs
  - All polyphonic channels summed to mono output

### Grainer Module

#### Added
- **Waveform Display Numerical Values**
  - Quant value displayed when adjusted
  - Pitch value displayed when adjusted
  - Real-time visual feedback

---

## [2.0.5] - 2025-01-19

### Delay Module

#### Added
- Anti-aliasing filter (16kHz lowpass) applied to all delay modes
- Improved Reverse mode with reduced click noise at short delay times (<0.1s)
- State persistence for mode settings (survives VCV Rack restart)

#### Changed
- Reverse mode simplified to continuous mode only (removed double-buffer mode)
- Improved crossfade length adjustment for short delay times

#### Fixed
- Click noise in Reverse mode at block boundaries
- High-frequency artifacts from interpolation in all modes

#### Removed
- Unused code cleanup: processAnalogMode, analogEngine members (148 lines)
- Unused QualityMode enum and related methods
- Unused AdvancedFeedback processor methods

### Grainer Module

#### Added
- Pitch Quantize LED blinking feature based on harmonic score
- Low harmony intervals blink faster, high harmony stays lit

---

## [2.0.4] - Previous Release

### Modulo Module

#### Changed
- Gain default value changed from 2.0 to 1.0
- Gain range changed from 0-4 to 0-2

---