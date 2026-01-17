# GroupDelay - All-Pass Disperser

Group delay effect using cascaded all-pass filters for transient shaping and phase dispersion.

## Overview

GroupDelay uses cascaded all-pass filters to create frequency-dependent phase delay (group delay). This allows for rich transient enhancement, stereo width adjustment, and subtle to dramatic phase-based effects.

## Quick Start

1. Connect audio sources to L/R AUDIO INPUTS
2. Adjust FREQ knob to set center frequency (20Hz-20kHz)
3. Use AMOUNT knob to control number of all-pass stages (0-32)
   - 0: Bypass (no phase delay)
   - Increasing values: More group delay
4. Adjust PINCH to control resonance Q (0.5-16)

## Parameters

### Main Controls

**FREQ** (20Hz~20kHz, default 1kHz)
- Center frequency for phase manipulation
- Suitable for pitch-shifting and envelope control
- CV input supported (±10V range)
- CV attenuation trim included

**AMOUNT** (0~32, default 4)
- Number of all-pass filter stages
- 0: Bypass (no phase delay)
- Higher values: More pronounced group delay
- Fractional values allow smooth adjustment
- CV input supported (±10V range)
- CV attenuation trim included

**PINCH** (0.5~16, default 0.3)
- Filter Q value
- 0.5: Wide peak, subtle resonance
- Higher values: Narrower peak, emphasized resonance
- CV input supported (±10V range)
- CV attenuation trim included

### Inputs/Outputs

- **L IN**: Left channel input
- **R IN**: Right channel input
- **L OUT**: Left channel output
- **R OUT**: Right channel output

## Signal Processing Flow

1. Input signal reading
2. All-pass filter chain processing
   - Specified number of stages in cascade
   - Fractional values use equal-power blending
3. Soft clipping (±5V range)
4. Output level LED for visual feedback

## Applications

- Transient thickness and width control
- Stereo image adjustment
- Effect fine-tuning
- Creative spatial effects
- Phase manipulation
