# CompTIA A+ 220-1201 — Storage Technologies

> **Exam Domain Reference** | Core 1 (220-1201) — Hardware (Domain 3)  
> Topics: HDD, SSD, NVMe, PCIe storage, SAS, mSATA, M.2, flash memory, optical drives

---



## Storage vs. Memory

| RAM | Storage |
|---|---|
| Volatile — data lost on power off | Non-volatile — data retained without power |
| Temporary working memory | Long-term data retention |
| Very fast | Slower than RAM (varies by type) |

---

## Hard Disk Drives (HDD)

HDDs store data magnetically on **spinning platters** — mechanical devices with moving parts.

**Internal components:**
- **Platters** — magnetic discs where data is stored
- **Spindle** — motor that spins the platters
- **Actuator arm** — moves the read/write head across the platters
- **Read/write head** — reads and writes data to the platter surface

**Spindle speeds (RPM):**

| Speed | Use Case |
|---|---|
| 5,400 RPM | Laptops, low-power drives |
| 7,200 RPM | Standard desktop drives |
| 10,000 RPM | Performance desktop/workstation |
| 15,000 RPM | Enterprise/server drives |

Higher RPM = lower latency = faster data access (the platter spins to the data faster).

**Form factors:**
- **3.5-inch** — desktop computers
- **2.5-inch** — laptops and mobile devices

**Failure risk:** Because HDDs have many moving mechanical parts (platters, spindle, actuator arm), any component can fail at any time.

---

## Solid State Drives (SSD)

SSDs store data in **non-volatile flash memory** with **no moving parts**.

**Advantages over HDD:**
- Dramatically faster read/write speeds
- More reliable — no mechanical components to fail
- Lighter and more shock-resistant

When connected via SATA, SSDs quickly reached the maximum bandwidth of the SATA interface (6 Gbps), requiring faster interfaces.

---

## Storage Interfaces & Speed

### SATA / AHCI

- **AHCI (Advanced Host Controller Interface)** — the communication standard used by SATA drives
- **SATA 3 max throughput: 6 Gbps**
- Sufficient for HDDs; bottleneck for high-performance SSDs

### NVMe & PCIe

To break through SATA's 6 Gbps limit, SSDs began connecting directly to the **PCI Express (PCIe) bus**.

**NVMe (Non-Volatile Memory Express):**
- Communication protocol designed specifically for flash storage on PCIe
- Very low latency; bypasses AHCI overhead
- Theoretical throughput via M.2 NVMe: **~20 Gbps**
- PCIe direct (adapter card): **~64 Gbps per lane**

**PCIe adapter card SSDs:** Full-size PCIe cards with SSD storage — common in desktops; not practical for laptops.

### SAS — Serial Attached SCSI

SAS is a high-performance interface for enterprise storage, evolving from the older parallel SCSI standard.

- Max throughput: **~22.5 Gbps**
- Used in large storage arrays and server environments
- SAS drive connectors look similar to SATA but are **slightly different** to prevent accidental cross-connection
- A SAS controller can use SAS drives but **not** standard SATA drives (by default)

| Interface | Max Speed | Use Case |
|---|---|---|
| SATA 3 | 6 Gbps | Standard HDDs and SATA SSDs |
| SAS | ~22.5 Gbps | Enterprise drives, storage arrays |
| NVMe (M.2) | ~20 Gbps | Modern laptop/desktop SSDs |
| PCIe (direct) | ~64 Gbps/lane | High-performance desktop SSDs |

---

## Form Factors

### mSATA

- **Mini SATA** — a smaller version of the SATA interface and form factor
- Bridged the gap between full-size SATA and the newer M.2 standard
- Largely replaced by M.2 in modern systems

### M.2

M.2 is the dominant interface for modern SSDs in laptops and desktops.

**Advantages:**
- No separate data or power cables — plugs directly into the M.2 slot on the motherboard
- Very compact
- Can support both SATA and NVMe protocols (depending on the slot and drive)

**M.2 Keys:** Small notches on the drive's connector edge indicate supported protocol and slot compatibility:

| Key | Protocol Supported |
|---|---|
| **B key** | SATA or PCIe ×2 |
| **M key** | PCIe ×4 (NVMe) |
| **B+M key** | Compatible with both B and M key slots |

> **Exam Tip:** An M.2 slot and drive must be compatible by key type. Check motherboard documentation for supported keys and protocols (SATA vs. NVMe).

**M.2 width standard:** 22 mm wide (the number in the form factor name, e.g., 2280 = 22 mm wide × 80 mm long).

---

## Flash Storage

Flash storage uses **EEPROM (Electrically Erasable Programmable Read-Only Memory)** — non-volatile memory that retains data without power.

**EEPROM limitation:** Has a finite number of write cycles — eventually becomes read-only.

**Common flash storage types:**

| Type | Notes |
|---|---|
| **USB flash drive** | Portable; widely used; easy to lose |
| **CompactFlash (CF)** | Older; larger form factor |
| **SD (Secure Digital)** | Common in cameras and mobile devices |
| **Mini SD / Micro SD** | Smaller SD variants for compact devices |
| **xD-Picture Card** | Older format for some digital cameras |

> **Flash drives are not recommended as primary backup media** — limited write cycles, small capacity, and easy to lose. Always keep a second copy elsewhere.

---

## Optical Drives

Optical drives use a **laser** to read microscopic bumps on disc surfaces.

**Common formats:**

| Format | Notes |
|---|---|
| **CD-ROM** | ~700 MB capacity; oldest format |
| **DVD-ROM** | ~4.7–8.5 GB capacity |
| **Blu-ray** | 25–100 GB capacity; highest density |

**Characteristics:**
- Slower than HDDs and SSDs
- Non-volatile — data persists without power
- Useful for archiving and reading older media
- Rarely included in modern laptops — external USB optical drives available for compatibility

---

## Storage Speed Comparison

| Technology | Interface | Approx. Max Speed | Moving Parts |
|---|---|---|---|
| HDD (5,400 RPM) | SATA | ~100 MB/s | Yes |
| HDD (7,200 RPM) | SATA | ~150 MB/s | Yes |
| SSD (SATA) | SATA 3 | ~600 MB/s | No |
| SSD (NVMe M.2) | PCIe / NVMe | ~3,500 MB/s+ | No |
| SSD (PCIe card) | PCIe direct | ~8,000 MB/s+ | No |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| HDD | Magnetic; spinning platters; mechanical; 3.5" (desktop) or 2.5" (laptop) |
| HDD RPM | Higher RPM = faster access; 5,400 / 7,200 / 10,000 / 15,000 RPM |
| SSD | Flash memory; no moving parts; much faster than HDD |
| SATA max | 6 Gbps; bottleneck for high-performance SSDs |
| AHCI | Communication standard for SATA |
| NVMe | PCIe-based protocol for SSDs; ~20 Gbps via M.2; low latency |
| SAS | Serial Attached SCSI; ~22.5 Gbps; enterprise storage arrays |
| SAS ≠ SATA | Similar connectors but physically different to prevent cross-connection |
| mSATA | Mini SATA; transitional form factor; largely replaced by M.2 |
| M.2 | No cables; B key / M key / B+M key; supports SATA or NVMe |
| EEPROM | Flash memory; non-volatile; finite write cycles |
| Flash drives | Not recommended as primary backup — limited writes, easy to lose |
| Optical | CD/DVD/Blu-ray; laser-read; slow; good for archives |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Hardware Domain**, covering all major storage technologies, interfaces, form factors, and speed comparisons.
