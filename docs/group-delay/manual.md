# GroupDelay - All-Pass Disperser

**Note: This manual is AI-generated and will be updated progressively.**

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
2. **CV Pre-processing** (2025 enhancement)
   - IIR low-pass filter applied to frequency CV input (~2Hz cutoff)
   - Low-frequency LFO modulation passes through, high-frequency jitter removed
   - Oscillation and artifact prevention
3. All-pass filter chain processing
   - Specified number of stages in cascade
   - Fractional values use equal-power blending
   - **Gradual Parameter Updates** (2025 enhancement)
     - 2 filters updated per frame with frequency/Q
     - All 32 filters updated over 16 frames
     - Distributed parameter change impact reduces oscillation
4. Soft clipping (±5V range)
5. Output level LED for visual feedback

## Stability Measures (2025 Enhancement)

Multiple safeguards ensure stable group delay operation:

### Numerical Safety
- **Double-precision filter computation**: All filter coefficients managed in 64-bit precision
- **Quantization noise reduction**: Minimized numerical errors during 32-stage cascade

### Oscillation Prevention
1. **IIR LFO Filter** (~2Hz cutoff)
   - Removes high-frequency jitter from CV inputs
   - Passes LFO signals (0.1-10Hz), removes noise

2. **Gradual Parameter Updates**
   - 2 filters updated per frame
   - Parameter changes distributed over 16 frames
   - Reduces coefficient update shock

3. **Fast Coefficient Smoothing**
   - Update rate: 0.5% per sample
   - ~180ms @ 44.1kHz to reach target value
   - Prevents clicks and artifacts

4. **Auto-reset on anomalies**
   - Detects NaN/Inf output and auto-resets
   - Prevents error propagation

### Recommended Settings
- **Low risk**: AMOUNT = 8~16 stages (maintains effect, improved stability)
- **Medium risk**: AMOUNT = 16~24 stages (stronger effect, moderate stability)
- **High risk**: AMOUNT = 24~32 stages (maximum effect, caution with LFO)

### ⚠️ Frequency Modulation Warning

**Excessive modulation of the FREQ parameter can cause the filter to self-oscillate.** Follow these guidelines:

**Safe Frequency Modulation**:
- **LFO frequency**: Keep within 0.1~5Hz range (IIR filter removes high-frequency jitter)
- **Modulation speed**: Use gradual, smooth changes
- **CV attenuation**: Avoid excessive modulation depth (use CV attenuator)

**If Oscillation Occurs**:
1. **Fix FREQ**: Disconnect CV input, set to fixed value via knob
2. **Reduce AMOUNT**: Decrease to 16 stages or lower
3. **Decrease CV amplitude**: Attenuate LFO output level
4. **Slow LFO rate**: Use 0.1~1Hz for slow, gentle modulation

**Critical**: Using AMOUNT = 24~32 stages with fast CV modulation (>5Hz) significantly increases oscillation risk.

## Applications

- Transient thickness and width control
- Stereo image adjustment
- Effect fine-tuning
- Creative spatial effects
- Phase manipulation
- Dynamic spatial effects with LFO modulation
