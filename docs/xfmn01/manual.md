# XFMN-01 - Cross-FM Noise Synthesizer

**Note: This manual is AI-generated and will be updated progressively.**

Cross-FM noise synthesizer with advanced modulation capabilities for VCV Rack

## Overview

XFMN-01 is an experimental synthesizer module that combines Cross-FM (frequency modulation) with chaotic noise generation. Through oscillator cross-modulation, organic noise algorithms, and non-linear distortion processing, it creates unique sonic textures that transcend traditional FM synthesis boundaries.

### Key Features

- **Dual FM Operators**: Two independently controllable FM operators
- **3 FM Modes**: Chaos, Wide, Pure different FM characteristics
- **Delay Effects**: High-quality delay processing
- **3-Mode Filter**: LP/BP/HP filtering
- **Octave Mode**: Sub Oct/Bypass/Upper Oct 3-stage range
- **Comprehensive CV Control**: Full CV control over all parameters

## Signal Flow

```
[OP1] ──┬── [FM ENGINE] ──┬── [DELAY] ── [FILTER] ── [OUTPUT GAIN] ── [OUTPUT L/R]
        │                │
[OP2] ──┴────────────────┘
        │
   [FM MODE]
```