# CompTIA A+ 220-1201 — Expansion Slots: PCI & PCIe

> **Exam Domain Reference** | Core 1 (220-1201) — Hardware (Domain 3)  
> Topics: Computer bus, PCI (32-bit/64-bit), PCI Express (PCIe) lanes, parallel vs. serial, installation

---

## Table of Contents

1. [The Computer Bus](#the-computer-bus)
2. [PCI — Peripheral Component Interconnect](#pci--peripheral-component-interconnect)
3. [PCI Express (PCIe)](#pci-express-pcie)
4. [PCI vs. PCIe Comparison](#pci-vs-pcie-comparison)
5. [Installing & Removing Expansion Cards](#installing--removing-expansion-cards)
6. [Key Takeaways](#key-takeaways)

---

## The Computer Bus

A **bus** is a pathway on the motherboard that connects components to each other — memory to CPU, expansion slots to the chipset, and so on.

Expansion slot buses allow additional cards (GPUs, NICs, sound cards, storage controllers) to be added to the motherboard, increasing the system's functionality.

---

## PCI — Peripheral Component Interconnect

- **Introduced:** 1994
- **Communication:** **Parallel** — multiple bits sent simultaneously across multiple lines
- **Versions:**
  - **32-bit PCI** — 32 separate data lines; sends 32 bits at once
  - **64-bit PCI** — 64 separate data lines; sends 64 bits at once
- **Status:** Legacy — found on older motherboards; mostly replaced by PCIe on modern systems

**How parallel works:** Each bit in the word travels on its own dedicated wire simultaneously. A 32-bit bus sends 32 bits across 32 wires at the same time.

**Physical keys:** Slots have small tabs (keys) that indicate the power level of the card. A 64-bit PCI card has extra connectors and a separate keyway to distinguish it from a 32-bit card.

---

## PCI Express (PCIe)

- **Communication:** **Serial** — one bit at a time per lane; multiple lanes multiply throughput
- **Status:** Current standard on modern motherboards
- **Lanes:** The number of serial pathways. Written as **×1, ×2, ×4, ×8, ×16** (pronounced "by 1", "by 4", etc.)

**How serial lanes work:**
Each PCIe lane is actually two unidirectional paths — one for transmit, one for receive.

```
PCIe ×1:   1 TX lane + 1 RX lane
PCIe ×4:   4 TX lanes + 4 RX lanes  (4× throughput of ×1)
PCIe ×16:  16 TX lanes + 16 RX lanes (most common for GPUs)
```

More lanes = higher bandwidth. A ×16 slot provides 16× the bandwidth of a ×1 slot.

**Slot sizes:** PCIe slots come in different physical lengths matching their lane counts (×1 is shortest; ×16 is longest). However, a smaller card can be placed in a larger slot — the extra lanes simply go unused.

**Physical identification vs. PCI:**
- PCIe keyway is **closer to the edge** of the motherboard
- PCI keyway is **farther from the edge**
- PCIe cards often have a **retention latch** on the far end of the slot that must be released before removal

---

## PCI vs. PCIe Comparison

| Feature | PCI | PCI Express (PCIe) |
|---|---|---|
| Introduced | 1994 | Later (mid-2000s) |
| Communication | Parallel | Serial |
| Bus widths | 32-bit or 64-bit | ×1, ×2, ×4, ×8, ×16 lanes |
| Throughput | Lower | Much higher (scales with lanes) |
| Keyway position | Further from motherboard edge | Closer to motherboard edge |
| Retention latch | No | Yes (on far end of slot) |
| Status | Legacy | Current standard |

---

## Installing & Removing Expansion Cards

### Installing

1. Align the card's connector with the correct slot (PCIe or PCI)
2. Ensure keyways are aligned
3. Press the card **straight down** — evenly and firmly — until fully seated (no copper contacts visible)
4. Screw the card's bracket to the computer case
5. For PCIe: the retention latch on the motherboard clicks into place automatically

### Removing

1. Remove the screw securing the bracket to the case
2. **For PCIe:** Release the retention latch on the far end of the slot before pulling the card out
3. Lift the card straight up and out

> **Exam Tip:** PCIe cards have a retention latch that locks the far end to the motherboard. Forgetting to release it before pulling can damage the card or slot.

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| Computer bus | Pathway connecting motherboard components; expansion slots use buses |
| PCI | Peripheral Component Interconnect; 1994; parallel; 32-bit or 64-bit |
| Parallel communication | Multiple bits sent simultaneously across multiple wires |
| PCIe | PCI Express; serial; current standard; scales with number of lanes |
| Serial communication | One bit at a time per lane; multiple lanes multiply bandwidth |
| PCIe lane notation | ×1, ×4, ×8, ×16 — pronounced "by 1", "by 4", etc. |
| PCIe keyway | Closer to motherboard edge (vs. PCI further from edge) |
| PCIe retention latch | Must be released before removing a PCIe card |
| Smaller card in larger slot | Allowed — extra lanes are unused but no damage occurs |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Section 3.5 — Hardware Domain**, covering PCI and PCIe expansion slot technologies, lane configurations, and card installation procedures.
