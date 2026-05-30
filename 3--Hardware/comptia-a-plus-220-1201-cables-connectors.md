# CompTIA A+ 220-1201 — Cables & Connectors

> **Exam Domain Reference** | Core 1 (220-1201) — Hardware (Domain 3)  
> Topics: Fiber optic (multimode/single-mode), USB versions & connectors, Serial (DB-9/DB-25, RS-232), Thunderbolt

---

## Table of Contents

1. [Fiber Optic Cable](#fiber-optic-cable)
   - [How Fiber Works](#how-fiber-works)
   - [Multimode vs. Single-Mode Fiber](#multimode-vs-single-mode-fiber)
   - [Fiber Connectors](#fiber-connectors)
2. [USB — Universal Serial Bus](#usb--universal-serial-bus)
   - [USB Versions & Speeds](#usb-versions--speeds)
   - [USB Connector Types](#usb-connector-types)
   - [USB-C](#usb-c)
3. [Serial Cables — DB-9 & DB-25](#serial-cables--db-9--db-25)
4. [Thunderbolt](#thunderbolt)
5. [Connector & Cable Summary](#connector--cable-summary)
6. [Key Takeaways](#key-takeaways)

---

## Fiber Optic Cable

### How Fiber Works

Fiber optic cable transmits data as **light pulses** rather than electrical signals through copper.

**Advantages over copper:**
- Immune to **RF (Radio Frequency) interference** and EMI
- Signals travel much longer distances without degradation
- More difficult to tap — better physical security
- Ideal for industrial environments with heavy electrical interference

**Construction (inside out):**
```
[Light source] → [High-reflective-index Core] → [Low-reflective-index Cladding] → [Buffer coating]
```

- **Core** — the glass or plastic pathway the light travels through
- **Cladding** — surrounds the core; different refractive index causes light to reflect back into the core (total internal reflection)
- **Buffer coating** — protects the fragile core and cladding from physical damage
- **Ferrule** — the ceramic tip inside the connector that protects and aligns the fiber end

**Light sources used:**
- **LED** — inexpensive; used with multimode fiber (short range)
- **Laser** — precise; used with single-mode fiber (long range)

### Multimode vs. Single-Mode Fiber

| Feature | Multimode (MMF) | Single-Mode (SMF) |
|---|---|---|
| Core size | Larger | Much smaller (narrower) |
| Light paths | Multiple modes (paths) through the core | Single path through the core |
| Light source | LED | Laser |
| Distance | Up to ~2 km | Many kilometers (no regeneration needed) |
| Cost | Less expensive | More expensive |
| Common use | Inside buildings; short-range connections | Long-range; campus/WAN/carrier links |

> **Exam Tip:** Multimode = **M**ultiple paths, **M**ore affordable, **M**oderate distance. Single-mode = **S**ingle path, **S**uperior distance, laser-driven.

### Fiber Connectors

Common fiber connector types (identified by shape and locking mechanism):

| Connector | Shape | Notes |
|---|---|---|
| **LC** | Small form-factor; rectangular | Most common in data centers |
| **SC** | Square push-pull | Common; older installations |
| **ST** | Round bayonet twist-lock | Older; mostly legacy |
| **MT-RJ** | Small; dual-fiber | Less common |

All fiber connectors contain a **ceramic ferrule** that holds and aligns the fiber end for precise light transmission.

---

## USB — Universal Serial Bus

USB is the standard connection type for keyboards, mice, printers, storage devices, and most computer peripherals.

### USB Versions & Speeds

| Version | Marketing Name | Max Speed | Max Cable Length |
|---|---|---|---|
| **USB 1.1** (low speed) | — | 1.5 Mbps | 3 m |
| **USB 1.1** (full speed) | — | 12 Mbps | 5 m |
| **USB 2.0** | Hi-Speed | 480 Mbps | 5 m |
| **USB 3.0** | SuperSpeed | 5 Gbps | 3 m |
| **USB 3.1** | SuperSpeed+ | 10 Gbps | 3 m |
| **USB 3.2** | SuperSpeed+ | 20 Gbps | 3 m |

> **Note:** USB specifications do not define an exact maximum cable length — the distances above are practical maximums to maintain rated throughput.

### USB Connector Types

| Connector | Version | Common Use |
|---|---|---|
| **Standard-A** | 1.1 / 2.0 / 3.0 | Host side (computer, hub) |
| **Standard-B** | 1.1 / 2.0 | Printers, older peripherals |
| **Standard-B (3.0)** | 3.0 | Taller than 2.0 Standard-B |
| **Mini-B** | 1.1 / 2.0 | Older mobile devices, cameras |
| **Micro-B** | 1.1 / 2.0 | Smartphones, tablets (pre-USB-C) |
| **Micro-B (3.0)** | 3.0 | Different, wider form factor than 2.0 Micro-B |
| **USB-C** | 3.1 / 3.2 / 4.0 | Universal modern standard |

### USB-C

USB-C is the modern standardized connector designed to replace all previous USB connector types.

**Key characteristics:**
- **Reversible** — no wrong orientation
- **Describes the physical connector only** — not the speed or signal type
- Can carry: USB data, DisplayPort video, HDMI video, Thunderbolt signals, power (USB PD)
- Similar in size to Micro-B but fully reversible
- The same USB-C port may support very different capabilities depending on the device

> **Exam Tip:** USB-C is a **connector shape**, not a speed rating. A USB-C port could be USB 2.0, 3.2, or Thunderbolt 3/4 — the connector looks identical regardless.

---

## Serial Cables — DB-9 & DB-25

Before USB, serial cables were the standard for connecting peripherals and devices.

| Connector | Pins | Also Called | Common Use |
|---|---|---|---|
| **DB-25** | 25 | DB-25 | Older modems, printers |
| **DB-9** | 9 | DE-9 (technically correct) | Console access to network equipment |

**RS-232:** The signaling standard used over serial cables — *Recommended Standard 232*, in use since 1969. Defines voltage levels and timing for serial data transmission.

**Modern use of DB-9:**
- Connecting to the **console port** on older switches, routers, and firewalls for out-of-band management
- Useful when normal network access to a device is unavailable
- Console ports may be DB-9, RJ45 (sending serial, not Ethernet), or USB depending on the device

**Adapter chain for modern laptops:**
```
Laptop (USB-C) → USB-C to USB-A adapter → USB to DB-9 adapter → DB-9 to RJ45 rollover cable → Console port
```

---

## Thunderbolt

Thunderbolt is a **high-speed serial interface** that carries both **data and power** over a single cable.

### Thunderbolt Versions

| Version | Connector | Max Throughput | Max Copper Length | Notes |
|---|---|---|---|---|
| **Thunderbolt 1** | Mini DisplayPort | 10 Gbps × 2 channels = 20 Gbps | — | Dual 10G channels |
| **Thunderbolt 2** | Mini DisplayPort | 20 Gbps (aggregated) | — | Combined channels |
| **Thunderbolt 3** | **USB-C** | 40 Gbps (aggregated) | 3 m copper / 60 m optical | Widely adopted |
| **Thunderbolt 4** | USB-C | 40 Gbps (aggregated) | 3 m copper | Dual 4K video; more PCIe bandwidth |

**Key Thunderbolt features:**
- **Daisy chaining** — devices can chain together; the host connects to one device, which connects to the next, and so on (up to 6 devices in a chain)
- **Data + power** on a single cable
- Thunderbolt 3/4 use the **USB-C physical connector** — but the port must be labeled with the Thunderbolt logo (⚡) to confirm Thunderbolt capability

> **Thunderbolt 4 improvements over 3:** Dual 4K display support, increased PCIe bandwidth to peripherals — same 40 Gbps speed but higher minimum performance requirements.

---

## Connector & Cable Summary

| Cable/Connector | Signal Type | Max Speed / Distance | Primary Use |
|---|---|---|---|
| Multimode fiber | Light (LED) | ~2 km | Short-range; in-building |
| Single-mode fiber | Light (laser) | Kilometers | Long-range; WAN/carrier |
| USB 2.0 | Electrical | 480 Mbps / 5 m | General peripherals |
| USB 3.0 | Electrical | 5 Gbps / 3 m | Fast peripherals, storage |
| USB 3.2 | Electrical | 20 Gbps / 3 m | High-speed storage |
| USB-C | Electrical | Varies by USB version | Universal modern connector |
| DB-9 / RS-232 | Electrical (serial) | Low speed | Console access; legacy |
| Thunderbolt 3 | Electrical / optical | 40 Gbps / 3 m (60 m optical) | High-speed peripherals, displays |
| Thunderbolt 4 | Electrical | 40 Gbps / 3 m | Dual 4K; enhanced PCIe |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| Multimode fiber | LED light source; multiple paths; ~2 km; short range; less expensive |
| Single-mode fiber | Laser light source; single path; kilometers; long range; more expensive |
| Ferrule | Ceramic tip inside fiber connector protecting the fiber end |
| USB 2.0 | 480 Mbps; 5 m |
| USB 3.0 | 5 Gbps (SuperSpeed); 3 m |
| USB 3.1 | 10 Gbps; 3 m |
| USB 3.2 | 20 Gbps; 3 m |
| USB-C | Physical connector only — does not define speed; reversible |
| DB-9 | 9-pin serial; RS-232; used for console access to network devices |
| RS-232 | Serial signaling standard since 1969 |
| Thunderbolt 1/2 | Mini DisplayPort connector; up to 20 Gbps |
| Thunderbolt 3 | USB-C connector; 40 Gbps; 3 m copper / 60 m optical; daisy chain |
| Thunderbolt 4 | USB-C connector; 40 Gbps; dual 4K; more PCIe bandwidth |
| Daisy chaining | Thunderbolt devices can be chained — up to 6 devices from one port |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201)**, covering fiber optic cable types, USB versions and connectors, legacy serial connections, and Thunderbolt standards.
