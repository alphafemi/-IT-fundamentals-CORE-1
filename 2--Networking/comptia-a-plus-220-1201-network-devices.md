# CompTIA A+ 220-1201 — Network Devices & Infrastructure

> **Exam Domain Reference** | Core 1 (220-1201) — Networking (Domain 2)  
> Topics: Routers, switches (managed/unmanaged), access points, patch panels, firewalls, PoE, cable modems, DSL, fiber/ONT, NICs

---

## Table of Contents

1. [Overview](#overview)
2. [Core Network Devices](#core-network-devices)
   - [Router](#router)
   - [Switch](#switch)
   - [Unmanaged vs. Managed Switches](#unmanaged-vs-managed-switches)
   - [Wireless Access Point (AP)](#wireless-access-point-ap)
   - [Firewall](#firewall)
3. [Physical Infrastructure](#physical-infrastructure)
   - [Patch Panel](#patch-panel)
   - [Network Interface Card (NIC)](#network-interface-card-nic)
4. [Power over Ethernet (PoE)](#power-over-ethernet-poe)
5. [Internet Connection Types](#internet-connection-types)
   - [Cable Modem (DOCSIS)](#cable-modem-docsis)
   - [DSL — Digital Subscriber Line](#dsl--digital-subscriber-line)
   - [Fiber / ONT](#fiber--ont)
6. [Device Summary Table](#device-summary-table)
7. [Key Takeaways](#key-takeaways)

---

## Overview

Modern networks are built from a combination of specialized devices, each performing a distinct function. In homes and small offices, several of these functions are often combined into one device (e.g., a wireless router that includes routing, switching, Wi-Fi, and a firewall). In enterprise environments, each function is typically handled by a dedicated device for performance, scalability, and manageability.

---

## Core Network Devices

### Router

Routers forward traffic **between IP subnets** based on the **destination IP address**.

- Maintains a **routing table** that maps destination networks to outbound interfaces
- Operates at **OSI Layer 3**
- Connects different network types: Ethernet ↔ wireless, copper ↔ fiber, LAN ↔ WAN
- Often combined with switching in a **Layer 3 switch** (multilayer switch)

### Switch

Switches connect end devices on a local network and forward traffic based on the **destination MAC address**.

- Operates at **OSI Layer 2** (standard switch) or **Layer 3** (with routing capability)
- Uses **ASIC (Application-Specific Integrated Circuit)** hardware for high-speed forwarding
- Common sizes: **24-port** or **48-port** for workgroup use; hundreds of ports in core/distribution switches
- May include **PoE** (Power over Ethernet) to power phones, APs, and cameras over the same cable

### Unmanaged vs. Managed Switches

| Feature | Unmanaged Switch | Managed Switch |
|---|---|---|
| Configuration | None — plug and play | Full configuration via CLI or web UI |
| VLANs | No | Yes |
| Traffic prioritization (QoS) | No | Yes |
| SNMP / remote management | No | Yes |
| Port mirroring | No | Yes |
| Redundancy support | No | Yes |
| Log storage | No | Yes |
| Price | Lower | Higher |
| Best for | Home / small office | Enterprise networks |

> **Port Mirroring:** Copies traffic from one port to another for analysis by a protocol analyzer or security monitoring tool — only available on managed switches.

### Wireless Access Point (AP)

An access point bridges a **wireless network** to a **wired network** — it does not route.

- Operates like a switch: makes forwarding decisions based on **MAC address**
- **No IP routing** occurs at the AP — it is a bridge between wireless and wired segments
- Corporate APs are dedicated devices separate from routers
- Often powered by **PoE** (no separate power outlet needed at ceiling mount location)

> **Exam Tip:** An AP bridges wireless ↔ wired. A wireless router combines an AP + router + switch + firewall into one device. Know the difference.

### Firewall

Firewalls control which traffic is allowed or blocked on a network.

| Type | How It Decides |
|---|---|
| **Traditional firewall** | Allows/blocks based on TCP/UDP **port numbers** |
| **Next-generation firewall (NGFW)** | Allows/blocks based on **application** identity, not just port |

**Additional firewall capabilities:**
- **VPN concentrator** — site-to-site and client-to-site VPN termination
- **Proxy** — sits between client and server, inspecting responses before forwarding
- **Router** — routes between IP subnets while enforcing security policies
- Multi-interface support — can connect many network segments simultaneously

---

## Physical Infrastructure

### Patch Panel

A patch panel provides **organized, permanent termination** for Ethernet runs between desks and the network closet.

```
Desk 9 ──────────────── Closet ──► [Patch Panel] ──short cable──► Switch Port
Desk 10 ─────────────── Closet ──► [Patch Panel] ──short cable──► Switch Port
Desk 11 ─────────────── Closet ──► [Patch Panel] ──short cable──► Switch Port
```

**How it works:**
- Ethernet cables are run permanently from each desk to the network closet
- The closet end is **punched down** onto the back of the patch panel
- The front of the patch panel has **RJ45 ports** — short patch cables connect these to switch interfaces
- To move a device to a different switch or VLAN, only the **short patch cable** in the closet changes — the long permanent run stays in place

**Benefits:**
- Easy reconfiguration without touching long cable runs
- Clean, labeled cable management
- Faulty short patch cables are easy and cheap to replace

### Network Interface Card (NIC)

A NIC connects a device to the Ethernet network.

- Built into most modern motherboards (laptops, desktops, servers)
- Available as **expansion cards** to add or extend Ethernet interfaces
- Each interface has a unique **MAC address** for Layer 2 identification
- Available in many speeds: 100 Mbps, 1 Gbps (copper), 10 Gbps, fiber

---

## Power over Ethernet (PoE)

PoE delivers **both data and electrical power** over a standard Ethernet cable — eliminating the need for a separate power outlet at the device location.

**Common PoE-powered devices:**
- IP desk phones
- Wireless access points
- IP cameras (including PTZ — pan, tilt, zoom)
- Laptops (PoE++)

### PoE Standards

| Standard | Max Power | Max Current | Common Use |
|---|---|---|---|
| **PoE** (802.3af) | 15.4W | 350 mA | Phones, basic APs |
| **PoE+** (802.3at) | 25.5W | 600 mA | PTZ cameras, higher-power APs |
| **PoE++** (802.3bt) | 51W or 71.3W | 600–960 mA | Laptops, high-power devices |

> **Compatibility:** PoE standards are **downward compatible** (a PoE++ switch can power a PoE device) but **not upward compatible** (a PoE switch cannot power a device that requires PoE++).

### PoE Delivery Methods

| Term | Description |
|---|---|
| **Endspan** | PoE power comes from the switch itself |
| **Midspan / Injector** | An inline injector adds PoE power between a non-PoE switch and the device |

---

## Internet Connection Types

### Cable Modem (DOCSIS)

- Delivers internet over the **coaxial cable** infrastructure used by cable TV providers
- Standard: **DOCSIS** (Data Over Cable Service Interface Specification)
- Provides Ethernet output for connection to a router
- Speeds: commonly **1 Gbps and higher**
- Used in homes and businesses that already have cable TV infrastructure

### DSL — Digital Subscriber Line

- Delivers internet over existing **telephone (copper) lines**
- Runs simultaneously with analog voice — no interference between them
- Typical speeds: **~200 Mbps downstream / ~20 Mbps upstream**
- Speed degrades with distance from the **central office (CO)**
- Maximum effective distance: approximately **10,000 feet** from the CO

> **Key rule:** The closer to the central office, the faster the DSL connection.

### Fiber / ONT

- Delivers internet over **fiber optic cable**
- Requires an **ONT (Optical Network Terminal)** to convert the optical signal to copper/Ethernet

**ONT outputs may include:**
- **RJ45** — Ethernet data connection
- **RJ11** — Voice over IP phone connections
- **F-connector (coax)** — Cable TV / video

**Demarcation point (demarc):**
- The ONT defines the **boundary of responsibility** between the customer and the ISP
- Everything **outside** the building = ISP's responsibility
- Everything **inside** the building = customer's responsibility

---

## Device Summary Table

| Device | Forwarding Basis | OSI Layer | Key Function |
|---|---|---|---|
| Router | IP address | Layer 3 | Route between subnets / networks |
| Switch | MAC address | Layer 2 (or 3) | Connect LAN devices |
| Access Point | MAC address | Layer 2 | Bridge wireless ↔ wired |
| Firewall | Port / Application | Layer 3–7 | Allow/block traffic; VPN; proxy |
| Patch Panel | N/A | Physical | Organized cable termination |
| NIC | MAC address | Layer 2 | Connect device to network |
| Cable Modem | N/A | Physical | Coax → Ethernet (DOCSIS) |
| DSL Modem | N/A | Physical | Phone line → Ethernet |
| ONT | N/A | Physical | Fiber → Ethernet (demarc point) |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| Router | Routes between IP subnets; Layer 3; can connect different network types |
| Switch | Forwards by MAC address; Layer 2; uses ASIC hardware |
| Layer 3 switch | Combined router + switch in one device |
| Unmanaged switch | Plug and play; no VLANs, no SNMP, no management |
| Managed switch | VLANs, QoS, SNMP, port mirroring, redundancy |
| Access point | Bridges wireless ↔ wired; no routing; MAC-based forwarding |
| Firewall | Traditional = port-based; NGFW = application-based |
| Patch panel | Permanent desk-to-closet runs; reconfigure via short patch cables in closet |
| NIC | Unique MAC per interface; built-in or expansion card |
| PoE | 15.4W / 25.5W / 51–71W; endspan (switch) or midspan (injector) |
| Cable modem | DOCSIS; coax; 1 Gbps+ |
| DSL | Telephone lines; up to ~200 Mbps; max ~10,000 ft from CO |
| ONT | Fiber to copper conversion; defines ISP vs. customer demarc |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Domain 2 — Networking**, covering network hardware devices, physical infrastructure, PoE standards, and internet connection types.
