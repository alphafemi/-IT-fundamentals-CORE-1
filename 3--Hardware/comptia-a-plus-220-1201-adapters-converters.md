# CompTIA A+ 220-1201 — Adapters & Converters

> **Exam Domain Reference** | Core 1 (220-1201) — Hardware (Domain 3)  
> Topics: DVI-to-HDMI, DVI-A to VGA, VGA-to-DVI conversion, USB-to-Ethernet, USB-C to USB-A, USB hubs

---

## Table of Contents

1. [Overview](#overview)
2. [Video Adapters & Converters](#video-adapters--converters)
   - [DVI-D to HDMI](#dvi-d-to-hdmi)
   - [DVI-A to VGA](#dvi-a-to-vga)
   - [VGA to Digital DVI](#vga-to-digital-dvi)
3. [USB Adapters & Hubs](#usb-adapters--hubs)
   - [USB to Ethernet](#usb-to-ethernet)
   - [USB-C to USB-A](#usb-c-to-usb-a)
   - [USB Hubs](#usb-hubs)
4. [Adapter vs. Converter — Key Distinction](#adapter-vs-converter--key-distinction)
5. [Key Takeaways](#key-takeaways)

---

## Overview

Not every cable or port combination is available off the shelf. Adapters and converters bridge the gap between different interface standards. Understanding which combinations are electrically compatible (adapter only) vs. which require signal conversion is essential for both the exam and real-world troubleshooting.

**General rule:**
- **Electrically compatible** → simple adapter or passive cable with two connector types
- **Different signal formats** → active converter required (may need power; performs signal processing)

Most adapters are designed for **temporary** use but often become permanent solutions.

---

## Video Adapters & Converters

### DVI-D to HDMI

**DVI-D** (digital DVI) and **HDMI** are **electrically compatible** — both carry the same digital video signal.

- A simple **passive cable** or **adapter** with DVI-D on one end and HDMI on the other is all that is needed
- No signal conversion occurs — the digital signal passes through unchanged
- Common use: connecting an older monitor with a DVI input to a newer GPU with HDMI output (or vice versa)

> **No active converter needed** — this is a plug-and-play connection.

### DVI-A to VGA

**DVI-A** (analog DVI) and **VGA** are also electrically compatible — both carry analog video signals.

- A simple **passive adapter** converts the physical connector shape (VGA 15-pin ↔ DVI analog)
- Officially supports up to **640×480 resolution**, though higher resolutions often work in practice
- Common use: connecting legacy VGA monitors to DVI-A outputs

> **No active converter needed** — analog-to-analog, passive adapter only.

### VGA to Digital DVI

**VGA** (analog) and **DVI-D** (digital) are **not** electrically compatible — they carry fundamentally different signal types.

- An **active converter** is required to convert analog VGA → digital DVI
- The converter performs actual signal processing and typically requires power
- Less common today but useful when legacy VGA sources must connect to digital-only displays

> **Active converter required** — signal must be processed, not just re-pinned.

---

## USB Adapters & Hubs

### USB to Ethernet

Thin and ultrabook laptops often omit a full-size RJ45 Ethernet port to save space. A USB-to-Ethernet adapter restores wired connectivity.

**Why you'd need one:**
- Wired connectivity in environments with poor or no Wi-Fi
- Directly connecting to a device for configuration or troubleshooting
- Network testing that requires a physical cable

The adapter converts USB data traffic to Ethernet — an **active converter** with a USB controller chip inside.

### USB-C to USB-A

Many modern laptops only have USB-C ports, eliminating full-size USB-A ports. A USB-C to USB-A adapter or cable allows legacy USB-A peripherals to connect.

**Two common forms:**
- **Short adapter** — plugs directly into the USB-C port; provides a USB-A socket
- **Cable** — longer; moves the USB-A socket away from the laptop body for easier access

### USB Hubs

A USB hub plugs into a single USB port and expands it into multiple output connections of various types.

**Common ports found on a multi-function USB hub:**
- USB-A (multiple)
- USB-C
- SD / microSD card reader
- HDMI video output
- Ethernet (RJ45)
- Audio jack

A hub is the all-in-one solution when you need multiple adapter types and don't know in advance exactly what you'll need.

---

## Adapter vs. Converter — Key Distinction

| Type | Signal Processing | Power Required | Examples |
|---|---|---|---|
| **Passive adapter / cable** | None — electrically compatible | No | DVI-D ↔ HDMI, DVI-A ↔ VGA |
| **Active converter** | Yes — signal is transformed | Sometimes | VGA → DVI-D, USB → Ethernet |

> **Exam Tip:** If two standards share the same signal type (both digital, or both analog), a passive adapter is usually sufficient. If the signal type changes (analog ↔ digital), an active converter is required.

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| DVI-D ↔ HDMI | Both digital; electrically compatible; passive adapter/cable only |
| DVI-A ↔ VGA | Both analog; electrically compatible; passive adapter only; up to 640×480 officially |
| VGA → DVI-D | Analog → digital; requires active converter with signal processing |
| USB to Ethernet | Active adapter; needed on thin laptops without RJ45 ports |
| USB-C to USB-A | Passive adapter or cable; allows legacy USB-A peripherals on USB-C-only laptops |
| USB hub | Single USB connection → multiple port types (USB, HDMI, Ethernet, SD, etc.) |
| Passive adapter | No signal conversion; just changes connector shape |
| Active converter | Performs signal processing; may require power |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Hardware Domain**, covering video and USB adapters/converters, compatibility rules, and multi-port USB hubs.
