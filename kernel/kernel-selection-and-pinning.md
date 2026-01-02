# Kernel Selection and Pinning — Linux Mint 21.3 on iMac Late 2013 (Kepler NVIDIA)

This document defines the **required kernel policy** for running **Linux Mint 21.3**
on **iMac Late 2013 (A1419)** systems equipped with **NVIDIA Kepler GPUs**
(GT 755M / GTX 780M).

Kernel choice is **not optional** on this hardware.
Using the wrong kernel will break the NVIDIA 470 legacy driver and result in
black screens, failed boots, or broken graphics.

---

## Tested and Supported Kernel

### ✅ Supported kernel series

**This guide supports only:**
Linux kernel 5.15.x (LTS series)


- This is the Ubuntu 22.04 LTS kernel series used by Linux Mint 21.x.
- It is the safest, most stable series for **NVIDIA 470 + Kepler** on this iMac.

### Tested reference (example)
On our tested system:

```bash
uname -r

Output:
5.15.0-91-generic

Note: This guide does not require an exact patchlevel match (91 vs 101 vs 164).
It requires staying within the 5.15.x LTS series.

❌ Unsupported / Risky Kernels (Avoid)

Not supported for this setup:

6.x kernels (any 6.*)

Mainline kernels

Experimental kernel tools / manual kernel installs

Kernel series jumps that break NVIDIA 470 DKMS builds

These can:

break NVIDIA 470 DKMS compilation

cause black screens or boot failures

introduce modesetting conflicts

destabilize suspend/resume

Check Your Current Kernel

uname -r

List installed kernel packages:
apt list --installed | grep linux-image

Expected:
linux-image-5.15.*-generic

linux-image-generic tracking 5.15

Switching Back to 5.15 (If Needed)

If the system was upgraded to an unsupported kernel:

Open Update Manager

Menu → View → Linux Kernels

Select 5.15 (recommended)

Install the latest 5.15.x

Reboot and select a 5.15 kernel if prompted
Verify after boot:
uname -r

Prevent Accidental Kernel Series Upgrades
Method 1: Update Manager (Recommended)

Open Update Manager

View → Linux Kernels

Stay on 5.15 (recommended)

Do not install 6.x kernels

This is enough for most users.

Method 2: APT Hold (Advanced)

To reduce risk of accidental kernel track changes:
sudo apt-mark hold linux-image-generic linux-headers-generic

To undo:
sudo apt-mark unhold linux-image-generic linux-headers-generic

What NOT to Do

Do not:

install mainline kernels

jump to 6.x kernels “just because newer”

remove kernel headers required for NVIDIA DKMS

For Kepler GPUs, newer kernels are often worse.

Validation Checklist
uname -r
dpkg -l | grep linux-image
nvidia-smi

Expected:
kernel is 5.15.x

NVIDIA 470 loads successfully

Selección y Fijación del Kernel — Linux Mint 21.3 en iMac Late 2013 (NVIDIA Kepler)

Este documento define la política obligatoria de kernel para ejecutar Linux Mint 21.3
en iMac Late 2013 (A1419) con GPUs NVIDIA Kepler
(GT 755M / GTX 780M) usando el driver NVIDIA 470 (legacy).

La selección del kernel no es opcional en este hardware.
Un kernel incorrecto puede romper NVIDIA 470 y causar pantallas negras,
fallos de arranque o gráficos inestables.

✅ Serie de Kernel Soportada (Obligatorio)

Esta guía soporta únicamente:
Kernel Linux 5.15.x (serie LTS)

Es la serie de kernel LTS de Ubuntu 22.04 usada por Linux Mint 21.x.

Es la opción más estable para NVIDIA 470 + Kepler en este iMac.

Referencia probada (ejemplo)

En nuestro sistema probado:
uname -r

Salida:
5.15.0-91-generic

Nota: Esta guía no exige el mismo “número exacto” (91 vs 101 vs 164).
Exige permanecer dentro de la serie LTS 5.15.x.

❌ Kernels No Soportados / Riesgosos (Evitar)

No soportados:

Kernels 6.x (cualquier 6.*)

Kernels mainline

Herramientas experimentales / instalaciones manuales de kernel

Saltos de serie que rompen el build DKMS de NVIDIA 470

Estos pueden:

romper el DKMS de NVIDIA 470

provocar pantallas negras o fallos de arranque

generar conflictos de modos gráficos

empeorar suspensión/reanudación

Verificar el Kernel Actual
uname -r

Listar kernels instalados:
apt list --installed | grep linux-image

Esperado:

linux-image-5.15.*-generic

linux-image-generic siguiendo 5.15

Volver a 5.15 (Si es Necesario)

Si el sistema se actualizó a un kernel incompatible:

Abrir Administrador de Actualizaciones

Ver → Kernels de Linux

Seleccionar 5.15 (recomendado)

Instalar el último 5.15.x

Reiniciar y seleccionar 5.15 si se solicita

Verificar:
uname -r

Evitar Saltos Accidentales de Serie
Método 1: Administrador de Actualizaciones (Recomendado)

Abrir Administrador de Actualizaciones

Ver → Kernels de Linux

Permanecer en 5.15 (recomendado)

No instalar kernels 6.x

Método 2: Bloqueo con APT (Avanzado)
sudo apt-mark hold linux-image-generic linux-headers-generic

Para revertir:
sudo apt-mark unhold linux-image-generic linux-headers-generic

Qué NO Debes Hacer

No:

instalar kernels mainline

brincar a 6.x “porque es más nuevo”

eliminar headers necesarios para DKMS de NVIDIA

En GPUs Kepler, kernels nuevos suelen ser peores.

Checklist de Validación
uname -r
dpkg -l | grep linux-image
nvidia-smi

Esperado:
kernel 5.15.x

NVIDIA 470 cargado correctamente
