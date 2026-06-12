# CompTIA A+ 220-1201 — Virtualization Services

> **Exam Domain Reference** | Core 1 (220-1201) — Networking & Hardware (Domain 2/3)  
> Topics: Hypervisor types (Type 1 / Type 2), CPU virtualization (VT/AMD-V), VM networking, VM escape, VDI, containerization, Docker

---


---

## The Hypervisor

A **hypervisor** (also called a **Virtual Machine Manager / VMM**) is the software that manages all virtual machines and controls how they interact with the underlying physical hardware.

**What the hypervisor allocates to each VM:**
- CPU cycles
- Memory (RAM)
- Storage
- Network connectivity

---

## Type 1 vs. Type 2 Hypervisors

| Feature | Type 1 (Bare Metal) | Type 2 (Hosted) |
|---|---|---|
| Also called | Bare metal hypervisor | Hosted hypervisor |
| Runs on | Directly on hardware — no host OS | On top of an existing OS |
| Performance | Higher — no host OS overhead | Lower — shares resources with host OS |
| Use case | Enterprise data centers, servers | Personal workstations, development |
| Examples | VMware ESXi, Microsoft Hyper-V | VMware Workstation, Oracle VirtualBox, Parallels Desktop |

**Type 1 architecture:**
```
Hardware → Hypervisor → VMs (each with guest OS)
```

**Type 2 architecture:**
```
Hardware → Host OS (Windows/macOS/Linux) → Hypervisor software → VMs
```

The VMs themselves are identical in both types — the difference is only in how the hypervisor is deployed.

---

## CPU Virtualization Support

Modern CPUs include hardware features specifically designed to improve virtualization performance and stability.

| CPU Vendor | Virtualization Feature |
|---|---|
| **Intel** | VT (Virtualization Technology) / VT-x |
| **AMD** | AMD-V (AMD Virtualization) |

Must be **enabled in BIOS/UEFI** before hypervisors can use these hardware features (see BIOS Settings doc).

---

## VM Resource Requirements

Each VM is a complete, independent operating system with its own resource allocation:

| Resource | Consideration |
|---|---|
| **CPU** | Hypervisor allocates CPU cycles; more VMs = more CPU demand |
| **RAM** | Each VM needs dedicated memory; physical RAM must support all running VMs |
| **Storage** | Each VM contains a full OS + applications + data; significant disk space required |
| **Network** | Each VM gets its own virtual network interface |

---

## VM Networking Modes

The hypervisor controls how VMs communicate with the outside world:

| Mode | Description |
|---|---|
| **NAT (Shared)** | VM uses a separate internal subnet; hypervisor performs NAT to reach the physical network |
| **Bridged** | VM appears as a normal device on the local network; gets an IP from the same subnet; no NAT |
| **Private / Host-only** | VM communicates only with the host and other VMs on the same private network; no external access |

---

## VM Security

### VM Escape

A **VM escape** occurs when malware on one VM exploits a vulnerability in the hypervisor to break out of its isolation and access other VMs or the host.

- Considered a critical security threat in virtualization
- No significant real-world VM escapes have occurred to date
- Hypervisor developers actively monitor and patch against this risk

### Each VM Needs Its Own Security

VMs are not inherently secure just because they're virtualized. Each VM should be treated as a standalone system:
- Configure a firewall
- Install anti-malware
- Apply OS hardening and patching
- Keep the OS updated

### Downloaded VMs

Malware authors sometimes publish pre-built VMs online with embedded malware.

**Best practice:** Build your own VMs from scratch. If downloading a VM from the internet, verify the source thoroughly and scan for malware before running.

---

## VDI — Virtual Desktop Infrastructure

**VDI (Virtual Desktop Infrastructure)** moves the entire desktop OS to a VM running on a remote server or in the cloud. The user's local device only handles display, keyboard, and mouse input.

- Also called **DaaS (Desktop as a Service)**
- The desktop OS, applications, and data all run on the virtualized system remotely
- Local device requires minimal CPU, RAM, or storage
- Requires a network connection to stream the desktop session
- From the user's perspective, it looks and behaves exactly like a local OS

---

## Containerization

**Containerization** virtualizes only the **application** — not a full OS. Each container is a self-contained, isolated application package.

**How it differs from VMs:**

| Feature | VMs | Containers |
|---|---|---|
| What is isolated | Full OS + application | Application only |
| OS per instance | Yes (guest OS per VM) | No — all share the host OS |
| Image size | Large | Small / lightweight |
| Portability | Moderate | Very high |
| Startup speed | Slower (full OS boot) | Fast |
| OS flexibility | Each VM can run a different OS | All containers must use the same host OS type |

**Containerization software:** The most popular is **Docker**.

**Limitation:** All containers on a single host must be compatible with the host OS. You cannot run a Windows container and a Linux container on the same Docker host.

---

## VMs vs. Containers

```
VMs:
Hardware → Hypervisor → [VM1: Guest OS + App] [VM2: Guest OS + App] [VM3: Guest OS + App]

Containers:
Hardware → Host OS → Container Engine (Docker) → [App1] [App2] [App3]
```

**Tradeoff:** VMs offer more OS flexibility; containers are lighter, faster, and more portable but all share the same host OS.

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| Hypervisor / VMM | Software managing all VMs; allocates CPU, RAM, storage, network |
| Type 1 (bare metal) | Runs directly on hardware; no host OS; examples: ESXi, Hyper-V |
| Type 2 (hosted) | Runs on top of a host OS; examples: VMware Workstation, VirtualBox, Parallels |
| Intel VT / AMD-V | CPU hardware features for virtualization; must be enabled in BIOS |
| NAT networking | VM on internal subnet; hypervisor NATs to external network |
| Bridged networking | VM appears as a normal device on the local network |
| Private/host-only | VM isolated; no external access |
| VM escape | Malware breaks out of VM isolation via hypervisor flaw; rare but serious threat |
| VM security | Each VM needs its own firewall, anti-malware, hardening |
| Downloaded VMs | Risk of embedded malware; build your own when possible |
| VDI / DaaS | Full desktop OS runs remotely as a VM; local device is just a terminal |
| Containerization | App-only isolation; no guest OS; lightweight; all share host OS |
| Docker | Most popular containerization platform |
| Container limitation | All containers on one host must be compatible with the same host OS |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201)**, covering hypervisor types, CPU virtualization support, VM networking, VM security, VDI/DaaS, and containerization (Docker).
