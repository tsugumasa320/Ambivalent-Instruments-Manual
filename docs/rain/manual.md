# Rain

A **4 HP** stereo **rain bed** generator: filtered noise with Clouds-style reverb and Mid/Side width. The panel artwork responds to your settings.

## Overview

Internally, `RainGenerator` shapes **uniform noise** with a **density** gain, runs it through a **0–1 DJ filter** (lowpass on the left half of the knob, highpass on the right half, neutral near the center), then through a **reverb** wet/dry control. `RainModule` applies **Mid/Side width** so you can narrow or exaggerate the stereo image before the outputs.

!!! note
    This DSP is **not** a bit-for-bit clone of any specific Max for Live `Rain.amxd`; treat it as its own rain-flavored texture engine.

## Parameters

**Density** (`0 .. 1`, default `0.5`)

- Scales the continuous noise bed (“how thick the rain feels”).

**Filter Cutoff** (`0 .. 1`, default `0.5`)

- DJ-style tone control: lowpass sweep toward the left from center, highpass sweep toward the right.

**Reverb** (`0 .. 1`, default `0.2`)

- Wet/dry for the built-in Clouds-style reverb.

**Stereo Width** (`0 .. 2`, default `1`)

- Mid/Side width applied after the generator: `0` collapses to mono, `1` leaves the natural stereo image, `2` exaggerates the side channel.

## CV inputs

When a CV jack is patched, its voltage **adds** to the knob (then clamps):

- **Density CV**, **Filter CV**, **Reverb CV**: `effective = clamp(knob + CV / 10, 0, 1)` (±10 V spans the full 0–1 range).
- **Width CV**: `effective = clamp(knob + CV * 0.2, 0, 2)` (5 V of CV moves the width by 1.0 unit).

Polyphonic CV uses the **first channel** only.

## Outputs

- **Audio L / Audio R**: stereo pair, scaled toward Rack’s ±5 V audio range (`× 5` after Mid/Side), each port `setChannels(1)`.

## Tips

- Keep **Density** moderate and push **Reverb** for distant-storm beds.
- Sweep **Filter Cutoff** slowly while modulating **Density** for evolving textures.
- Use **Width** near `0` to fold Rain into a mono send, or above `1` for extra-wide headphones moments.

## Context menu

- No additional entries in the current build.
