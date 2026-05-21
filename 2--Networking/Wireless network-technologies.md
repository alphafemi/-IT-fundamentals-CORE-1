# CompTIA A+ 220-1201 — Wireless Technologies

> **Exam Domain Reference** | Core 1 (220-1201) — Networking (Domain 2)  
> Topics: 802.11 standards, Wi-Fi frequencies & channels, Bluetooth, RFID, NFC

---

## Table of Contents

1. [Overview](#overview)
2. [802.11 Wi-Fi Standards](#80211-wi-fi-standards)
   - [Naming Convention](#naming-convention)
   - [Frequencies & Channels](#frequencies--channels)
   - [Channel Bandwidth](#channel-bandwidth)
3. [Bluetooth](#bluetooth)
4. [RFID — Radio Frequency Identification](#rfid--radio-frequency-identification)
5. [NFC — Near Field Communication](#nfc--near-field-communication)
6. [Wireless Technology Comparison](#wireless-technology-comparison)
7. [Key Takeaways](#key-takeaways)

---

## Overview

Wireless technologies span a broad range of use cases — from high-speed local area networking (Wi-Fi) to short-range personal device connectivity (Bluetooth), passive asset tracking (RFID), and contactless payments (NFC). Each uses different frequencies, ranges, and communication methods suited to its purpose.

---

## 802.11 Wi-Fi Standards

Wi-Fi networks are standardized by the **IEEE (Institute of Electrical and Electronics Engineers)** under the **802.11 Committee**. These networks are commonly referred to as **802.11 networks**.

### Naming Convention

To simplify version identification, the 802.11 Committee introduced consumer-friendly names alongside the technical standard designations:

| Technical Standard | Consumer Name | Notes |
|---|---|---|
| 802.11ac | **Wi-Fi 5** | |
| 802.11ax | **Wi-Fi 6** | Standard 6 GHz band |
| 802.11ax | **Wi-Fi 6E** | Extended — uses 6 GHz band |
| 802.11be | **Wi-Fi 7** | Latest generation |

> **Exam Tip:** Know both the 802.11 designation and the Wi-Fi generation number for each standard.

### Frequencies & Channels

Wi-Fi networks operate across three frequency bands. Rather than referencing exact frequencies, the 802.11 standard groups them into **channels** for easier reference.

| Band | Characteristics | Example Channel | Actual Frequency |
|---|---|---|---|
| **2.4 GHz** | Longer range; more interference; only 3 non-overlapping channels | Channel 6 | 2.437 GHz |
| **5 GHz** | More channels; less interference; shorter range than 2.4 GHz | Channel 44 | 5.220 GHz |
| **6 GHz** | Most available spectrum; least interference; Wi-Fi 6E/7 only | Many channels | Varies |

**2.4 GHz limitations:**
- Only **3 non-overlapping 20 MHz channels** available (channels 1, 6, and 11)
- Shared with Bluetooth and other ISM-band devices
- More congested in high-density environments (apartments, offices)

**5 GHz advantages:**
- Many more non-overlapping channels
- Supports wider channel bandwidths for higher throughput
- Less interference from neighboring networks

**6 GHz advantages:**
- The most spectrum of the three bands
- Available only on Wi-Fi 6E and Wi-Fi 7 devices
- Significantly reduced congestion

### Channel Bandwidth

The wider the channel bandwidth, the higher the potential throughput. Common bandwidths used in 802.11 networks:

| Bandwidth | Notes |
|---|---|
| **20 MHz** | Standard; most compatible |
| **40 MHz** | Higher throughput; used in 5 GHz and 2.4 GHz |
| **80 MHz** | Higher throughput; 5 GHz and 6 GHz |
| **160 MHz** | Maximum; 5 GHz and 6 GHz; best performance |

> **Key Point:** Some access points and devices support **multiple bands simultaneously**, allowing devices to connect on whichever band offers the best performance.

---

## Bluetooth

Bluetooth provides short-range wireless connectivity, most commonly for personal peripherals.

| Feature | Detail |
|---|---|
| Frequency | 2.4 GHz (ISM band) |
| Maximum range (consumer) | ~10 meters |
| Network type | PAN (Personal Area Network) |
| License required | No (unlicensed ISM frequencies) |

**Common Bluetooth uses:**
- Wireless headsets and speakers
- Keyboards and mice
- Smartphone tethering
- Wearables (smartwatches, fitness trackers)

**ISM Band:** The 2.4 GHz frequency is part of the **Industrial, Scientific, and Medical (ISM)** band — an unlicensed set of frequencies. This is why both Wi-Fi and Bluetooth can be used without any special licensing.

> **Note:** Because both Wi-Fi (2.4 GHz) and Bluetooth share the same frequency band, interference between the two is possible in congested environments.

---

## RFID — Radio Frequency Identification

RFID uses radio waves to identify and track tags attached to objects, animals, or people.

### How RFID Works

1. An **RFID tag** (passive or active) is attached to or embedded in an object
2. An **RFID scanner** emits a radio frequency signal
3. The signal **powers the passive tag** (no battery needed) and prompts it to transmit its ID code
4. The scanner receives the ID and **compares it against a database** to identify the object

### RFID Tag Types

| Type | Power Source | Range | Use Cases |
|---|---|---|---|
| **Passive** | Powered by scanner's RF signal | Short range | Access cards, product tags, pet microchips |
| **Active** | Internal battery | Longer range | Asset tracking, vehicle identification |

### Common RFID Applications

- Building **access control** (key cards/badges)
- **Retail product tracking** and inventory management
- **Assembly line** and supply chain management
- **Pet microchips** (grain-of-rice sized implant)

**RFID tag anatomy (passive flat card style):**
- The **loop around the outside** is the antenna
- The **small chip in the center** is the RFID IC
- No battery — entirely powered by the scanner's radio signal

---

## NFC — Near Field Communication

NFC builds on RFID technology but extends it to support **two-way communication** between devices.

| Feature | RFID | NFC |
|---|---|---|
| Communication | One-way (tag → reader) | Two-way |
| Range | Varies (cm to meters) | ≤ 4 cm |
| Common use | Tracking, access control | Payments, pairing, identification |

### Common NFC Use Cases

- **Contactless payments** — tap phone or smartwatch at a point-of-sale terminal
- **Device pairing** — use NFC to pass Wi-Fi or Bluetooth configuration to a new device
- **Access control** — phone or watch used as a door key instead of a physical card
- **Identification** — NFC-enabled ID in phones replaces physical badges

---

## Wireless Technology Comparison

| Technology | Frequency | Range | License | Communication | Primary Use |
|---|---|---|---|---|---|
| **Wi-Fi (802.11)** | 2.4 / 5 / 6 GHz | Building / campus | No (ISM) | Two-way | LAN / internet access |
| **Bluetooth** | 2.4 GHz | ~10 meters | No (ISM) | Two-way | Personal peripherals, PAN |
| **RFID (passive)** | Varies | cm to meters | No | One-way | Asset tracking, access cards |
| **RFID (active)** | Varies | Longer | No | One-way | Long-range asset tracking |
| **NFC** | 13.56 MHz | ≤ 4 cm | No | Two-way | Payments, pairing, ID |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| 802.11ac = Wi-Fi 5 | Older but still widely used |
| 802.11ax = Wi-Fi 6/6E | Current standard; 6E adds 6 GHz band |
| 802.11be = Wi-Fi 7 | Latest generation |
| 2.4 GHz | 3 non-overlapping channels; longer range; more interference |
| 5 GHz | More channels; less interference; shorter range |
| 6 GHz | Most spectrum; Wi-Fi 6E/7 only |
| Channel bandwidth | 20 / 40 / 80 / 160 MHz — wider = faster |
| Bluetooth | 2.4 GHz ISM; ~10 m range; PAN; no license needed |
| ISM band | Unlicensed 2.4 GHz; shared by Wi-Fi and Bluetooth |
| RFID passive | No battery; powered by scanner signal; short range |
| RFID active | Battery-powered; longer range |
| NFC | Extends RFID to two-way; ≤4 cm; payments, pairing, access |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Domain 2 — Networking**, covering wireless networking standards, frequencies, and short-range wireless technologies including Bluetooth, RFID, and NFC.
