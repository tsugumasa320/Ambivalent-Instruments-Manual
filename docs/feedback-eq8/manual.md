# Feedback EQ8 - Global Feedback Equalizer

Stereo 8-band EQ with one global feedback loop.

## Overview

`Feedback EQ8` is a stereo 8-band parametric EQ with fixed frequency bands and one bipolar `Feedback Amount` control. Instead of simply making the whole signal louder or quieter, that control sends part of the EQ output back into the EQ input.

This means the EQ bands do two jobs at once: they shape the audible output, and they decide which frequency areas are emphasized inside the feedback loop. Gentle settings work like a resonant tone shaper. Stronger settings can move toward ringing, howl, and controlled self-oscillation.

The loop is stabilized internally with a soft limiter and a DC blocker. The limiter is only inside the feedback path, so the audible output keeps the EQ character rather than sounding hard-clipped by default.

## Parameters

**FEEDBACK AMOUNT** (`-95%` to `+95%`, default `0%`)
- Controls the amount and polarity of the global feedback loop.
- Positive values feed the EQ output back in phase; negative values feed it back with inverted polarity.
- **GUI Display**: The slider displays a bipolar percentage from `-95.0` to `+95.0`.
- **Examples**:
  - **Value = 0%**: Behaves like a fixed 8-band EQ without added feedback.
  - **Value = +35%**: Boosted bands start to ring and sustain more clearly.
  - **Value = +75%**: Strong resonance, easily moving toward self-oscillation depending on the EQ curve and source.
  - **Value = -50%**: Inverted feedback changes the tone and transient feel in a different, often hollower way than positive feedback.
- **Uses**: Start low for subtle resonance, then raise it until the bands you boosted begin to "talk back" to the source.
- **Details**: The internal loop is clamped to `±95%` and stabilized with an in-loop `tanh` limiter plus a DC blocker around `20Hz`.

**EQ BANDS** (`±12dB` each, default `0dB`)
- The 8 fixed bands are `60Hz`, `170Hz`, `310Hz`, `600Hz`, `1kHz`, `3kHz`, `6kHz`, and `12kHz`.
- `60Hz` is a low shelf, `12kHz` is a high shelf, and the middle bands shape the main resonant color.
- **GUI Display**: Each band slider shows gain in dB from `-12.00 dB` to `+12.00 dB`.
- **Examples**:
  - **Low band boost**: Raise `60Hz` to `+6dB` with moderate positive feedback for heavier low-end bloom and low resonance.
  - **Mid band boost**: Raise `1kHz` or `3kHz` to `+6dB` to `+10dB` for nasal, vocal, or metallic resonant emphasis.
  - **High band cut/boost**: Boost `6kHz` or `12kHz` for bright, unstable edge, or cut them to keep the feedback darker and smoother.
  - **Mixed curve**: Cut lows, boost mids, and slightly lift highs to make the loop focus on presence instead of rumble.
- **Uses**: Think of the EQ sliders as "feedback color selectors". The more you boost a band, the more that frequency region tends to dominate the loop.
- **Details**: The panel places the higher bands at the top and the lower bands near the bottom.

## I/O / CV

- **Audio In**: `L/R`. If the right input is unconnected, the left input is copied to the right side internally.
- **Audio Out**: `L/R`.
- **Polyphonic Audio**: Polyphonic audio inputs are processed per channel. The outputs follow the same active channel count instead of being summed to mono.
- **CV In**: None.

## LED Display

- **Band LEDs**: Each band LED shows output energy around its corresponding EQ band. They work as a quick visual hint for which spectral regions are currently active.
- **Feedback LED**: The white feedback LED shows overall output level, not the numeric feedback amount.

## Context Menu

- **Reset All**: Resets all 8 EQ bands and `Feedback Amount` to `0`.

## Usage Examples

- **Plain EQ mode**: Keep `Feedback Amount` at `0%` and use the module as a fixed 8-band EQ without added feedback.
- **Resonant tone shaping**: Set `Feedback Amount` around `+30%` to `+50%`, then boost one or two bands to make those areas ring more than the rest of the source.
- **Near self-oscillation**: Push `Feedback Amount` above `+70%` and boost a narrow tonal area in the mids or highs. Small slider changes can make a large audible difference here.
- **Negative feedback texture**: Move `Feedback Amount` below `0%` for a different phase interaction. This is useful when positive feedback becomes too obvious or boomy.
- **Color by band balance**: Boost `60Hz` for low bloom, `1kHz` to `3kHz` for vocal or metallic focus, and `6kHz` to `12kHz` for brighter unstable edge.

## Notes

- `Feedback EQ8` can self-oscillate. That is intentional. Start from lower feedback settings and raise the amount gradually.
- The limiter and DC blocker only stabilize the loop. They do not turn the module into a safety brick-wall limiter on the final output.
- Because there are no CV inputs, this module is best treated as a manual performance or sound-design processor rather than an automation-heavy EQ.
- If you want conventional overall level control after the feedback stage, patch an external VCA or output module after `Feedback EQ8`.
