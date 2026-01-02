# NVIDIA Kepler (GT 755M / GTX 780M) — Correct Driver on Linux Mint (470.xx)

This document covers the **Late-2013 iMac (A1419)** models equipped with **NVIDIA Kepler GPUs**:

- **NVIDIA GeForce GT 755M (GK107M)**
- **NVIDIA GeForce GTX 780M (Kepler)**

These GPUs require the **NVIDIA 470.xx legacy driver**. Newer NVIDIA driver branches do not support Kepler and will fail.

---

## Tested Systems

### System A (Example: “Natali” iMac)
- iMac (27-inch, Late 2013)
- CPU: Intel Core i5-4570
- GPU: NVIDIA GeForce GT 755M (GK107M, Kepler)
- Display: 2560×1440 @ 60Hz

### System B (Example: “Regina” iMac)
- iMac (27-inch, Late 2013)
- CPU: Intel Core i7-4771
- GPU: NVIDIA GeForce GTX 780M (Kepler)
- Display: 2560×1440 @ 60Hz

---

## Why 470.xx is Mandatory

Kepler GPUs are not supported by modern NVIDIA driver branches. On these iMacs:

- **nouveau** (open-source driver) can boot but often causes instability, tearing, poor performance, or black screens.
- **nvidia-driver-470** (legacy) provides correct acceleration and stability for Kepler.

---

## Quick Success Criteria (Verify Everything)

After setup, these must be true:

```bash
nvidia-smi
inxi -Gx
lsmod | grep nouveau
