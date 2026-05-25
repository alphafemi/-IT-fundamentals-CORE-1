# CompTIA A+ 220-1201 — Internet Connection Types

> **Exam Domain Reference** | Core 1 (220-1201) — Networking (Domain 2)  
> Topics: Satellite, fiber, cable/DOCSIS, DSL/ADSL, cellular tethering/hotspot, WISP

---

## Table of Contents

1. [Overview](#overview)
2. [Satellite](#satellite)
3. [Fiber Optic](#fiber-optic)
4. [Cable (DOCSIS)](#cable-docsis)
5. [DSL — Digital Subscriber Line](#dsl--digital-subscriber-line)
6. [Cellular — Tethering & Mobile Hotspot](#cellular--tethering--mobile-hotspot)
7. [WISP — Wireless Internet Service Provider](#wisp--wireless-internet-service-provider)
8. [Connection Type Comparison](#connection-type-comparison)
9. [Key Takeaways](#key-takeaways)

---

## Overview

Internet connectivity reaches end users through many different technologies depending on location, infrastructure availability, and cost. Each type has distinct speed characteristics, latency profiles, distance limitations, and use cases — all of which are tested on the A+ exam.

---

## Satellite

Satellite internet communicates between a ground antenna and an orbiting satellite, then back to Earth.

**Characteristics:**
- Available virtually anywhere on Earth — ideal for **remote locations** with no terrestrial options
- Typical speeds: **~100 Mbps down / ~5 Mbps up**
- Higher cost than terrestrial connections due to launch and maintenance of satellites

**Latency:**

| Type | Latency | Notes |
|---|---|---|
| Traditional (GEO) | ~500 ms (250 ms up + 250 ms down) | Satellite at very high orbit |
| Starlink (LEO) | ~25–60 ms | Low Earth Orbit; much closer to ground |

**Limitations:**
- Requires **line of sight** to the satellite — obstructions block the signal
- **Rain fade** — heavy storms can degrade or drop the connection

---

## Fiber Optic

Fiber transmits data as light pulses through thin glass or plastic strands.

**Advantages over copper:**
- Much higher data capacity over much longer distances
- Ideal for **wide area networks (WANs)** and metropolitan connections
- Increasingly available directly to homes (FTTH — Fiber to the Home)

**Disadvantages:**
- More expensive than copper for cabling and equipment
- Repair costs are higher than copper
- Requires conversion at the home/office (ONT) from fiber to copper

**Common WAN implementations:**
- **SONET rings** — carrier-grade fiber rings in metro/regional networks
- **Multi-wavelength (DWDM)** — multiple data streams over one fiber using different light wavelengths

---

## Cable (DOCSIS)

Cable internet runs over the same **coaxial cable** infrastructure used for cable TV.

**Key technology:** **Broadband** — multiple frequencies run simultaneously on the same wire, carrying different service types (TV, voice, data) at the same time.

**Standard:** **DOCSIS** (Data Over Cable Service Interface Specification) — defines how data is transmitted over cable networks. Multiple DOCSIS versions provide increasing speeds.

**Speeds:** typically **50 Mbps – 1 Gbps+**

**What a cable connection delivers:**
- Internet data
- Television
- Voice (VoIP)

All over the same coaxial cable from the cable company.

---

## DSL — Digital Subscriber Line

DSL delivers internet over existing **telephone copper wire**, alongside regular voice calls.

**Also called:** **ADSL — Asymmetric Digital Subscriber Line**

**Why "asymmetric"?** Download speed is significantly faster than upload speed — common with residential connections.

| Direction | Typical Speed |
|---|---|
| Download | Up to ~200 Mbps |
| Upload | Up to ~20 Mbps |

**Distance limitation:**
- Speed decreases as distance from the **central office (CO)** increases
- Maximum effective distance: **~10,000 feet** from the CO
- The closer to the CO, the faster the connection

> **Exam Tip:** DSL = telephone lines; ADSL = asymmetric (download faster than upload); max ~10,000 ft from central office.

---

## Cellular — Tethering & Mobile Hotspot

Cellular networks divide geography into **cells** served by antennas — the same infrastructure used for mobile phone calls.

**Two ways to share cellular internet:**

| Method | Devices Supported | Description |
|---|---|---|
| **Tethering** | One device | Single device connects to the phone for internet access |
| **Mobile Hotspot** | Multiple devices | Phone acts as a Wi-Fi router; many devices share cellular data |

- Check with your carrier — tethering and hotspot may require an **additional plan or fee**
- Uses the same 4G/LTE or 5G network as voice calls

---

## WISP — Wireless Internet Service Provider

A WISP provides internet access over a **wireless radio link** — useful where cable, phone, or fiber infrastructure doesn't exist.

**Ideal for:** Rural areas and remote locations without wired ISP options

**How it works:**
- Customer installs an **outdoor antenna**
- Antenna connects wirelessly to the WISP's network
- Simple to set up — no underground cabling required

**Technologies used by WISPs:**
- Meshed **802.11** networks
- **5G home internet** (using mobile carrier infrastructure)
- Proprietary wireless protocols

**Speeds:** typically **10 Mbps – 1 Gbps** depending on technology and distance

---

## Connection Type Comparison

| Type | Medium | Typical Download | Latency | Distance Limit | Best For |
|---|---|---|---|---|---|
| **Satellite (GEO)** | Radio / space | ~100 Mbps | ~500 ms | None (global) | Very remote locations |
| **Satellite (Starlink)** | Radio / LEO | ~100–200 Mbps | 25–60 ms | None (global) | Remote; lower latency |
| **Fiber** | Light / glass | 1 Gbps+ | Very low | Very long | High-speed; WAN backbone |
| **Cable (DOCSIS)** | Coax | 50 Mbps – 1 Gbps+ | Low | Neighborhood | Home/business with cable TV |
| **DSL / ADSL** | Copper (phone) | Up to ~200 Mbps | Low-moderate | ~10,000 ft from CO | Areas with phone service |
| **Cellular** | Radio | Varies (4G/5G) | Low (5G) | Cell coverage area | Mobile; tethering; hotspot |
| **WISP** | Radio (wireless) | 10 Mbps – 1 Gbps | Varies | Line of sight to tower | Rural / no wired ISP |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| Satellite | Global coverage; line-of-sight required; rain fade; GEO ~500 ms latency; Starlink ~25–60 ms |
| Fiber | Light-based; long distance; expensive; SONET / DWDM for WAN; ONT at home |
| Cable | Coaxial; DOCSIS standard; broadband (multiple frequencies); 50 Mbps–1 Gbps+ |
| Broadband | Multiple frequencies on one wire simultaneously |
| DOCSIS | Data Over Cable Service Interface Specification |
| DSL / ADSL | Phone copper lines; asymmetric (download > upload); max ~10,000 ft from CO |
| Tethering | One device uses phone's cellular internet |
| Mobile hotspot | Multiple devices share phone's cellular internet |
| WISP | Wireless ISP; outdoor antenna; 10 Mbps–1 Gbps; good for rural areas |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Domain 2 — Networking**, covering internet connection technologies including satellite, fiber, cable, DSL, cellular, and wireless ISP options.
