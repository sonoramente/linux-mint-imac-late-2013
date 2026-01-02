# Audio on iMac (27-inch, Late 2013) — Internal Speakers on Linux Mint

This document explains the **audio behavior on the iMac Late 2013 (A1419)** when running Linux Mint.

Unlike GPU or Wi-Fi, **audio does not require special drivers or patches** on this model.
The Intel HDA audio controller used by Apple is fully supported by the Linux kernel.

The only required steps are **verification and correct output selection**.

---

## Hardware Overview

- Audio controller: Intel HDA (Apple implementation)
- Outputs:
  - Internal stereo speakers
  - Headphone jack (analog)
  - Optical digital output (combined jack)
- Input:
  - Internal microphone

Linux Mint uses:
- ALSA (kernel level)
- PulseAudio (user level)

No Apple-specific modules are required.

---

## Verify Audio Output Detection

Check available audio sinks:

```bash
pactl list short sinks
