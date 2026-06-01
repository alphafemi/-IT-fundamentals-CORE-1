# CompTIA A+ 220-1201 — Motherboard Compatibility: Intel vs. AMD & Server Motherboards

> **Exam Domain Reference** | Core 1 (220-1201) — Hardware (Domain 3)  
> Topics: Intel vs. AMD CPUs, CPU socket compatibility, server motherboards, multisocket, rack-mount

---



## Intel vs. AMD CPUs

The two dominant CPU manufacturers for personal computers are **Intel** and **AMD**. Both make x86-compatible processors, but they are **not interchangeable** on the same motherboard.

| Characteristic | Intel | AMD |
|---|---|---|
| General reputation | Historically highest performance | Historically lower price point |
| Price vs. performance | Varies by generation | Varies by generation |
| Socket type | Intel-specific | AMD-specific |
| Compatible motherboard | Intel socket board only | AMD socket board only |

> **Important:** These generalizations shift frequently — Intel and AMD compete aggressively, and the "best value" or "best performance" crown changes with each product generation. Always evaluate current-generation specs rather than relying on historical reputation alone.

---

## CPU Socket Compatibility

The physical size of Intel and AMD processors is similar, but their **socket interfaces are different and incompatible** with each other.

- An **AMD CPU requires an AMD-compatible motherboard socket**
- An **Intel CPU requires an Intel-compatible motherboard socket**
- Attempting to install the wrong CPU in a socket physically won't work — the pin/contact layout is different

**Rule:** CPU and motherboard must be from the same manufacturer's supported socket generation. Always verify compatibility before purchasing.

---

## Installing a CPU

Modern CPU installation does not require force — the socket is designed to accept the processor with minimal pressure.

**General process:**
1. Open the socket cover/retention arm
2. Align the CPU with the socket (look for alignment notches or a triangle marker on the CPU corner)
3. **Drop the CPU into place** — it should seat without any downward pressure
4. Close the retention cover and lock with the handle
5. Apply thermal paste and attach the CPU cooler

> **Never force a CPU into a socket.** If resistance is felt, the CPU is misaligned. Forcing it will bend or break pins.

---

## Server Motherboards

Server motherboards are designed for maximum reliability, expandability, and processing power — significantly more capable than typical desktop boards.

**Key features of server motherboards:**

| Feature | Desktop Board | Server Board |
|---|---|---|
| CPU sockets | 1 | Often 2 (multisocket) |
| Memory slots | 2–8 | 6, 8, or more |
| Expansion slots | 1–7 | Many |
| Form factor | ATX / Micro-ATX / Mini-ITX | Full ATX (rack-mount) |
| Target use | Personal computing | High-availability services, databases, virtualization |

**Multisocket:** Multiple physical CPUs installed on the same motherboard. Combined CPU cores and threads scale workloads like databases, virtualization, and web services.

**Memory:** Server boards typically support more memory slots (6+) and may support ECC RAM for error correction.

**Form factor:** Server motherboards are designed to fit into **19-inch rack enclosures** — the industry standard for data center and server room equipment. This uses the full ATX form factor.

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| Intel vs. AMD | Both are x86-compatible but not interchangeable — different socket types |
| Socket compatibility | CPU must match the motherboard socket — AMD boards ≠ Intel boards |
| Performance generalization | Intel/AMD leadership changes frequently; compare current specs |
| CPU installation | No force required; align, drop in, close retention cover |
| Server motherboard | Often multisocket (2 CPUs), more memory slots, more expansion |
| Server form factor | Full ATX; designed for 19-inch rack mounting |
| ECC RAM on servers | Common on server boards for error detection and correction |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Section 3.5 — Hardware Domain**, covering Intel vs. AMD motherboard compatibility and server motherboard specifications.
