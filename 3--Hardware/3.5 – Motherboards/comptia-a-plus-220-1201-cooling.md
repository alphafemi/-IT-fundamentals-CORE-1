# CompTIA A+ 220-1201 — Cooling Systems

> **Exam Domain Reference** | Core 1 (220-1201) — Hardware (Domain 3)  
> Topics: Case fans, passive cooling, heat sinks, thermal paste, thermal pads, liquid cooling

---

## Table of Contents

1. [Why Cooling Matters](#why-cooling-matters)
2. [Active Cooling — Fans](#active-cooling--fans)
3. [Passive Cooling](#passive-cooling)
4. [Heat Sinks](#heat-sinks)
5. [Thermal Interface Materials](#thermal-interface-materials)
   - [Thermal Paste](#thermal-paste)
   - [Thermal Pads](#thermal-pads)
6. [Liquid Cooling](#liquid-cooling)
7. [Cooling Method Comparison](#cooling-method-comparison)
8. [Key Takeaways](#key-takeaways)

---

## Why Cooling Matters

All computing components generate heat as a by-product of operation. Without proper cooling, heat builds up and causes:
- Thermal throttling (CPU/GPU slows down to reduce heat)
- System instability and crashes
- Permanent hardware damage

Effective cooling keeps components within safe operating temperatures for reliability and performance.

---

## Active Cooling — Fans

**Airflow principle:** Cool air enters one side of the case → passes over hot components → heated air exits the other side.

**Good airflow practice:**
- Route cables out of the airflow path
- Ensure unobstructed front intake and rear/top exhaust
- Check that all components are positioned to allow air movement

**Common case fan sizes:**

| Size | Use |
|---|---|
| 80 mm | Smaller cases, rear exhaust |
| 120 mm | Most common; good balance of airflow and noise |
| 200 mm | Large cases; moves more air at lower RPM (quieter) |

**Variable speed fans:** Most modern fans are temperature-controlled — they spin slowly (quietly) when the system is cool and ramp up as temperatures rise.

**On-card fans:** High-end graphics cards and other power-hungry adapter cards often include their own dedicated fans on the card itself.

---

## Passive Cooling

**Passive cooling** uses no fans — heat is dissipated through surface area and natural convection, with no moving parts and no noise.

**Best for:**
- Media servers and set-top boxes (quiet environment)
- Purpose-built appliances
- Situations where component heat output is low and manageable

Passive cooling is always used in conjunction with a **heat sink** to spread heat over a large surface area.

---

## Heat Sinks

A **heat sink** is a metal component (usually aluminum or copper) that draws heat away from a component and distributes it across many fins, maximizing the surface area for heat dissipation.

**How it works:**
1. Heat conducts from the hot component into the heat sink base
2. Heat spreads across the fins
3. Air passing through the fins carries the heat away

> **Safety warning:** Heat sinks get extremely hot during operation. Never touch one on a running system — burns are possible.

Heat sinks are used on CPUs, GPUs, voltage regulators, and other high-heat components.

---

## Thermal Interface Materials

A thermal interface material fills the microscopic gaps between a component's surface and the heat sink, ensuring maximum heat transfer. Two main types:

### Thermal Paste

- **Also called:** Thermal grease, conductive grease, thermal compound
- **Application:** A pea-sized amount applied to the center of the component — it spreads out when the heat sink is pressed down
- **Performance:** Best thermal conductivity of common interface materials
- **Reusability:** Not reusable — clean off old paste and apply fresh paste whenever a heat sink is removed and reinstalled

### Thermal Pads

- **Form:** Pre-cut solid pad placed between the component and heat sink
- **Performance:** Slightly less effective than thermal paste
- **Advantage:** Less messy; no risk of paste spreading onto nearby components
- **Reusability:** Not reusable — replace when heat sink is removed

**Typical CPU cooling stack (bottom to top):**
```
CPU → Thermal paste or pad → Heat sink → (optional) Fan on top of heat sink
```

For larger coolers, the fan may be positioned sideways, blowing air through the heat sink fins horizontally.

---

## Liquid Cooling

Liquid cooling circulates coolant through a closed loop to transfer heat away from hot components more efficiently than air alone.

**Common use cases:**
- High-end gaming systems
- Overclocked processors (pushing CPUs beyond factory speed limits)
- Workstations with extreme heat output

**How it works:**
1. A **water block / cold plate** sits on top of the CPU (or GPU), absorbing heat into the coolant
2. Coolant flows through **tubes** to a **radiator**
3. **Fans on the radiator** cool the coolant by blowing air through the radiator fins
4. Cooled coolant returns to the water block to repeat the cycle

**Advantages over air cooling:**
- More efficient heat removal
- Can maintain lower temperatures under sustained heavy load
- Fans run slower (quieter) because the radiator is more efficient than a CPU heatsink fan

---

## Cooling Method Comparison

| Method | Moving Parts | Noise | Effectiveness | Best For |
|---|---|---|---|---|
| Case fans | Yes | Moderate | Good | General airflow in most systems |
| On-card fans | Yes | Moderate | Good (localized) | GPUs, high-heat adapter cards |
| Passive (heat sink only) | No | None | Limited | Low-heat appliances, set-top boxes |
| Air (heat sink + fan) | Yes | Low–moderate | Good | Most desktops and laptops |
| Liquid cooling | Yes (pump + fan) | Low | Excellent | High-end gaming, overclocking |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| Case fans | 80 / 120 / 200 mm; variable speed; cool air in, hot air out |
| Airflow | Clear cable paths; unobstructed front intake and rear/top exhaust |
| Passive cooling | No fans; no noise; uses heat sink + convection; for low-heat appliances |
| Heat sink | Metal fins increase surface area; conducts heat from component to air |
| Heat sink safety | Gets very hot — do not touch on a running system |
| Thermal paste | Also called thermal grease; pea-sized application; best conductivity; not reusable |
| Thermal pad | Pre-cut solid pad; less messy than paste; slightly less effective; not reusable |
| Thermal interface | Required between component and heat sink — both paste and pad are not reusable |
| Liquid cooling | Closed loop: cold plate → tubes → radiator → fans → back to cold plate |
| Liquid cooling use | High-end gaming; overclocking; sustained heavy workloads |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Hardware Domain**, covering cooling solutions including fans, passive cooling, heat sinks, thermal interface materials, and liquid cooling systems.
