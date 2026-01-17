# Delay - Stereo Delay Module

Professional stereo delay engine with multiple delay modes including Repitch, Fade, Reverse, and Ping-pong. Features 3rd-order Lagrange interpolation for high-quality audio processing, inspired by Ableton Live.

## Overview

Delay is a professional-grade stereo delay effect module offering four distinct delay modes with high-quality audio processing. It features adjustable delay time (0.010s to 5.000s), feedback, tone filter, modulation depth, and dry/wet mixing. The module also offers transition modes accessible via right-click context menu, making it suitable for various musical applications from subtle ambience to dramatic sound design.

## Quick Start

1. Connect audio source to AUDIO L/R INPUT
2. Connect output to AUDIO L/R OUTPUT
3. Select delay mode using MODE button (4 modes available)
4. Adjust TIME knob to set delay time (0.010s to 5.000s)
5. Use FEEDBACK knob to control repetition
6. Use WET knob to balance between dry and delayed signal

## Parameters

### Main Controls

**TIME** (0.0〜1.0, default 0.5)
- Delay time control (displayed in seconds: 0.010s to 5.000s)
- Exponential curve for musical response
- CV input supported
- Range: 10ms to 5 seconds

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
  1. **Repitch**: Delay time changes affect pitch (hardware-like behavior)
  2. **Fade**: Crossfade between old/new delay times (Ableton Live style)
  3. **Reverse**: Reversed playback of delay buffer
  4. **Ping-pong**: Delay bounces between left and right channels

Mode lights indicate current mode:
- **Repitch Light**: Repitch mode active
- **Fade Light**: Fade mode active
- **Reverse Light**: Reverse mode active
- **Ping-pong Light**: Ping-pong mode active

## Transition Modes (Right-Click Context Menu)

Right-click on the module to access Transition Mode options. These control how the delay time changes when the TIME knob or CV is adjusted:

### Repitch Transition
- Delay time changes cause pitch shifts
- Hardware-like behavior
- Creates dramatic tape-stop effects
- Similar to vintage tape delays

### Fade Transition (Default)
- Smooth crossfade between old and new delay times
- No pitch changes
- Clean, professional sound
- Inspired by Ableton Live

### Jump Transition
- Immediate jump to new delay time
- Can create glitchy/artifacts effects
- Useful for experimental sounds
- May produce clicks at transitions

## Signal Processing Flow

1. Input signal (L/R) enters delay buffer
2. Delay time controls read position from buffer
3. Transition mode determines how time changes are handled
4. Tone filter applied to feedback path
5. Modulation adds subtle pitch variation (if MOD > 0)
6. Feedback sends delayed signal back to input
7. Dry/Wet crossfade for output mixing
8. Output signal (L/R) with delayed content

## Delay Modes

### Repitch Mode
- Delay time changes affect pitch
- Hardware-like behavior similar to vintage tape delays
- Creates pitch bend effects when TIME knob is modulated
- Clean, transparent sound at constant delay times

### Fade Mode
- Standard stereo delay with smooth transitions
- Ableton Live inspired behavior
- Crossfade between old/new delay times
- No pitch changes when time is adjusted
- Suitable for traditional delay effects

### Reverse Mode
- Reversed playback of delay buffer
- Creates unique, backwards echo effects
- Ideal for ambient and experimental sounds
- Can create psychedelic textures

### Ping-Pong Mode
- Delay alternates between left and right channels
- Creates rhythmic, bouncing echo patterns
- Excellent for stereo separation
- Wide stereo imaging

## CV Inputs

All CV inputs accept ±10V signals:
- **TIME CV**: Modulates delay time
- **TONE CV**: Modulates tone filter
- **FEEDBACK CV**: Modulates feedback amount
- **WET CV**: Modulates dry/wet mix

## Usage Examples

### Basic Delay Effect
1. Set MODE to Fade
2. Adjust TIME to desired delay (around 0.500s for medium echo)
3. Set FEEDBACK to 0.3-0.5 for moderate repeats
4. Adjust WET to blend delayed signal

### Hardware-Like Repitch
1. Set MODE to Repitch
2. Select "Repitch" transition mode from context menu
3. Adjust TIME to desired delay
4. Use TIME CV to modulate delay time for pitch bend effects
5. Set FEEDBACK to 0.4-0.6
6. Use WET at 0.5-0.7

### Ping-Pong Echo
1. Set MODE to Ping-pong
2. Adjust TIME for rhythmic echo (around 0.500s)
3. Set FEEDBACK to 0.4-0.6
4. Use WET at 0.5-0.7 for prominent stereo effect

### Ambient Wash
1. Set MODE to Fade
2. Use longer TIME (1.000s to 5.000s)
3. High FEEDBACK (0.7-0.8)
4. Lower WET (0.2-0.4) for subtle ambience
5. Add slight MOD (0.1-0.2) for warmth

### Reverse Reverb
1. Set MODE to Reverse
2. Medium TIME (0.250s to 0.750s)
3. Moderate FEEDBACK (0.3-0.5)
4. Low WET (0.1-0.3) for atmospheric effect

### Glitchy Jump
1. Set MODE to Fade
2. Select "Jump" transition mode from context menu
3. Use TIME CV for rapid time changes
4. Medium FEEDBACK (0.4-0.6)
5. Creates glitchy, artifact-filled sounds

## Tips and Tricks

- **Self-Oscillation**: Set FEEDBACK to 0.8-0.9 and TIME to create rhythmic patterns
- **Ducking**: Use external VCA to reduce wet level when input is loud
- **Rhythmic Delay**: Set TIME to match your tempo using external CV
- **Stereo Width**: Ping-pong mode creates wide stereo image
- **Modulation**: Small MOD amounts (0.05-0.15) add tape-like warmth
- **Repitch Effects**: Use TIME CV for dramatic pitch bend effects in Repitch mode
- **Smooth Transitions**: Fade transition mode is best for clean, professional results
- **Hardware Character**: Repitch transition mode creates vintage tape delay character
- **Jump Glitches**: Jump transition mode can create interesting artifacts and glitches

## Time Display

The TIME knob displays delay time in seconds (0.010s to 5.000s). This makes it easy to:
- Set precise delay times
- Calculate musical divisions (e.g., 0.500s = 1/8 note at 120 BPM)
- Synchronize with other modules

## Technical Specifications

- **Delay Modes**: Repitch, Fade, Reverse, Ping-pong
- **Transition Modes**: Repitch, Fade, Jump (via context menu)
- **Interpolation**: 3rd-order Lagrange
- **Max Feedback**: 95% (prevents infinite loops)
- **CV Input Range**: ±10V
- **Delay Time Range**: 0.010s to 5.000s
- **Sample Rate**: Up to 96kHz (system dependent)
- **Default Transition**: Fade

## Notes

- The module automatically handles DC offset in feedback path
- Mode switching uses smooth transitions
- Right-click context menu provides transition mode selection
- Long delay times at high sample rates may use more memory
- Time display shows actual delay time in seconds
- Sync/Clock/Tap functionality has been removed
