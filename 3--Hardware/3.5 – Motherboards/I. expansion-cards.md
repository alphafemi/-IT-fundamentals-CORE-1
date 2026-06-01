# CompTIA A+ 220-1201 — Expansion Cards

> **Exam Domain Reference** | Core 1 (220-1201) — Hardware (Domain 3)  
> Topics: Sound cards, video/GPU adapters, capture cards, NICs, driver installation best practices

---


---

## Overview

Expansion cards extend the functionality of a motherboard beyond what it provides by default. They connect via PCIe (or legacy PCI) slots and are designed to be user-installable — no factory service required.

**General installation process:**
1. Power off the system
2. Install the card into the appropriate slot
3. Power on — most modern OSes auto-detect the hardware
4. Install or update drivers
5. Verify operation via Device Manager

---

## Sound Cards

A dedicated sound card provides audio capabilities superior to the basic audio often built into a motherboard.

**What a sound card adds:**
- Higher quality audio output (better DAC, lower noise)
- Multi-channel output — connect home theater systems (multiple speakers, subwoofer)
- Audio input — multiple microphones, musical instruments, line-in sources
- Digital audio I/O (optical/coaxial S/PDIF)

**Common connectors on a sound card:**
- Left/right audio output
- Headphone output
- Line input
- Digital audio output

---

## Video Adapters (GPU)

**Integrated graphics:** Many CPUs include a built-in GPU. Video outputs (VGA, DVI, HDMI, DisplayPort) from integrated graphics connect directly to motherboard ports.

**Discrete GPU (graphics card):** A separate expansion card with its own dedicated GPU and VRAM, providing far more graphics processing power than integrated graphics.

**When to use a discrete GPU:**
- High-end gaming
- 3D rendering and animation
- Video editing
- AI/ML workloads
- Driving multiple high-resolution monitors

Discrete GPUs connect via a PCIe ×16 slot and often require supplemental power via PCIe 6-pin or 8-pin connectors from the power supply.

---

## Capture Cards

A capture card provides **video input** into the computer — the opposite of a video output card.

**Use cases:**
- Recording gameplay from a console
- Digitizing video from cameras or legacy equipment
- Ingesting video from multiple external sources

**Characteristics:**
- Handles large amounts of data — connects directly to the PCIe bus for high throughput
- Common input formats: **HDMI**, **SDI** (Serial Digital Interface — professional broadcast format)

---

## Network Interface Cards (NIC)

A NIC provides wired Ethernet connectivity. While most motherboards include a built-in NIC, a separate card may be needed when:

- The motherboard has no built-in Ethernet (thin/budget boards)
- The onboard NIC has failed
- Multiple Ethernet ports are required (servers, firewalls, security appliances)

**Multi-port NICs:** A single PCIe card with 4 (or more) Ethernet ports — useful for servers requiring multiple network connections.

---

## Driver Installation Best Practices

| Step | Action |
|---|---|
| 1. Check motherboard docs | Confirm available slot types and any compatibility requirements |
| 2. Check card manufacturer requirements | Minimum OS, hardware, and driver requirements |
| 3. Review knowledge base | Known issues, quirks, or pre-requisites |
| 4. Check driver install order | Some cards require drivers BEFORE hardware installation; others AFTER |
| 5. Install hardware | Seat card in correct slot; secure with screw |
| 6. Boot and verify auto-detection | Most modern OSes install basic drivers automatically |
| 7. Check manufacturer for latest driver | Website may have newer drivers than what Windows auto-installs |
| 8. Uninstall old driver if needed | Some updates require removing the previous version first |
| 9. Verify in Device Manager | Confirm the device is recognized and functioning without errors |

> **Exam Tip:** Driver install order matters — always check the card's documentation before installing. Installing in the wrong order can cause a non-functional device or system instability.

**Windows Device Manager:** Used to install, update, roll back, and verify the status of device drivers. If a card shows a yellow exclamation mark, the driver is missing or not functioning correctly.

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| Expansion cards | Add functionality not built into the motherboard; user-installable |
| Sound card | Better audio quality; multi-channel output; instrument/mic inputs |
| Integrated graphics | GPU built into CPU; connects to motherboard video ports |
| Discrete GPU | Separate PCIe card; dedicated VRAM; for gaming, video editing, rendering |
| Capture card | Video INPUT (not output); PCIe; HDMI and SDI are common inputs |
| NIC | Wired Ethernet; add when onboard is absent, failed, or more ports needed |
| Multi-port NIC | Multiple Ethernet connections on one PCIe card; used in servers |
| Driver install order | Some cards need drivers before hardware, some after — check documentation |
| Device Manager | Verify, install, update, or roll back drivers in Windows |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Hardware Domain**, covering expansion card types (sound, video/GPU, capture, NIC) and driver installation best practices.
