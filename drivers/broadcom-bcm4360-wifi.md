# Broadcom BCM4360 Wi-Fi (Late-2013 iMac) — Working Method on Linux Mint

Late-2013 iMacs commonly include **Broadcom BCM4360 802.11ac** Wi-Fi.
On Linux Mint, the reliable solution is the **Broadcom STA (“wl”)** driver:

- Package: `bcmwl-kernel-source`
- Kernel module: `wl`

Open-source Broadcom drivers (`b43`, `brcmsmac`) typically do **not** support BCM4360 correctly.

---

## Tested Hardware

Example detection (typical output):
```bash
lspci | grep -i network

