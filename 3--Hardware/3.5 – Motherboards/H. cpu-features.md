# CompTIA A+ 220-1201 — CPU Features

> **Exam Domain Reference** | Core 1 (220-1201) — Hardware (Domain 3)  
> Topics: 32-bit vs. 64-bit processors, x86 vs. x64, ARM architecture, CPU cores

---



## 32-bit vs. 64-bit Processors

The bit-width of a processor describes how much data it can process at once and how much memory it can address.

| Feature | 32-bit | 64-bit |
|---|---|---|
| Max addressable memory | 4 GB (2³²) | ~17 billion GB (2⁶⁴) |
| Intel naming | x86 (reference to 8086 CPU) | x64 |
| OS required | 32-bit OS | 64-bit OS |
| Common today | Rare (legacy only) | Standard |

**Why 64-bit matters:** Modern applications and workloads require far more than 4 GB of RAM. A 64-bit processor can theoretically address an enormous amount of memory, allowing operating systems to scale to very large memory configurations.

> **Exam Tip:** x86 = 32-bit; x64 = 64-bit. These naming conventions appear frequently on the exam and in Windows system information.

---

## Application & Driver Compatibility

**Hardware drivers:**
- A 64-bit OS requires **64-bit drivers**
- A 32-bit OS requires **32-bit drivers**
- Drivers are not interchangeable between architectures

**Applications:**
- A **32-bit OS cannot run 64-bit applications**
- A **64-bit OS can usually run 32-bit applications** (backward compatible)

**Windows Program Files structure:**

| Folder | Contains |
|---|---|
| `Program Files` | 64-bit applications |
| `Program Files (x86)` | 32-bit applications |

When a 32-bit application installs on a 64-bit Windows system, it goes into `Program Files (x86)` automatically.

---

## ARM Architecture

**ARM (Advanced Risk Machine / Advanced RISC Machine)** is a CPU architecture created by **ARM Limited**, which licenses the design to chip manufacturers rather than making chips itself.

**Key characteristics:**

| Feature | Detail |
|---|---|
| Power consumption | Very low — ideal for battery-powered devices |
| Heat output | Minimal |
| Performance | Fast, efficient instruction processing |
| Licensing model | ARM Ltd. licenses the spec; third parties manufacture chips |

**Where ARM is used:**
- **~99% of mobile phones** use ARM processors
- Tablets and wearables
- Increasingly in **laptops and desktops** (e.g., Apple Silicon M-series)

ARM's efficiency advantage comes from its **RISC (Reduced Instruction Set Computing)** design — simpler, more efficient instructions compared to the complex instruction sets of traditional x86 CPUs.

---

## CPU Cores

A modern CPU package contains multiple **cores** — each core is essentially an independent processor capable of executing instructions simultaneously.

**Core count examples:** 4-core, 8-core, 16-core processors

**What each core contains:**
- Individual CPU execution unit
- Dedicated **cache memory** for that core

**Benefit:** Multiple cores can process multiple instructions in parallel — significantly increasing overall computing throughput compared to a single-core CPU.

**Common reference points:**

| Core Count | Typical Use |
|---|---|
| 2–4 cores | Basic laptops, budget desktops |
| 6–8 cores | Mainstream desktops, gaming |
| 12–16+ cores | Workstations, high-end systems |
| 32–64+ cores | Servers, data center CPUs |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| 32-bit (x86) | Max 4 GB RAM; Intel 8086 legacy naming |
| 64-bit (x64) | Theoretical 17 billion GB; current standard |
| x86 = 32-bit | Intel naming based on 8086 processor line |
| x64 = 64-bit | Current standard for desktops, laptops, servers |
| 64-bit OS | Can run 32-bit apps; cannot run on 32-bit hardware |
| 32-bit OS | Cannot run 64-bit apps |
| Program Files (x86) | Windows folder for 32-bit apps on 64-bit OS |
| ARM | Advanced Risk Machine; low power; 99% of mobile phones |
| ARM licensing | ARM Ltd. creates specs; others manufacture chips |
| CPU cores | Multiple independent processors in one package; each has own cache |
| More cores | More simultaneous instruction execution = higher throughput |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Hardware Domain**, covering CPU architecture differences (32-bit/64-bit/x86/x64/ARM) and multi-core processor features.
