# CompTIA A+ 220-1201 — VLANs & VPNs

> **Exam Domain Reference** | Core 1 (220-1201) — Networking (Domain 2)  
> Topics: LAN, broadcast domain, VLAN, inter-VLAN routing, VPN, concentrator, client-to-site VPN, site-to-site VPN

---



---

## LANs & Broadcast Domains

A **LAN (Local Area Network)** is a group of devices connected together within a single **broadcast domain** — meaning a broadcast sent by one device is received by all other devices on that same network segment.

**Key property:** Broadcast domains are isolated from each other. A broadcast sent on the red network is never seen by devices on the blue network.

```
Red Switch                     Blue Switch
┌─────────────┐               ┌─────────────┐
│  Device A   │               │  Device C   │
│  Device B   │               │  Device D   │
└─────────────┘               └─────────────┘
  Broadcast domain 1            Broadcast domain 2
```

**Problem:** Two separate 24-port switches with only 2 devices each wastes hardware, space, and power.

---

## VLANs — Virtual Local Area Networks

### Why VLANs Exist

VLANs allow a single physical switch to host **multiple logical broadcast domains simultaneously** — combining the efficiency of one switch with the separation of many.

### How VLANs Work

Each **port** on a VLAN-capable switch is assigned to a VLAN. Ports in the same VLAN share a broadcast domain; ports in different VLANs are isolated from each other — just as if they were on separate physical switches.

```
Single Physical Switch (24 ports)
┌─────────────────────────────────────────┐
│  Port 1  │ VLAN 1 (Gate Room)           │
│  Port 2  │ VLAN 1 (Gate Room)           │
│  Port 3  │ VLAN 2 (Dining Room)         │
│  Port 4  │ VLAN 2 (Dining Room)         │
│  Port 5  │ VLAN 3 (Infirmary)           │
│  Port 6  │ VLAN 3 (Infirmary)           │
└─────────────────────────────────────────┘
```

- A broadcast from a VLAN 1 device is **only seen by other VLAN 1 devices**
- VLAN 2 and VLAN 3 devices are completely unaware of it
- One switch, one power source, one rack unit — multiple isolated networks

**Benefits of VLANs:**
- Efficient use of switch hardware
- Logical separation for security and organization
- Reduces broadcast traffic across the network
- Segments sensitive systems (e.g., finance, HR, guest Wi-Fi) without extra hardware

### Inter-VLAN Routing

Devices on different VLANs **cannot communicate directly** — they are in separate broadcast domains. To allow communication between VLANs, a **router** is required.

Options:
- **External router** — a dedicated router connected to the switch handles routing between VLANs
- **Layer 3 switch** — some switches have built-in routing capability and can route between VLANs internally

---

## VPNs — Virtual Private Networks

A **VPN (Virtual Private Network)** creates an **encrypted tunnel** over an untrusted network (like the internet), protecting all data transmitted between endpoints.

If someone intercepts VPN traffic, the captured data is unreadable — it appears as encrypted ciphertext.

### VPN Concentrator

The **concentrator** is the device responsible for encrypting and decrypting VPN traffic.

- Typically built into a **firewall** or a dedicated VPN appliance
- Can also be implemented as **software** running on an existing server
- Most operating systems include built-in VPN client software
- Third-party VPN clients are also available

### Client-to-Site VPN

Used when **remote users** (e.g., employees working from home) need secure access to a corporate network.

```
Remote User (Home)                    Corporate Network
┌──────────────┐     Encrypted       ┌───────────────────┐
│  VPN Client  │◄───── Internet ─────►│  VPN Concentrator │── Internal Resources
└──────────────┘      Tunnel          └───────────────────┘
```

**How it works:**
- The user's VPN client connects to the corporate concentrator over the internet
- All traffic between the user and the concentrator is encrypted
- The concentrator decrypts traffic and forwards it to internal resources
- Can be configured as **always-on** — automatically connects when the device boots and has internet access, with no manual intervention required

### Site-to-Site VPN

Used when **two physical office locations** need to communicate securely over the internet.

```
Corporate HQ                               Remote Office
┌─────────────────────┐                   ┌─────────────────────┐
│ Internal Network    │                   │ Internal Network    │
│ (unencrypted)       │                   │ (unencrypted)       │
│  ┌──────────────┐   │   Encrypted       │   ┌──────────────┐  │
│  │   Firewall / │◄──┼── Internet ───────┼──►│   Firewall / │  │
│  │ Concentrator │   │    Tunnel         │   │ Concentrator │  │
│  └──────────────┘   │                   │   └──────────────┘  │
└─────────────────────┘                   └─────────────────────┘
```

**How it works:**
- Each site has a **firewall acting as a VPN concentrator**
- Traffic within each office travels in the clear (unencrypted) on the internal network
- Any traffic crossing the internet between sites is **automatically encrypted** by the firewalls
- End users at each site have no awareness of the VPN — it is transparent

---

## VLAN vs. VPN Comparison

| Feature | VLAN | VPN |
|---|---|---|
| Purpose | Logical network segmentation | Encrypted communication over untrusted networks |
| Where it operates | Within a single physical switch or campus | Across the internet or WAN |
| Encryption | No | Yes |
| Requires router to communicate between segments | Yes (inter-VLAN routing) | N/A |
| Key device | Managed switch | VPN concentrator / firewall |
| Use case | Separating departments on one switch | Remote workers, connecting branch offices |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| LAN | Single broadcast domain; broadcasts seen by all devices in the segment |
| Broadcast domain | Isolated segment; broadcasts do not cross into other domains |
| VLAN | Logical separation on one physical switch; each VLAN = separate broadcast domain |
| Inter-VLAN routing | Requires a router or Layer 3 switch for VLANs to communicate |
| VPN | Encrypted tunnel over an untrusted network |
| Concentrator | Device that encrypts/decrypts VPN traffic; built into firewall or standalone |
| Client-to-site VPN | Remote user → corporate network; used for work-from-home |
| Always-on VPN | Automatically connects at login; no manual start needed |
| Site-to-site VPN | Office → office; firewalls act as concentrators; transparent to users |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Domain 2 — Networking**, covering virtual network segmentation (VLANs) and secure remote connectivity (VPNs).
