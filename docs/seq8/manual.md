# Seq8 - 8-Step CV/Gate Sequencer

Simple 8-step sequencer with internal clock and external sync support.

## Overview

Seq8 cycles through 8 steps, outputting a CV voltage and gate pulse for each step. It can run from its internal tempo (40–200 BPM) or lock to an external clock with a selectable multiplier. A reset input returns the sequence to step 1, and RESET takes priority when RESET and clock arrive on the same sample.

## Parameters

**STEP 1–8** (0.0–1.0, default 0.0)

- CV value for each step (output range: 0–10V)
- **Examples**:
  - **Value = 0.0**: 0V output
  - **Value = 0.5**: 5V output
  - **Value = 1.0**: 10V output

**TEMPO** (default 0.5)

- Without external clock: sets internal tempo from 40–200 BPM
- With external clock: selects sync multiplier
  - 0.25x / 0.5x / 1x / 2x / 4x
- **LED**: Tempo LED pulses at the active rate; brightness increases with tempo
- **Examples**:
  - **No clock, Tempo = 0.0**: 40 BPM
  - **No clock, Tempo = 0.5**: 120 BPM
  - **No clock, Tempo = 1.0**: 200 BPM
  - **Clock connected, Tempo = 0.0**: 0.25x (one step every 4 clocks)
  - **Clock connected, Tempo = 0.5**: 1x (one step per clock)
  - **Clock connected, Tempo = 1.0**: 4x (four steps per clock)

## I/O / CV

- **Audio In**: None
- **Audio Out**: None
- **Clock In**: External clock input (triggers step advance)
- **Reset In**: Reset trigger (returns to step 1)
- **CV Out**: Step CV (0–10V, mono), available at the left output jack
- **Gate Out**: Gate pulse per step (10V, mono), available at the right output jack

## Behavior Notes

- When an external clock is connected, the Tempo knob switches to sync multiplier mode: 0.25x / 0.5x / 1x / 2x / 4x
- RESET takes priority: if RESET and Clock triggers arrive on the same sample, the clock event is ignored and the sequence resets to step 1
- Changing the sync multiplier resets the internal phase counter to prevent drift
- Gate pulse duration is 1ms

## Context Menu

- No additional items
