# Crackl

Inspired by *Velvet Sunset* by manual: a compact **mono** texture generator with three parallel “crackle” voices, shared shaping, and a single output.

## Overview

Each voice routes a **morphing oscillator** through **sample-and-hold noise modulation**, then into a shared **tanh-style drive**. A **modulo** stage wraps the mix before **sample-rate / resolution-style degradation** and a master **Out** gain.

Use Crackl as a bed behind chords, as a percussive digital grit layer, or as a standalone noise instrument.

## Panel layout (16 HP)

- **Top row**: **Drive**, **Sample rate**, **Modulo**, and **Out** (master gain), each with a matching CV jack directly below.
- **Middle**: per-voice **Harmonics** and **Noise Mod** knobs with CV.
- **Lower**: vertical **Freq** sliders for voices A/B/C, **Gain** trims, and **Freq** / **Gain** CV columns.

## Parameters

**Freq 1 / 2 / 3** (`0 .. 1`, default `0.5`)

- Vertical sliders controlling each voice’s pitch mapping (normalized; mapped to high audio rates in DSP).

**Noise Mod A / B / C** (`0 .. 1`, default `0.1`)

- Depth of the per-voice sample-and-hold noise modulator.

**Harmonics A / B / C** (`0 .. 1`, default `0`)

- Morph amount from sine toward brighter/harder shapes (per voice).

**Drive** (`0 .. 1`, default `0`)

- Shared saturation before modulo and degradation.

**Modulo** (`0 .. 1`, default `0`)

- Positive fractional wrap amount applied after the mix.

**Sample rate** (`0 .. 1`, default `1`)

- Internal resample / hold ratio passed to the degrader. The knob is wired so that **fully left = 1** and **turning clockwise moves toward 0** (saved patch values match that orientation).

**Out** (`0 .. 2`, default `1`)

- Master output level after DSP.

**Gain A / B / C** (`0 .. 1`, default `0.5`)

- Per-voice level into the mix.

## I/O and CV

- **Harmonics A/B/C CV**, **Noise Mod A/B/C CV**: when connected, the effective value is `clamp01(knob + CV * 0.2)` (approximately ±5 V sweeps the 0–1 range with headroom).
- **Drive CV**, **Sample rate CV**, **Modulo CV**, **Freq A/B/C CV**, **Gain A/B/C CV**: same `knob + CV * 0.2` rule with 0–1 clamping where applicable.
- **Out**: mono audio output (`setChannels(1)`).

Polyphonic CV cables use the **first channel** (`getVoltage()`), consistent with other Ambivalent Instruments modules.

## Tips

- Start with **Noise Mod** low and **Harmonics** at zero for smoother tones; push both for digital grit.
- **Modulo** at zero disables the wrap; small values add subtle folding, larger values break the waveform into rhythmic patterns.
- Automate **Sample rate** slowly for lo-fi sweeps; pair with **Drive** for more apparent energy.

## Context menu

- No extra menu items in the current build.
