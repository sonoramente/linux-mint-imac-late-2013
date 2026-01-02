# Linux Mint on iMac (27-inch, Late 2013 – NVIDIA Kepler)

This repository documents a **fully working, tested, and reproducible**
installation of **Linux Mint** on the **iMac Late 2013 (A1419)** equipped
with **NVIDIA Kepler GPUs**.

This guide exists because generic Linux tutorials consistently fail
on this hardware due to Apple firmware quirks, NVIDIA driver deprecations,
and Broadcom Wi-Fi constraints.

All procedures documented here were validated on real hardware after
weeks of testing, failure analysis, and correction.

---

## ✅ Tested Configurations

### iMac Late 2013 — i5-4570 / GeForce GT 755M
- NVIDIA Driver: **470.256.02**
- Wi-Fi: Broadcom BCM4360 (wl)
- Display: 2560×1440 @ 60Hz
- Audio: Internal speakers functional
- Camera: FaceTime HD functional

### iMac Late 2013 — i7-4771 / GeForce GTX 780M
- NVIDIA Driver: **470.256.02**
- Identical driver stack and fixes
- Higher GPU headroom, same stability

---

## ❗ Critical NVIDIA Note

Late-2013 iMacs use **Kepler-based NVIDIA GPUs**.

These GPUs are **NOT supported by modern NVIDIA drivers**.

The **470.xx legacy branch is mandatory**.
Any guide recommending newer drivers is incorrect for this hardware.


NVIDIA 470 + Kepler depends on the kernel

---

## 🔒 Kernel Requirement (Mandatory)

This hardware **requires the Linux 5.15.x LTS kernel series**.

Using newer kernels (6.x or mainline) can break the NVIDIA 470 legacy driver
and result in black screens or boot failures.

Before proceeding, **verify your kernel** and ensure it matches the supported
series.

➡️ **See:** [Kernel Selection and Pinning](kernel/kernel-selection-and-pinning.md)

---


---

## ✔ What Works

- NVIDIA proprietary driver (470.xx)
- Hardware-accelerated OpenGL
- Wi-Fi (Broadcom BCM4360)
- Ethernet (Gigabit)
- Internal speakers
- FaceTime HD camera
- HiDPI-tuned desktop (XFCE)
- Stable boot (nouveau fully disabled)
- External displays via Mini DisplayPort / Thunderbolt
  - Apple Thunderbolt Display (A1407)
  - DisplayPort-over-Thunderbolt works natively
Thunderbolt displays function as DisplayPort devices on this iMac and require
no additional drivers. Advanced Thunderbolt features (daisy-chaining,
networking, hot-plug reliability) are outside the scope of this guide.

---

## ❌ What This Guide Avoids

- nouveau driver instability
- broken or deprecated NVIDIA drivers
- partial Broadcom solutions
- undocumented kernel hacks
- vague “it should work” instructions

---

## 🖥️ Scope

This repository applies **only** to:
- iMac (27-inch, Late 2013)
- NVIDIA GT 755M
- NVIDIA GTX 780M

Other models may differ.

---

## ⚠️ Disclaimer

This guide assumes:
- Comfort with the Linux terminal
- UEFI boot awareness
- Willingness to modify system configuration

Proceed carefully and read each section fully.

---

---

# Linux Mint en iMac (27 pulgadas, Finales de 2013 – NVIDIA Kepler)

Este repositorio documenta una instalación **completamente funcional,
probada y reproducible** de **Linux Mint** en el **iMac Late 2013 (A1419)**
equipado con **GPUs NVIDIA Kepler**.

Esta guía existe porque los tutoriales genéricos de Linux **fallan
constantemente** en este hardware debido a particularidades del firmware
de Apple, la descontinuación de drivers NVIDIA y las limitaciones del
Wi-Fi Broadcom.

Todos los procedimientos aquí documentados fueron validados en hardware
real tras semanas de pruebas, errores y correcciones.

---

## ✅ Configuraciones Probadas

### iMac Late 2013 — i5-4570 / GeForce GT 755M
- Driver NVIDIA: **470.256.02**
- Wi-Fi: Broadcom BCM4360 (wl)
- Pantalla: 2560×1440 @ 60Hz
- Audio: Altavoces internos funcionales
- Cámara: FaceTime HD funcional

### iMac Late 2013 — i7-4771 / GeForce GTX 780M
- Driver NVIDIA: **470.256.02**
- Mismo stack de drivers y correcciones
- Mayor potencia gráfica, misma estabilidad

---

## ❗ Nota Crítica sobre NVIDIA

Los iMac Late-2013 utilizan **GPUs NVIDIA basadas en Kepler**.

Estas GPUs **NO son compatibles con drivers NVIDIA modernos**.

El uso del driver **470.xx es obligatorio**.
Cualquier guía que recomiende drivers más nuevos es incorrecta para
este hardware.


NVIDIA 470 + Kepler depende del kernel 

## 🔒 Requisito de Kernel (Obligatorio)

Este hardware **requiere la serie de kernel Linux 5.15.x (LTS)**.

El uso de kernels más nuevos (6.x o mainline) puede romper el driver legacy
NVIDIA 470 y provocar pantallas negras o fallos de arranque.

Antes de continuar, **verifica tu kernel** y asegúrate de que pertenece a la
serie soportada.

➡️ **Ver:** [Selección y Fijación del Kernel](kernel/kernel-selection-and-pinning.md)

---


---

## ✔ Lo que Funciona

- Driver propietario NVIDIA (470.xx)
- Aceleración OpenGL por hardware
- Wi-Fi (Broadcom BCM4360)
- Ethernet (Gigabit)
- Altavoces internos
- Cámara FaceTime HD
- Escritorio optimizado para HiDPI (XFCE)
- Arranque estable (nouveau deshabilitado)
- Pantallas externas vía Mini DisplayPort / Thunderbolt
  - Apple Thunderbolt Display (A1407)
  - DisplayPort sobre Thunderbolt funciona de forma nativa
Las pantallas Thunderbolt funcionan como dispositivos DisplayPort en este iMac
y no requieren drivers adicionales. Funciones avanzadas de Thunderbolt
(encadenamiento, red, hot-plug) quedan fuera del alcance de esta guía.

---

## ❌ Lo que esta Guía Evita

- Inestabilidad del driver nouveau
- Drivers NVIDIA rotos o descontinuados
- Soluciones incompletas para Broadcom
- Hacks de kernel sin documentación
- Instrucciones vagas del tipo “debería funcionar”

---

## 🖥️ Alcance

Este repositorio aplica **únicamente** a:
- iMac (27 pulgadas, Late 2013)
- NVIDIA GT 755M
- NVIDIA GTX 780M

Otros modelos pueden comportarse de forma diferente.

---

## ⚠️ Aviso

Esta guía asume:
- Comodidad usando la terminal
- Conocimiento básico de arranque UEFI
- Disposición a modificar la configuración del sistema

Proceda con cuidado y lea cada sección completamente.

