# CompTIA A+ 220-1201 — RAM & Memory Technologies

> **Exam Domain Reference** | Core 1 (220-1201) — Hardware (Domain 3)  
> Topics: RAM vs. storage, DIMM, SO-DIMM, SDRAM, DDR versions, backward compatibility, keying

---

---

## What RAM Is (and Isn't)

**RAM (Random Access Memory)** is temporary, high-speed working memory used while the computer is running.

| RAM | Storage (HDD/SSD) |
|---|---|
| Temporary — lost when powered off | Permanent — retains data |
| Very fast | Slower than RAM |
| Holds active applications and data | Holds installed programs and files |
| Required for CPU to process data | Used for long-term data storage |

**How data flows:**
```
Storage (HDD/SSD) → loaded into → RAM → processed by → CPU → result saved back to → Storage
```

The CPU can only work with data that is currently in RAM. Everything must be loaded into memory before it can be processed.

> **Exam Tip:** Do not confuse RAM with storage. "Running out of memory" = RAM is full, not storage.

---

## DIMM — Dual Inline Memory Module

A **DIMM** is the physical module that holds multiple RAM chips and installs into the motherboard's memory slot.

**Why "Dual Inline":**
- One side of the module has a row of electrical contacts
- The **other side has a separate, different set of contacts**
- Two separate lines of contacts = Dual Inline

**Data width:** DIMMs transfer data in **64-bit blocks**.

**Installation:**
- Push the DIMM straight down into the slot until the side clips snap into place
- To remove: push the side clips outward — the module pops up for removal

---

## SO-DIMM — Laptop Memory

**SO-DIMM (Small Outline DIMM)** is the compact memory form factor used in laptops and mobile devices — approximately **half the size** of a standard DIMM.

- Installed **horizontally** in most laptops to conserve vertical space
- Slide in at an angle, then press flat to lock with side clips
- Functionally identical to a DIMM — just physically smaller

| Form Factor | Used In |
|---|---|
| DIMM | Desktop computers, servers |
| SO-DIMM | Laptops, small form-factor PCs, mobile devices |

---

## SDRAM & Double Data Rate (DDR)

**SDRAM (Synchronous Dynamic RAM)** synchronizes all memory operations to the system's common clock, keeping data transfers consistent across components.

**Single Data Rate (older):** One data transfer per clock cycle.

**DDR (Double Data Rate):** Transfers data on **both the rising and falling edge** of each clock cycle — effectively **doubling throughput** without increasing the clock speed.

```
Single data rate:    ↑ transfer     ↑ transfer     ↑ transfer
DDR:                 ↑ transfer  ↓ transfer  ↑ transfer  ↓ transfer
                     (2× the data in the same time)
```

---

## DDR Versions

Each DDR generation increases speed and capacity but is **not backward compatible** with previous versions.

| Version | Notes |
|---|---|
| **DDR** | Original DDR; obsolete |
| **DDR2** | Faster than DDR; obsolete |
| **DDR3** | Increased capacity and speed over DDR2 |
| **DDR4** | Faster than DDR3; current standard in many systems |
| **DDR5** | Latest generation; highest transfer speeds |

**Key rule:** DDR3 cannot be installed in a DDR4 motherboard. DDR4 cannot be installed in a DDR5 motherboard. Each generation requires a motherboard specifically designed for it.

---

## Physical Keying & Compatibility

To **prevent installing the wrong memory**, DDR modules have a **notch (key)** cut at a specific location along the bottom edge of the module. The motherboard's memory slot has a corresponding **ridge** in the matching position.

- Each DDR generation has the key in a **different position**
- A DDR4 module physically **cannot be inserted** into a DDR3 slot — the notch won't align
- This hardware keying is a built-in safeguard against incompatible installations

> **Practical tip:** Always check your motherboard documentation for the supported DDR generation, speed, and maximum capacity before purchasing or installing RAM.

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| RAM | Temporary high-speed working memory; lost on power off |
| RAM ≠ storage | RAM holds active data; storage holds files long-term |
| DIMM | Full-size module; dual inline contacts; 64-bit data width |
| SO-DIMM | Half-size DIMM for laptops; installed horizontally |
| SDRAM | Synchronized to system clock |
| DDR | Double Data Rate; transfers on rising AND falling clock edge; 2× throughput |
| DDR versions | DDR → DDR2 → DDR3 → DDR4 → DDR5; each faster; none backward compatible |
| Keying | Physical notch prevents inserting wrong DDR generation into a slot |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Hardware Domain**, covering RAM types, DIMM and SO-DIMM form factors, SDRAM, DDR technology, and DDR version compatibility.
