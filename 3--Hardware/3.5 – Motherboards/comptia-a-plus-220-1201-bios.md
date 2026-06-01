# CompTIA A+ 220-1201 — BIOS & UEFI

> **Exam Domain Reference** | Core 1 (220-1201) — Hardware (Domain 3)  
> Topics: BIOS, POST, legacy BIOS, UEFI, flash memory, bootloader

---

## Table of Contents

1. [What Is the BIOS?](#what-is-the-bios)
2. [POST — Power-On Self-Test](#post--power-on-self-test)
3. [Where BIOS Is Stored](#where-bios-is-stored)
4. [Legacy BIOS](#legacy-bios)
5. [UEFI — Unified Extensible Firmware Interface](#uefi--unified-extensible-firmware-interface)
6. [Legacy BIOS vs. UEFI Comparison](#legacy-bios-vs-uefi-comparison)
7. [Key Takeaways](#key-takeaways)

---

## What Is the BIOS?

**BIOS (Basic Input/Output System)** is the firmware that initializes the hardware and prepares the system to load the operating system every time the computer is powered on.

**Other names for BIOS:**
- Firmware
- System BIOS
- ROM BIOS (historical — originally stored in Read-Only Memory; now stored in flash memory)

The BIOS runs before the operating system loads. What you see on screen during those first few seconds after pressing the power button is the BIOS, not the OS.

---

## POST — Power-On Self-Test

When the computer powers on, the BIOS immediately runs the **POST (Power-On Self-Test)** — a hardware diagnostic that verifies core components are present and functioning.

**What POST checks:**
- CPU present and functioning
- RAM installed
- Keyboard connected
- Mouse connected
- Other essential hardware

**POST outcomes:**
- **Pass** → system proceeds to load the operating system (via the bootloader)
- **Fail** → error message displayed on screen (or a series of beep codes if the display isn't working)

**Bootloader:** Once POST completes successfully, the bootloader takes over. It may load the OS automatically or prompt the user to choose an operating system.

> **Exam Tip:** POST is the first thing that runs after power-on. If a system fails to boot, POST is the starting point for hardware diagnostics.

---

## Where BIOS Is Stored

Modern BIOS/UEFI firmware is stored in **flash memory** on the motherboard — not traditional ROM.

- Flash memory allows the BIOS to be **updated (flashed)** without replacing hardware
- Some motherboards include **two flash chips** — a main BIOS and a backup — providing recovery if a BIOS update fails

> **Best practice before flashing BIOS:** Always back up the current configuration. A failed BIOS update can render a system unbootable; a backup chip or recovery image is essential.

---

## Legacy BIOS

The traditional BIOS that predates UEFI — has been in use for **over 25 years**.

**Characteristics:**
- Text-based interface — keyboard navigation only (arrow keys, Enter, function keys)
- Designed for older hardware
- Limited support for modern hardware features
- No mouse support
- Partition table limitations (cannot support large drives beyond ~2 TB without workarounds)

Legacy BIOS is still found on older systems and some embedded hardware.

---

## UEFI — Unified Extensible Firmware Interface

UEFI is the modern replacement for legacy BIOS, created by **Intel** and now the standard on all modern computers.

**Characteristics:**
- **Graphical interface** — mouse and keyboard supported
- **Standardized** — same features and options across manufacturers
- Supports larger drives (no 2 TB partition limit)
- Faster boot times
- Supports **Secure Boot** (prevents unauthorized code from loading at startup)
- Supports virtualization configuration, advanced CPU features, power management, security settings

**Common UEFI settings categories:**
- CPU overview and virtualization options
- Connected storage, audio, and network devices
- Advanced CPU features
- Power management
- Security (Secure Boot, passwords)
- Startup/boot order

> **Caution:** UEFI settings directly control hardware behavior. Changing settings without understanding the consequences can cause system instability or prevent the OS from booting.

---

## Legacy BIOS vs. UEFI Comparison

| Feature | Legacy BIOS | UEFI |
|---|---|---|
| Interface | Text-based | Graphical (GUI) |
| Input | Keyboard only | Mouse and keyboard |
| Age | 25+ years | Modern standard |
| Standardization | Varies by manufacturer | Standardized across manufacturers |
| Large drive support | Limited (~2 TB) | Full support |
| Secure Boot | No | Yes |
| Boot speed | Slower | Faster |
| Storage | ROM / flash | Flash memory |
| Created by | Various | Intel |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| BIOS | Firmware that initializes hardware before the OS loads |
| Also called | System BIOS, ROM BIOS, firmware |
| POST | Power-On Self-Test; checks CPU, RAM, keyboard, mouse; runs at every power-on |
| Bootloader | Loads after POST; starts the OS |
| BIOS storage | Flash memory on the motherboard (not ROM) |
| Dual BIOS chips | Main + backup; protects against failed updates |
| Legacy BIOS | Text-based; keyboard only; 25+ years old; limited hardware support |
| UEFI | Modern; graphical; mouse support; standardized; Secure Boot; created by Intel |
| UEFI caution | Changing settings can cause instability — always document and back up first |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Hardware Domain**, covering BIOS/UEFI firmware, POST, bootloader, legacy vs. UEFI differences, and flash storage of firmware.
