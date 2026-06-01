# CompTIA A+ 220-1201 — Motherboard Connections

> **Exam Domain Reference** | Core 1 (220-1201) — Hardware (Domain 3)  
> Topics: Main power connector (20/24-pin), PCIe power (6/8-pin), SATA data, M.2, pin headers

---



## Main Power Connector

The main power connector supplies **3.3V, 5V, and 12V DC** power to the motherboard and its attached components.

| Version | Pins | Notes |
|---|---|---|
| Older ATX | 20-pin | Legacy motherboards |
| Modern ATX | 24-pin | Current standard |

**Compatibility:** A 24-pin connector can often be used on a 20-pin motherboard — the extra 4 pins simply have no socket. Some power supply cables are modular, allowing the 4-pin section to be detached, leaving a 20-pin connector.

**Keying:** The connector's pins have different shapes that allow only one correct orientation — prevents incorrect insertion. A locking latch secures the connector in place; it must be unlatched to remove.

---

## PCIe Supplemental Power Connectors

Some adapter cards — most commonly **graphics cards** — require more power than the motherboard alone can deliver through the PCIe slot. A direct power connector from the power supply provides this additional power.

| Connector | Pins | Power Delivered |
|---|---|---|
| PCIe 6-pin | 6 | 75W |
| PCIe 8-pin | 8 | 150W |

**Flexible design:** Some PCIe power connectors are designed as 8-pin with a detachable 2-pin section, allowing use as either a 6-pin or 8-pin connector depending on the card's requirement.

**Where to find it:** Look for power connectors on the **top or side edge** of a graphics card. If present, they must be connected for the card to function properly.

---

## SATA Data Connectors

SATA data connectors on the motherboard provide the data link between the motherboard and SATA storage drives (HDDs, SSDs).

- **Shape:** Distinctive **L-shaped** connector — keyed to prevent incorrect insertion
- **Function:** Data only — a separate SATA power cable from the power supply powers the drive
- **Quantity:** Equals the maximum number of SATA drives supported

Some motherboards also include an **eSATA** port (external SATA) on the rear I/O panel, or it may be provided via a PCIe expansion card that adds eSATA ports to the outside of the system.

---

## M.2 Connector

The M.2 slot is a compact, cable-free interface for SSDs directly on the motherboard.

- Small connector — requires a close look to find on a busy motherboard
- No separate data or power cables needed — the drive plugs directly into the slot
- Secured with a single screw after installation
- Supports SATA or NVMe protocols depending on slot type and drive key (B/M/B+M)

---

## Pin Headers

**Pin headers** (also called header pins) are rows of bare pins sticking up from the motherboard surface. They provide simple electrical connections for case components and low-bandwidth interfaces.

**Common pin header uses:**

| Header Type | Connected To |
|---|---|
| Power button | Case power switch |
| Reset button | Case reset switch |
| HDD activity LED | Hard drive activity light on case |
| Power LED | Power indicator light on case |
| USB 2.0 header | Front-panel USB ports on case |
| USB 3.0 header | Front-panel USB 3.0 ports on case |
| TPM header | Trusted Platform Module (security chip) |
| Audio header | Front-panel headphone/mic jacks |

**How to connect:** Individual wires from the case connect to the correct pin header pairs. The motherboard is typically labeled (silkscreen) to identify each header's function, or a legend is printed in the manual.

> **Exam Tip:** Front panel connectors (power button, reset, HDD LED) are single-wire pairs connected to specific pin header locations on the motherboard. Getting these wrong is a common cause of a system that won't power on.

---

## Connector Quick Reference

| Connector | Pins | Voltage/Power | Purpose |
|---|---|---|---|
| Main ATX power | 20 or 24 | 3.3V / 5V / 12V | Motherboard primary power |
| PCIe 6-pin | 6 | 75W | GPU / high-power adapter supplemental power |
| PCIe 8-pin | 8 | 150W | GPU / high-power adapter supplemental power |
| SATA data | 7 | N/A (data only) | Storage drive data connection |
| M.2 slot | varies | Power + data | NVMe or SATA SSD; no cables |
| Pin headers | 2+ | Low voltage | Case buttons, LEDs, USB, TPM, audio |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| 24-pin ATX | Modern main power; 3.3V/5V/12V; keyed; locking latch |
| 20-pin legacy | Can accept a 24-pin connector with 4 pins hanging off |
| PCIe 6-pin | 75W supplemental power for adapter cards |
| PCIe 8-pin | 150W supplemental power; can detach 2 pins → 6-pin |
| SATA data | L-shaped; 7 pins; data only; no power |
| M.2 | Cable-free SSD slot; one screw secures it |
| Pin headers | Bare pins for case buttons, LEDs, USB, TPM, audio |
| Front panel headers | Power/reset buttons and LEDs connect here; labeled on motherboard |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Section 3.5 — Hardware Domain**, covering motherboard power connectors, storage interfaces, M.2, and pin header connections.
