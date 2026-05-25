# CompTIA A+ 220-1201 — Introduction to IP, TCP, UDP & Ports

> **Exam Domain Reference** | Core 1 (220-1201) — Networking (Domain 2 Primer)  
> Topics: IP, TCP, UDP, encapsulation, port numbers, ephemeral ports, well-known ports

> **Note:** This topic is not directly tied to a specific exam objective but serves as a foundational primer for all networking topics in Domain 2. If you are unfamiliar with IP basics, review this before moving on to other networking sections.

---


---

## Overview — The Network as a Road

Think of networking in these terms:

| Analogy | Networking Concept |
|---|---|
| The road | The physical network (Ethernet, Wi-Fi, DSL, etc.) |
| The truck | **IP (Internet Protocol)** — carries the data |
| The boxes on the truck | **TCP or UDP** — the transport containers |
| Contents of the boxes | Application data (HTTP, email, voice, etc.) |
| Street address | **IP address** — identifies where data is going |
| Room in the house | **Port number** — identifies which service receives the data |

IP does not care what type of network is underneath it. Whether the data travels over Ethernet, Wi-Fi, or DSL, IP handles the addressing and delivery.

---

## Encapsulation

Data sent across a network is nested in layers — this is called **encapsulation**. Each layer adds its own header (and sometimes trailer) to the data.

**Example — Client sending a web request to a server:**

```
[ Ethernet Header ] [ Ethernet Payload                              ] [ Ethernet Trailer ]
                    [ IP Header ] [ IP Payload                      ]
                                  [ TCP Header ] [ TCP Payload      ]
                                                 [ HTTP Data        ]
```

- The **Ethernet frame** carries everything across the physical network
- Inside is an **IP packet** with source/destination addresses
- Inside IP is a **TCP segment** managing the reliable delivery
- Inside TCP is the **HTTP data** — the actual web content

On the receiving end, each layer is unwrapped in reverse — this is called **decapsulation**.

---

## TCP — Transmission Control Protocol

TCP is a **connection-oriented** protocol — it establishes a formal session before sending data and formally closes it when done.

**Phone call analogy:**
- You dial → phone rings → other person says hello → you say hello → conversation happens → both say goodbye → hang up
- TCP mirrors this: formal **connection setup**, data exchange with **acknowledgments**, formal **connection teardown**

**Key TCP characteristics:**

| Feature | Description |
|---|---|
| Connection-oriented | Formal setup and teardown (handshake) |
| Reliable delivery | Acknowledgments confirm data was received |
| Error recovery | Lost or corrupt data is automatically retransmitted |
| Flow control | Receiver can tell sender to speed up or slow down |

**Common applications that use TCP:**
- **HTTPS** — secure web browsing
- **SSH** — secure remote terminal access
- **Email protocols** (IMAP, SMTP)

---

## UDP — User Datagram Protocol

UDP is a **connectionless** protocol — it sends data without setting up a session or confirming delivery.

**Key UDP characteristics:**

| Feature | Description |
|---|---|
| Connectionless | No formal setup or teardown |
| Unreliable delivery | No acknowledgments; sender does not know if data arrived |
| No error recovery | Lost data is not retransmitted by UDP |
| No flow control | Receiver cannot signal sender to slow down |
| Low overhead | Faster than TCP; less processing required |

**Why use UDP?** For **real-time applications**, lost data cannot be replayed. It's better to keep moving than to pause and retransmit.

**Common applications that use UDP:**
- **VoIP** — voice over IP calls
- **Video streaming** — real-time video
- **DHCP** — Dynamic Host Configuration Protocol (IP address assignment)
- **TFTP** — Trivial File Transfer Protocol (small file transfers)

> **Exam Tip:** Some UDP-based applications handle their own error checking at the application layer instead of relying on UDP. For example, if a DHCP request gets no response, the application simply tries again.

---

## TCP vs. UDP Comparison

| Feature | TCP | UDP |
|---|---|---|
| Connection type | Connection-oriented | Connectionless |
| Reliability | Reliable (acknowledgments) | Unreliable (best effort) |
| Error recovery | Yes — retransmits lost data | No |
| Flow control | Yes | No |
| Overhead | Higher | Lower |
| Speed | Slower (due to overhead) | Faster |
| Use cases | Web (HTTPS), SSH, email | VoIP, video, DHCP, TFTP |

---

## IP Addresses

Every device on a network has an **IP address** — a unique identifier, like a house's street address.

- **Source IP address** — where the data is coming from
- **Destination IP address** — where the data is going

When a client communicates with a server, both addresses are included in every IP packet so responses can be routed back correctly.

---

## Port Numbers

IP addresses identify *which device* to send data to. **Port numbers** identify *which service* on that device should handle the data.

```
Server IP: 10.0.0.2
├── TCP Port 80    → Web server (HTTP)
├── TCP Port 143   → Email server (IMAP)
└── UDP Port 5004  → VoIP server
```

Every communication flow requires:
1. **Source IP address** (client)
2. **Destination IP address** (server)
3. **Protocol** (TCP or UDP)
4. **Source port** (client's ephemeral port)
5. **Destination port** (server's well-known port)

### Well-Known (Non-Ephemeral) Ports

- Range: **0 – 1,023** (though any consistent port can serve this role)
- Assigned to specific services; rarely change
- Also called **permanent ports**

| Port | Protocol | Service |
|---|---|---|
| 80 | TCP | HTTP (web) |
| 443 | TCP | HTTPS (secure web) |
| 143 | TCP | IMAP (email) |
| 22 | TCP | SSH (secure shell) |
| 5004 | UDP | RTP / VoIP |
| 67/68 | UDP | DHCP |
| 69 | UDP | TFTP |

### Ephemeral (Client) Ports

- Range: **1,024 – 65,535**
- Randomly chosen by the client for each new connection
- Temporary — closed when the session ends; a new random port is chosen next time
- Allow a single client to maintain multiple simultaneous connections to the same server

> **Important:** TCP port 80 and UDP port 80 are **not the same**. Port numbers are unique per protocol. The same number in TCP and UDP are treated as completely separate ports.

---

## Putting It All Together

Here is an example of a client (10.0.0.1) simultaneously communicating with a server (10.0.0.2) on three different services:

| Traffic Flow | Source IP | Source Port | Destination IP | Destination Port | Protocol |
|---|---|---|---|---|---|
| Web (HTTP) | 10.0.0.1 | 51,200 (ephemeral) | 10.0.0.2 | 80 | TCP |
| VoIP | 10.0.0.1 | 49,876 (ephemeral) | 10.0.0.2 | 5,004 | UDP |
| Email (IMAP) | 10.0.0.1 | 52,341 (ephemeral) | 10.0.0.2 | 143 | TCP |

Each flow uses a **different random source port** (ephemeral) but the **same well-known destination port** for each service. This is how a single device can run multiple network conversations at the same time — called **multiplexing**.

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| IP | The Internet Protocol; handles addressing and routing; works over any network type |
| Encapsulation | Data is nested in layers (HTTP inside TCP inside IP inside Ethernet) |
| TCP | Connection-oriented; reliable; uses acknowledgments and retransmission |
| UDP | Connectionless; unreliable; low overhead; used for real-time traffic |
| IP address | Identifies which device on the network |
| Port number | Identifies which service on that device |
| Well-known ports | 0–1,023; assigned to specific services (e.g., HTTP = 80) |
| Ephemeral ports | 1,024–65,535; randomly assigned to clients; temporary |
| Multiplexing | Multiple simultaneous connections using different port numbers |
| TCP ≠ UDP ports | TCP port 80 and UDP port 80 are separate and distinct |

---

> 📚 **Study Resource:** This document serves as a foundational primer for **CompTIA A+ Core 1 (220-1201) Domain 2 — Networking**. Understanding IP, TCP, UDP, and ports is essential before studying specific networking protocols and services.
