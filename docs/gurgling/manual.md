# Gurgling

A **4 HP** stereo texture source that sits between filtered noise and bubbling water. Three percentage knobs sculpt the exciter, a **Freq** control sets the filter modulation rate, and **Stereo Width** follows the same Mid/Side law as **Rain**.

## Overview

`BubbleGenerator` produces a mono sample. A very short delay line offsets left/right slightly before Mid/Side width is applied, so width changes remain meaningful even though the source is strongly correlated.

## Parameters

**Density** (`0 .. 100 %`, default `30 %`)

- How quickly the bubble / S&H exciter evolves.

**Clarity** (`0 .. 100 %`, default `100 %`)

- How strong the clarity / brightness layer feels on the bubble exciter: higher values push brighter, more “lit up” motion; lower values keep the bed softer and more muffled.

**Freq** (`0 .. 100 %`, default `10 %`)

- Scales the filter-related S&H rate (higher → faster modulations).

**Stereo Width** (`0 .. 2`, default `1`)

- Same Mid/Side width as Rain: `0` mono, `1` natural, `2` exaggerated side.

## CV inputs

Percentage knobs (`Density`, `Clarity`, `Freq`):

- `effective = clamp(knob_percent + CV_volts * 10, 0, 100)` — each **1 V** moves the readout by **10 percentage points**.

**Width CV**:

- `effective = clamp(knob_width + CV_volts * 0.2, 0, 2)` — identical law to Rain’s width CV.

Polyphonic CV uses the **first channel** only.

## Outputs

- **Left audio / Right audio**: stereo pair at ±5 V scale (`kOutputFullScaleV = 5`), each port `setChannels(1)`.

## Tips

- Sweep **Clarity** while holding **Density** low for subtle water-on-glass textures.
- Push **Freq** for more chatter in the filter path; back off if the highpass gets too nervous.
- Use **Width** near `0` to keep Gurgling centered in a mono FX send.

## Context menu

- No additional entries in the current build.
