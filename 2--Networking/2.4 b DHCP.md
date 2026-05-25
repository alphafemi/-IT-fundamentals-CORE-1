# CompTIA A+ 220-1201 — DHCP (Dynamic Host Configuration Protocol)

> **Exam Domain Reference** | Core 1 (220-1201) — Networking (Domain 2)  
> Topics: DHCP DORA process, DHCP scope, IP pools, exclusions, reservations, static DHCP assignment

---


---

## Overview

DHCP (Dynamic Host Configuration Protocol) was created in **1997** to automatically assign IP configuration to network devices — eliminating the need for manual static configuration on every device.

**Without DHCP**, an administrator would need to manually configure on each device:
- IP address
- Subnet mask
- Default gateway
- DNS server(s)
- Any other IP parameters

With hundreds or thousands of devices on a modern network, manual configuration is impractical. DHCP handles this automatically behind the scenes every time a device connects.

---

## The DORA Process

Every time a device connects to a network and needs an IP address, it goes through a four-step process known as **DORA**:

| Step | Name | Who Sends | Description |
|---|---|---|---|
| **D** | **Discover** | Client → Network (broadcast) | Client announces itself and looks for available DHCP servers |
| **O** | **Offer** | DHCP Server → Network (broadcast) | Server offers an available IP address to the client |
| **R** | **Request** | Client → Network (broadcast) | Client accepts one offer and formally requests that IP address |
| **A** | **Acknowledge** | DHCP Server → Network (broadcast) | Server confirms the assignment; IP is now leased to the client |

### Step-by-Step Example

**Scenario:** Sam's laptop has just turned on with no IP address.

```
Sam's Laptop (0.0.0.0)          DHCP Server (10.10.10.99)
        │                                  │
  1. DISCOVER ──── broadcast ──────────────►
     (from 0.0.0.0:68 to 255.255.255.255:67)
        │                                  │
        ◄──── broadcast ──── 2. OFFER ──────
     (from 10.10.10.99:67 to 255.255.255.255:68)
        │                                  │
  3. REQUEST ───── broadcast ──────────────►
     (from 0.0.0.0:68 to 255.255.255.255:67)
        │                                  │
        ◄──── broadcast ──── 4. ACK ────────
     (from 10.10.10.99:67 to 255.255.255.255:68)
        │
   Sam is assigned 10.10.10.42
```

> **Why broadcasts?** Until the ACK is received, the client has no IP address and cannot send or receive unicast traffic. All four steps use broadcasts so every device on the subnet sees them.

> **Exam Tip:** The entire DORA process uses **UDP port 67** (server) and **UDP port 68** (client). The client sends from `0.0.0.0` until the lease is confirmed.

If multiple DHCP servers exist on the network, the client receives multiple offers in step 2 and selects one. The request in step 3 tells all DHCP servers which offer was accepted — the others retract their offers.

---

## DHCP Scope

A **DHCP scope** is the predefined configuration on the DHCP server that defines what IP information will be assigned to clients on a given subnet.

### IP Address Pools

The pool is the range of IP addresses the DHCP server can hand out.

**Example pools:**
```
192.168.1.0/24
192.168.2.0/24
192.168.3.0/24
```

When a client connects from a given subnet, the DHCP server pulls an available address from the matching pool. Pools do not need to be a single contiguous range — multiple sections can be combined.

### Exclusions

**Excluded addresses** are IPs within the pool range that the DHCP server will **never assign** dynamically.

Use exclusions for:
- Routers and switches with static IPs
- Servers with manually configured addresses
- Printers or other infrastructure devices

Exclusions prevent IP conflicts between dynamically assigned addresses and devices that already have static IPs in that range.

### Scope Options

Beyond IP addresses, a DHCP scope can distribute additional configuration:

| Option | Description |
|---|---|
| Subnet mask | Network mask for the assigned IP |
| Default gateway | Router address for traffic leaving the subnet |
| DNS servers | IP address(es) of DNS servers |
| Lease duration | How long the IP assignment is valid |
| VoIP server | IP of voice server (if applicable) |
| Other options | Any additional IP configuration parameters |

---

## DHCP Reservations

A **DHCP reservation** (also called a **static DHCP assignment** or **IP reservation**) binds a specific IP address to a specific device using its **MAC address**.

**How it works:**
- The DHCP server is configured with a MAC address → IP address mapping
- Every time that device connects, it always receives the same IP address
- The device still goes through the full DORA process — it just always gets the same result

**Why use reservations instead of static IPs on the device?**
- All assignments are managed **centrally** from the DHCP server
- If the IP scheme changes, only the DHCP server needs updating — not every individual device

**Common uses for reservations:**
- File servers
- Web servers
- Printers
- Routers and switches
- Any device that should always be reachable at the same address

### Example Reservation Configuration

| Device Name | MAC Address | Reserved IP |
|---|---|---|
| Prometheus | `AA:BB:CC:DD:EE:01` | 192.168.1.6 |
| Odyssey | `AA:BB:CC:DD:EE:02` | 192.168.1.9 |

All other devices connecting to the network receive any available address from the pool (e.g., `192.168.1.2` – `192.168.1.254`, excluding `.6` and `.9`).

---

## DORA Packet Details

| Step | Source IP | Source Port | Destination IP | Destination Port |
|---|---|---|---|---|
| Discover | `0.0.0.0` | UDP 68 | `255.255.255.255` | UDP 67 |
| Offer | DHCP Server IP | UDP 67 | `255.255.255.255` | UDP 68 |
| Request | `0.0.0.0` | UDP 68 | `255.255.255.255` | UDP 67 |
| Acknowledge | DHCP Server IP | UDP 67 | `255.255.255.255` | UDP 68 |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| DHCP | Automatically assigns IP configuration; created in 1997 |
| DORA | Discover → Offer → Request → Acknowledge |
| Discover | Client broadcast from `0.0.0.0`; finds DHCP servers |
| Offer | DHCP server proposes an available IP address |
| Request | Client accepts one offer; broadcast so all servers see the choice |
| Acknowledge | Server confirms assignment; IP lease begins |
| DHCP ports | Client: UDP 68 / Server: UDP 67 |
| DHCP scope | Predefined pool of IPs and configuration options for a subnet |
| Exclusions | IPs in the pool range that will never be dynamically assigned |
| Reservation | MAC address → fixed IP mapping; device always gets the same IP |
| Static DHCP | Another name for a DHCP reservation |
| Lease | Temporary IP assignment; client must renew before it expires |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Domain 2 — Networking**, covering DHCP operation, the DORA process, scope configuration, and IP reservations.
