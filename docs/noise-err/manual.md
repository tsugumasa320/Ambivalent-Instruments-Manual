# NØ!SE//ERR - Dual-Output Noise Oscillator

Dual-output oscillator for moving seamlessly between stillness and motion, harmony and dissonance.

## Overview

`NØ!SE//ERR` generates two related signals at the same time and sends them to `OUT 1` and `OUT 2`. A top-panel bank switch selects which pair is active:

- `SIN / SAW`
- `RECT / RAND`

Both outputs pass through the same internal chain:

`OSC -> Filter -> Wavefold -> Drive -> Volume`

This makes the module useful both as a pitched oscillator and as a texture source for unstable, noise-forward timbres.

## Parameters

**Wave Bank** (`SIN / SAW` or `RECT / RAND`)
- Selects the active output pair
- `OUT 1` carries the first waveform in the selected bank
- `OUT 2` carries the second waveform in the selected bank

**FREQ** (`20 Hz - 2000 Hz`, default `261.625565 Hz`)
- Base oscillator frequency in Hertz
- The knob uses equal-octave (logarithmic) mapping: the display stays in Hz, but rotation changes pitch evenly across the range
- `V/Oct` applies standard 1V/oct modulation (`× 2^V`) around the knob frequency; `0V` keeps the knob pitch
- `Freq CV Trim` defaults to `1`, so you can plug a sequencer and play immediately; lower it to `0` to ignore pitch CV

**Filter Cutoff** (`20 Hz - 20000 Hz`, default `440 Hz`)
- Center frequency of the internal band-pass filter

**Filter Q** (`0.5 - 12.0`, default `1.0`)
- Resonance amount of the band-pass filter

**Filter Gain** (`0 - 10000`, default `1`)
- Pre-wavefold gain after filtering
- Uses a logarithmic taper with a steeper low-gain knob curve (power exponent 0.5) so low gains do not occupy too much of the rotation

**Wavefold** (`0 - 1`, default `0`)
- Controls the amount of wavefolding after the filter gain stage

**Drive** (`0 - 1`, default `0`)
- Adds post-wavefold saturation

**Volume** (`0 - 2`, default `1`)
- Final output level before the output jacks

## I/O / CV

- **V/Oct**: Pitch CV input
- **Freq CV Trim**: Bipolar trim (`-1 .. 1`) for `V/Oct`; default `1`
- **Filter Cutoff CV**: Cutoff modulation input
- **Filter Cutoff CV Trim**: Bipolar trim (`-1 .. 1`)
- **Q CV**: Direct resonance modulation input
- **Filter Gain CV**: Gain modulation input
- **Filter Gain CV Trim**: Bipolar trim (`-1 .. 1`)
- **Wavefold CV**: Wavefold modulation input
- **Wavefold CV Trim**: Bipolar trim (`-1 .. 1`)
- **Drive CV**: Direct drive modulation input
- **Volume CV**: Output level modulation input
- **Volume CV Trim**: Bipolar trim (`-1 .. 1`)
- **OUT 1**: First waveform of the selected bank
- **OUT 2**: Second waveform of the selected bank

## Signal Notes

- In `SIN / SAW` mode, the module behaves like a paired tonal oscillator with smooth and bright outputs.
- In `RECT / RAND` mode, `OUT 1` becomes a hard-edged rectangular source, while `OUT 2` becomes a rate-following random waveform.
- `RAND` is not white noise. It updates target values at oscillator rate and interpolates linearly between them.

## LEDs

- **Freq LED**: Monitors oscillator frequency on a logarithmic scale
- **Output LED**: Monitors the larger level of `OUT 1` and `OUT 2`

## Context Menu

- No additional items
