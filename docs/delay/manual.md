# Delay - Stereo Delay Module

Professional stereo delay engine with multiple delay modes including Classic, Ping-pong, Analog, and Reverse. Features 3rd-order Lagrange interpolation for high-quality audio processing.

## Overview

Delay is a professional-grade stereo delay effect module offering four distinct delay modes with high-quality audio processing. It features adjustable delay time, feedback, tone filter, modulation depth, and dry/wet mixing, making it suitable for various musical applications from subtle ambience to dramatic sound design.

## Quick Start

1. Connect audio source to AUDIO L/R INPUT
2. Connect output to AUDIO L/R OUTPUT
3. Select delay mode using MODE button (4 modes available)
4. Adjust TIME knob to set delay time
5. Use FEEDBACK knob to control repetition
6. Use WET knob to balance between dry and delayed signal

## Parameters

### Main Controls

**TIME** (0.0〜1.0, default 0.5)
- Delay time control
- Exponential curve for musical response
- CV input supported
- Range: approximately 10ms to 2 seconds (dependent on mode)

**FEEDBACK** (0.0〜0.95, default 0.5)
- Feedback amount for delay repetitions
- Higher values create more echoes
- CV input supported
- Maximum 95% to prevent infinite feedback loops

**WET** (0.0〜1.0, default 0.5)
- Dry/Wet mix ratio
- 0.0: 100% dry (original signal)
- 1.0: 100% wet (delayed signal only)
- Equal-power crossfade used
- CV input supported

**TONE** (0.0〜1.0, default 0.5)
- Tone filter for delay feedback path
- Lower values: Low-pass filter (warmer sound)
- Higher values: High-pass filter (brighter sound)
- CV input supported

**MOD** (0.0〜1.0, default 0.0)
- Modulation depth (WOW effect)
- Adds subtle pitch modulation to delay
- CV input supported
- Creates tape-like wow and flutter effects

### Mode Selection

**MODE BUTTON**
- Cycles through 4 delay modes:
  1. **Classic**: Standard stereo delay
  2. **Ping-pong**: Delay bounces between left and right channels
  3. **Analog**: Simulates analog delay with subtle warmth
  4. **Reverse**: Reversed playback of delay buffer

Mode lights indicate current mode:
- **Classic Light**: Classic mode active
- **Pingpong Light**: Ping-pong mode active
- **Analog Light**: Analog mode active
- **Reverse Light**: Reverse mode active

## Signal Processing Flow

1. Input signal (L/R) enters delay buffer
2. Delay time controls read position from buffer
3. Tone filter applied to feedback path
4. Modulation adds subtle pitch variation (if MOD > 0)
5. Feedback sends delayed signal back to input
6. Dry/Wet crossfade for output mixing
7. Output signal (L/R) with delayed content

## Delay Modes

### Classic Mode
- Standard stereo delay with identical delay time for both channels
- Suitable for traditional delay effects
- Clean, transparent sound

### Ping-Pong Mode
- Delay alternates between left and right channels
- Creates rhythmic, bouncing echo patterns
- Excellent for stereo separation

### Analog Mode
- Simulates analog delay characteristics
- Subtle warmth and saturation
- Slight frequency response variation

### Reverse Mode
- Reversed playback of delay buffer
- Creates unique, backwards echo effects
- Ideal for ambient and experimental sounds

## CV Inputs

All CV inputs accept ±10V signals:
- **TIME CV**: Modulates delay time
- **TONE CV**: Modulates tone filter
- **FEEDBACK CV**: Modulates feedback amount
- **WET CV**: Modulates dry/wet mix

## Usage Examples

### Basic Delay Effect
1. Set MODE to Classic
2. Adjust TIME to desired delay (around 0.3-0.5 for quarter notes)
3. Set FEEDBACK to 0.3-0.5 for moderate repeats
4. Adjust WET to blend delayed signal

### Ping-Pong Echo
1. Set MODE to Ping-pong
2. Adjust TIME for rhythmic echo (around 0.4)
3. Set FEEDBACK to 0.4-0.6
4. Use WET at 0.5-0.7 for prominent stereo effect

### Ambient Wash
1. Set MODE to Analog
2. Use longer TIME (0.7-1.0)
3. High FEEDBACK (0.7-0.8)
4. Lower WET (0.2-0.4) for subtle ambience
5. Add slight MOD (0.1-0.2) for warmth

### Reverse Reverb
1. Set MODE to Reverse
2. Medium TIME (0.4-0.6)
3. Moderate FEEDBACK (0.3-0.5)
4. Low WET (0.1-0.3) for atmospheric effect

## Tips and Tricks

- **Self-Oscillation**: Set FEEDBACK to 0.8-0.9 and TIME to create rhythmic patterns
- **Ducking**: Use external VCA to reduce wet level when input is loud
- **Rhythmic Delay**: Set TIME to match your tempo using external CV
- **Stereo Width**: Ping-pong mode creates wide stereo image
- **Modulation**: Small MOD amounts (0.05-0.15) add tape-like warmth

## Technical Specifications

- **Delay Modes**: Classic, Ping-pong, Analog, Reverse
- **Interpolation**: 3rd-order Lagrange
- **Max Feedback**: 95% (prevents infinite loops)
- **CV Input Range**: ±10V
- **Sample Rate**: Up to 96kHz (system dependent)
- **Transition Modes**: Fade, Hard

## Notes

- The module automatically handles DC offset in feedback path
- Mode switching uses smooth transitions when supported
- Long delay times at high sample rates may use more memory
