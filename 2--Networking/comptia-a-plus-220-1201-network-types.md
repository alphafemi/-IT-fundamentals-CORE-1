# CompTIA A+ 220-1201 — Network Types

> **Exam Domain Reference** | Core 1 (220-1201) — Networking (Domain 2)  
> Topics: LAN, WAN, PAN, MAN, SAN, WLAN — definitions, characteristics, and use cases

---

## Table of Contents

1. [Overview](#overview)
2. [LAN — Local Area Network](#lan--local-area-network)
3. [WAN — Wide Area Network](#wan--wide-area-network)
4. [PAN — Personal Area Network](#pan--personal-area-network)
5. [MAN — Metropolitan Area Network](#man--metropolitan-area-network)
6. [SAN — Storage Area Network](#san--storage-area-network)
7. [WLAN — Wireless Local Area Network](#wlan--wireless-local-area-network)
8. [Network Types Comparison](#network-types-comparison)
9. [Key Takeaways](#key-takeaways)

---

## Overview

Networks are categorized by their **geographic scope** and **purpose**. Knowing the name, size, speed characteristics, and common technologies for each network type is directly tested on the A+ exam.

---

## LAN — Local Area Network

A LAN connects devices within a **close physical area** — a floor, a building, or a group of nearby buildings.

**Key characteristics:**
- Fastest speeds of any network type
- Typically uses **Ethernet (wired)** or **802.11 Wi-Fi (wireless)**
- All devices are under the same administrative control
- Single building or campus scale

> **Rule of thumb:** If you're getting the fastest speeds, you're probably on a LAN.

---

## WAN — Wide Area Network

A WAN connects networks across **long distances** — cities, states, countries, or globally.

**Key characteristics:**
- Slower than LAN due to distance and infrastructure complexity
- Connects geographically separated locations

**Common WAN technologies:**

| Technology | Description |
|---|---|
| Point-to-point serial | Dedicated leased line between two locations |
| MPLS | Multiprotocol Label Switching — carrier-managed WAN routing |
| Satellite (non-terrestrial) | Communication via orbiting satellites |
| Fiber / undersea cable (terrestrial) | Physical cable across land or ocean |

**Terrestrial vs. Non-terrestrial:**
- **Terrestrial** — WAN links that travel over land (fiber, copper, microwave towers)
- **Non-terrestrial** — WAN links that use satellites orbiting in space

---

## PAN — Personal Area Network

A PAN connects devices in the **immediate personal space** of an individual — typically within a few meters.

**Common PAN technologies:**
- **Bluetooth** — wireless headsets, speakers, keyboards, mice
- **Infrared (IR)** — short-range line-of-sight communication (older devices)
- **NFC** — Near Field Communication (≤4 cm); payments, pairing

**Real-world PAN use cases:**
- Hands-free calling and audio in a vehicle
- Wireless headsets
- Fitness trackers and health devices syncing to a smartphone
- Smartwatch connecting to a phone

---

## MAN — Metropolitan Area Network

A MAN spans a **single city or metropolitan area** — larger than a LAN but smaller than a WAN.

**Key characteristics:**
- Connects multiple remote locations within the same city
- Historically proprietary technologies; now increasingly standardized on **Metro Ethernet**
- Some cities and governments build their own MANs using **municipal fiber** (governments have right-of-way to lay their own cable)

**Metro Ethernet:** Ethernet connectivity scaled up to city-wide distances — familiar technology extended to a larger geographic area.

---

## SAN — Storage Area Network

A SAN is a **dedicated high-speed network** for centralized storage, separate from the regular data network.

**Key characteristics:**
- Provides **block-level access** — storage appears as a locally attached drive to the accessing device
- Optimized for transferring **large amounts of data** efficiently
- Runs on its own **isolated, high-speed network** to avoid impacting other traffic
- Connected to the main network via very high-speed links

**Block-level access explained:** Unlike file-level access (where you download an entire file), block-level access allows a device to read or modify a specific portion of a very large file without transferring the whole thing — much more efficient for databases and large workloads.

---

## WLAN — Wireless Local Area Network

A WLAN is a **wireless version of a LAN**, using **802.11 (Wi-Fi)** technology.

**Key characteristics:**
- Allows mobile devices, laptops, and other wireless devices to access network resources without a cable
- Uses **wireless access points** to provide coverage
- Scale by adding access points for larger buildings or campus environments
- Same geographic scope as a wired LAN — just without the cables

---

## Network Types Comparison

| Network Type | Full Name | Geographic Scope | Speed | Common Technologies |
|---|---|---|---|---|
| **LAN** | Local Area Network | Building / campus | Fastest | Ethernet, 802.11 |
| **WAN** | Wide Area Network | City to global | Slower | MPLS, serial, satellite, fiber |
| **PAN** | Personal Area Network | ~1–10 meters | Varies | Bluetooth, NFC, IR |
| **MAN** | Metropolitan Area Network | City / metro area | High | Metro Ethernet, municipal fiber |
| **SAN** | Storage Area Network | Data center (isolated) | Very high | Fibre Channel, iSCSI |
| **WLAN** | Wireless Local Area Network | Building / campus | High | 802.11 (Wi-Fi) |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| LAN | Local; fastest speeds; Ethernet or Wi-Fi; building/campus scale |
| WAN | Long distance; slower; MPLS, serial, satellite; city-to-global |
| Terrestrial WAN | Land-based links (fiber, copper, microwave) |
| Non-terrestrial WAN | Satellite-based links |
| PAN | Personal space; Bluetooth, NFC, IR; ~1–10 meters |
| MAN | City-scale; Metro Ethernet; may use municipal fiber |
| Metro Ethernet | Ethernet extended to metropolitan distances |
| SAN | Dedicated storage network; block-level access; isolated high-speed network |
| Block-level access | Read/write specific data blocks without transferring entire files |
| WLAN | Wireless LAN; 802.11; same scope as LAN but cable-free |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Domain 2 — Networking**, covering network type definitions, geographic scope, and the technologies associated with each network category.
