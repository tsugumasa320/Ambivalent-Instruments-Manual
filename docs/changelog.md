# Changelog - Ambivalent Instruments

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