# Delay Expander - Tap Tempo & Sync for Delay

Tap tempo, sync, and clock expansion for the Delay module.

## Overview

Delay Expander adds tap tempo, tempo sync, and clock I/O to the Delay module. Place Delay Expander directly to the right of the Delay module — it communicates via VCV Rack's expander mechanism and has no standalone audio processing.

## Setup

**Place Delay Expander to the right of Delay** — the expander must be immediately adjacent (no gap) to the right side of a Delay module. When properly connected, the Sync Mode LED will respond to the sync state.

## Controls

**Tap** (button)
- Tap repeatedly to set BPM from the interval between taps
- The detected tempo is sent to the Delay module

**Sync On** (button)
- Toggles tempo sync mode
- When enabled, delay time quantizes to note divisions based on the detected tempo
- **LED**: Sync Mode LED indicates whether sync is active

**Reset** (button)
- Resets tap tempo and sync phase
- Use to re-sync with an external clock

## I/O

- **Sync In**: External clock input — BPM is calculated from pulse interval
- **Reset In**: Reset trigger input — same function as the Reset button
- **Clock Out**: Outputs a pulse at the current delay time interval

## Context Menu

- No additional items
