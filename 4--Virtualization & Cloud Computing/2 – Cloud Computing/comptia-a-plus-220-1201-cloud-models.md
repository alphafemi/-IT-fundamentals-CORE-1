# CompTIA A+ 220-1201 — Cloud Computing Models

> **Exam Domain Reference** | Core 1 (220-1201) — Networking (Domain 2)  
> Topics: Public vs. private cloud, IaaS, SaaS, PaaS, shared responsibility model

---

## Table of Contents

1. [What Is Cloud Computing?](#what-is-cloud-computing)
2. [Cloud Deployment Models](#cloud-deployment-models)
   - [Public Cloud](#public-cloud)
   - [Private Cloud](#private-cloud)
   - [Hybrid Cloud](#hybrid-cloud)
   - [Community Cloud](#community-cloud)
3. [Cloud Service Models](#cloud-service-models)
   - [IaaS — Infrastructure as a Service](#iaas--infrastructure-as-a-service)
   - [PaaS — Platform as a Service](#paas--platform-as-a-service)
   - [SaaS — Software as a Service](#saas--software-as-a-service)
4. [Shared Responsibility Model](#shared-responsibility-model)
5. [Key Takeaways](#key-takeaways)

---

## What Is Cloud Computing?

Cloud computing delivers computing resources (CPU, storage, applications) over the internet — hosted in someone else's data center — on demand.

**Key advantages:**
- Deploy applications globally in moments (vs. weeks for physical servers)
- Scale resources up or down instantly
- Pay only for what you use — no large upfront capital expenditure
- Geographic distribution — deploy close to users worldwide
- Metered billing — efficient for seasonal or variable workloads

---

## Cloud Deployment Models

### Public Cloud

- Hosted and managed by a **third-party cloud provider**
- Accessible over the **public internet**
- Examples: Microsoft Azure, Amazon Web Services (AWS), Google Cloud, Rackspace

### Private Cloud

- Cloud infrastructure hosted in an **organization's own data center**
- Organization purchases and manages all hardware
- Data stays within the organization's control
- More control and security; higher upfront cost

### Hybrid Cloud

- Combination of **public and private** cloud
- Internal/sensitive applications on the private cloud; public-facing services on the public cloud
- Very common in enterprise organizations

### Community Cloud

- Shared cloud infrastructure built cooperatively by a **group of organizations** with similar needs
- Allows smaller organizations to share cloud costs and capabilities without each building their own private cloud

---

## Cloud Service Models

Three service models define **who manages what**:

### IaaS — Infrastructure as a Service

Also called: **HaaS (Hardware as a Service)**

You **rent the hardware** — CPU, storage, network — from the cloud provider. You manage everything above the hardware layer.

**Customer manages:**
- Operating system (install, patch, update)
- Applications
- Data
- Security

**Provider manages:**
- Physical data center
- Network infrastructure
- Physical hardware

**Example:** Renting a virtual server from AWS or Azure and installing your own OS and web server software.

**Trade-off:** Maximum control + maximum management overhead.

### PaaS — Platform as a Service

You **rent a platform** — the provider manages the OS and infrastructure; you build and run your application on top.

**Customer manages:**
- Application code and development
- Data

**Provider manages:**
- Physical infrastructure
- Network
- OS and runtime environment

**Example:** Salesforce Platform — developers build custom applications that run on Salesforce's managed infrastructure.

**Trade-off:** Less management overhead than IaaS; more flexibility than SaaS.

### SaaS — Software as a Service

You **use an application** — the provider manages everything.

**Customer manages:**
- User accounts / identity
- Data input
- Devices used to access the service

**Provider manages:**
- Everything: infrastructure, OS, application code, updates, security

**Example:** Google Mail (Gmail), Microsoft 365 — log in and use; no installation or maintenance needed.

**Trade-off:** Least management overhead; least flexibility / customization.

---

## Shared Responsibility Model

The **shared responsibility model** defines what the cloud provider is responsible for vs. what the customer is responsible for.

| Layer | On-Premises | IaaS | PaaS | SaaS |
|---|---|---|---|---|
| Physical data center | Customer | **Provider** | **Provider** | **Provider** |
| Network infrastructure | Customer | **Provider** | **Provider** | **Provider** |
| Hardware (CPU/storage) | Customer | **Provider** | **Provider** | **Provider** |
| Operating system | Customer | Customer / Provider | **Provider** | **Provider** |
| Application | Customer | Customer | Customer | **Provider** |
| Data | Customer | Customer | Customer | Customer |
| Identity / accounts | Customer | Customer | Customer | Customer |

> **Rule of thumb:** As you move from IaaS → PaaS → SaaS, the provider takes over more responsibility. The customer always retains responsibility for their data and user accounts.

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| Public cloud | Hosted by third-party; accessible from internet; AWS, Azure, Google Cloud |
| Private cloud | In-house data center; full control; higher upfront cost |
| Hybrid cloud | Mix of public and private; very common in enterprises |
| Community cloud | Shared infrastructure among organizations with similar needs |
| IaaS | Rent hardware; you manage OS, apps, data; also called HaaS |
| PaaS | Rent a platform; provider manages OS; you write the app |
| SaaS | Use an app; provider manages everything; you just log in |
| SaaS examples | Gmail, Microsoft 365 |
| PaaS examples | Salesforce Platform |
| IaaS examples | AWS EC2, Azure VMs |
| Shared responsibility | Data and user accounts always remain the customer's responsibility |
| IaaS management | Most overhead (you manage OS + apps); most control |
| SaaS management | Least overhead; least flexibility |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Domain 2 — Networking**, covering cloud deployment models (public/private/hybrid/community) and service models (IaaS/PaaS/SaaS) including the shared responsibility model.
