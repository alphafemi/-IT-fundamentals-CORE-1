# CompTIA A+ 220-1201 — Computer Power

> **Exam Domain Reference** | Core 1 (220-1201) — Hardware (Domain 3)  
> Topics: AC vs. DC, amps/volts/watts, PSU voltages, 24-pin connector, modular PSUs, redundant PSUs, 80 PLUS efficiency ratings

> ⚠️ **Safety first:** Always disconnect from the power source before working inside a computer. Capacitors inside can hold charge even after unplugging. Never connect yourself to a building's electrical system — even the ground wire can be energized.

---



## AC vs. DC Power

| Type | Full Name | Description | Source |
|---|---|---|---|
| **AC** | Alternating Current | Current constantly reverses direction; shown as a wave | Wall outlets, power grid |
| **DC** | Direct Current | Current flows in one direction at constant voltage; shown as a flat line | Batteries, PSU output |

Motherboards and all computer components run on **DC power**. The **power supply unit (PSU)** converts AC from the wall outlet to the DC voltages the system needs.

**Regional AC standards:**

| Region | Voltage | Frequency |
|---|---|---|
| US / Canada | 110–120V AC | 60 Hz |
| Europe | 220–240V AC | 50 Hz |

**Manual vs. auto-switching PSUs:**
- Older PSUs have a manual voltage switch on the back (120V / 230V) — must be set correctly before plugging in
- Modern PSUs are auto-switching — detect input voltage automatically
- **Warning:** Connecting a PSU set for 120V to a 230V outlet will likely destroy the PSU

---

## Electrical Fundamentals

| Term | Abbreviation | Analogy (water hose) | Definition |
|---|---|---|---|
| **Ampere** | A (amp) | Volume of water flowing | Number of electrons passing a point per second |
| **Voltage** | V (volt) | Water pressure | Electrical potential / pressure |
| **Wattage** | W (watt) | Total power delivered | Real power consumption |

**Wattage formula:**
```
Watts = Volts × Amps
```

**Example:** 120V × 0.5A = **60W**

---

## PSU Voltages — Input & Output

A PSU outputs multiple DC voltages for different components:

| Voltage | Use |
|---|---|
| **+12V** | PCIe adapter cards, hard drives, most high-power components |
| **+5V** | Some older motherboard components |
| **+3.3V** | Modern motherboard components, M.2 slots, RAM |
| **+5V SB** | Standby power — keeps motherboard awake for Wake-on-LAN and power button |
| **−12V** | Integrated LAN, some older PCI cards |
| **−5V** | Legacy — older adapter cards; rarely seen on modern PSUs |

> **Exam Tip:** +5V SB (standby) is what allows a computer to wake from sleep via a network signal or front-panel power button.

---

## The 24-Pin Main Power Connector

The main power connector delivers **+3.3V, +5V, and +12V** to the motherboard.

- **Modern standard:** 24-pin
- **Legacy:** 20-pin (older motherboards)
- **Compatibility:** A 24-pin connector can be used on a 20-pin motherboard — the extra 4 pins are unused
- **Keyed:** Can only be inserted one way; a locking latch secures it

---

## Modular vs. Fixed PSUs

| Type | Description | Advantage | Disadvantage |
|---|---|---|---|
| **Fixed** | All cables permanently attached | Simpler; lower cost | Unused cables clutter the case |
| **Modular** | Cables plug in as needed | Clean cable management; only use what you need | More expensive |
| **Semi-modular** | Some fixed, some modular | Compromise option | — |

Modular PSUs are preferred for clean builds and improved airflow inside the case.

---

## Redundant Power Supplies (Servers)

Enterprise servers often include **two power supplies** for high availability:

- Each PSU is capable of supporting **100% of the system's power load**
- Under normal operation, each runs at **~50% load**
- If one PSU fails or is disconnected, the other instantly takes the full load
- PSUs are **hot-swappable** — can be removed and replaced while the system is running with zero downtime

---

## Sizing a Power Supply

Calculate the total wattage requirement of all components (CPU, GPU, storage, RAM, fans, etc.) and select a PSU that can handle the load with headroom.

**Rule of thumb:** Choose a PSU rated for **~150% of your expected load** (i.e., your expected load should be ~50-67% of PSU capacity). This:
- Prevents overloading
- Improves efficiency (PSUs run most efficiently at 50–80% load)
- Leaves room for future upgrades

**Note:** Higher-wattage PSUs are not faster — they just provide more capacity. Physical size remains the same across wattage tiers.

---

## 80 PLUS Efficiency Ratings

When AC is converted to DC, some energy is lost as heat. The **80 PLUS** certification program rates PSU efficiency.

| Rating | Min. Efficiency |
|---|---|
| **80 PLUS** (no tier) | 80% |
| **80 PLUS Bronze** | ~82–85% |
| **80 PLUS Silver** | ~85–88% |
| **80 PLUS Gold** | ~87–90% |
| **80 PLUS Platinum** | ~90–94% |
| **80 PLUS Titanium** | ~92–96% |

**Higher efficiency = less heat generated = lower electricity cost = better for cooling**

> **Exam Tip:** 80 PLUS Titanium is the most efficient; plain 80 PLUS is the least. Higher efficiency costs more upfront but saves money over time through lower power consumption and reduced cooling needs.

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| AC | Alternating Current; from wall outlet; 120V/60Hz (US) or 230V/50Hz (EU) |
| DC | Direct Current; required by computer components; produced by PSU |
| PSU | Converts AC → DC; outputs +3.3V, +5V, +12V, and others |
| Watts formula | Volts × Amps = Watts |
| +5V SB | Standby power; enables wake-on-LAN and power button response |
| 24-pin connector | Modern main power; delivers 3.3V/5V/12V to motherboard |
| 20→24-pin compat | 24-pin connector fits 20-pin motherboard; 4 pins unused |
| Manual PSU switch | Must be set to correct voltage before plugging in; wrong setting = failure |
| Modular PSU | Only connect cables needed; cleaner build |
| Redundant PSU | Two PSUs at 50% load each; hot-swappable; zero downtime on failure |
| PSU sizing rule | PSU wattage ≈ 150% of expected load |
| 80 PLUS | Efficiency rating; Titanium is highest; plain 80 PLUS is lowest |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Hardware Domain**, covering power supply operation, AC/DC concepts, PSU voltages, connectors, modular designs, redundancy, sizing, and efficiency ratings.
