# Feedback EQ8 - Global Feedback Equalizer

Stereo 8-band parametric equalizer with one global feedback control for resonance and self-oscillation.

## Features

- 8 fixed EQ bands shared with EQ8 (`60Hz`, `170Hz`, `310Hz`, `600Hz`, `1kHz`, `3kHz`, `6kHz`, `12kHz`)
- One bipolar `Feedback Amount` control with `±95%` display range
- In-loop `tanh` limiter and DC blocker for stable feedback behavior
- Clean output path with feedback stabilization kept inside the loop
- Stereo audio I/O with left-to-right copy when the right input is unconnected
- Polyphonic audio processing per channel, with matching polyphonic outputs
- Band LEDs that show output energy around each EQ band

## Documentation

- [English Manual](manual.md) - Complete user guide in English
- [日本語マニュアル](manual_jp.md) - 日本語での詳細ガイド

## Quick Start

1. Add `Feedback EQ8` to your VCV Rack patch
2. Connect stereo audio input and output
3. Start with `Feedback Amount` at `0%` and shape the tone with the 8 EQ bands
4. Raise `Feedback Amount` gradually to introduce resonance and feedback color
5. Boost or cut different bands to decide which frequency areas feed back the most

For detailed instructions, see the full manual pages linked above.
