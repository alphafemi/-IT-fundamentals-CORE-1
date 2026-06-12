# CompTIA A+ 220-1201 — Cloud Characteristics

> **Exam Domain Reference** | Core 1 (220-1201) — Networking (Domain 2)  
> Topics: Internal vs. external cloud, metered vs. non-metered utilization, ingress/egress, elasticity, availability, file synchronization, multitenancy

---

## Table of Contents

1. [Internal vs. External Cloud](#internal-vs-external-cloud)
2. [Metered Utilization](#metered-utilization)
3. [Elasticity](#elasticity)
4. [Availability & Redundancy](#availability--redundancy)
5. [File Synchronization](#file-synchronization)
6. [Multitenancy](#multitenancy)
7. [Key Takeaways](#key-takeaways)

---

## Internal vs. External Cloud

| Feature | Internal (Private) Cloud | External (Public) Cloud |
|---|---|---|
| Who owns hardware | The organization | The cloud provider |
| Who maintains it | The organization | The cloud provider |
| Resource dedication | Exclusive — no sharing | Shared with other customers |
| Upfront cost | High (capital expenditure) | None |
| Ongoing cost | No per-use fees | Pay-as-you-go or fixed monthly |
| Examples | Organization's own data center | AWS, Microsoft Azure, Rackspace |

**Key trade-off:** Private cloud requires significant upfront investment but has no metered usage costs. Public cloud has no upfront cost but ongoing usage fees.

---

## Metered Utilization

Cloud pricing models:

### Metered (Pay-as-you-go)

Costs based on actual resource consumption — common in enterprise/business cloud services.

| Traffic Type | Direction | May Be Charged |
|---|---|---|
| **Ingress** | Data coming **into** the cloud (uploads) | Yes |
| **Storage** | Data stored on cloud drives | Yes (per GB) |
| **Egress** | Data going **out** of the cloud (downloads by users) | Yes (often higher rate) |

At month-end, all usage is totaled and invoiced. Busy months = higher cost.

### Non-Metered (Fixed)

Common on consumer cloud services — pay a fixed price for a maximum storage block regardless of how much you upload or download.

**Example:** Paying $X/month for 2 GB of cloud storage — the fee is the same whether you use 100 MB or the full 2 GB.

---

## Elasticity

**Elasticity** is the ability to **scale resources up or down instantly** based on demand.

- Scale up when demand increases — deploy additional application instances automatically
- Scale down when demand decreases — release unused resources to reduce cost
- Changes can happen instantly and often **automatically** (no manual intervention)

**Example:** A retail website automatically spins up additional server instances during a holiday sale, then scales back down when traffic returns to normal.

> **Exam Tip:** Elasticity = automatic scaling up AND down. It is a defining characteristic of cloud computing.

---

## Availability & Redundancy

Cloud providers maintain high availability through:

- **Multiple redundant data centers** — if one facility has a problem, others take the load
- **Redundant hardware** within each data center — drive arrays, network connections, power
- **Cross-data-center failover** — in extreme cases, entire workloads are migrated from one data center to another

Result: Cloud services appear to be "always available" because multiple layers of redundancy absorb failures.

---

## File Synchronization

Cloud infrastructure can automatically **replicate data** across multiple geographic data centers.

- Maintains consistency across regions — users worldwide access the same data
- Can be application-managed (by the customer) or handled automatically by the cloud infrastructure
- Ensures data is available even if one data center is taken offline

**Example:** A database hosted in North America is automatically synchronized to data centers in Europe and Asia for low-latency global access.

---

## Multitenancy

**Multitenancy** means multiple customers (**tenants**) share the same cloud infrastructure simultaneously.

- All tenants use the same physical hardware, storage, and network
- **Strict separation** is maintained — no tenant can see another tenant's data
- Enables **efficiency**: by keeping hardware fully utilized across many customers, the provider achieves better economics and can offer lower costs

> **Exam Tip:** Multitenancy is how cloud providers make their infrastructure cost-effective. Multiple customers share resources, but their data remains isolated.

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| Internal/private cloud | Organization owns and manages all hardware; no ongoing usage fees; high upfront cost |
| External/public cloud | Third-party owned; shared infrastructure; pay-as-you-go or fixed |
| Metered utilization | Billed by actual use (ingress, storage, egress) |
| Ingress | Data flowing INTO the cloud |
| Egress | Data flowing OUT of the cloud (often costs more) |
| Non-metered | Fixed price for maximum storage block; consumer cloud model |
| Elasticity | Instant scale up or down based on demand; automatic; defining cloud feature |
| Availability | Multiple redundant data centers and hardware; cross-facility failover |
| File synchronization | Data replicated across data centers; customer or cloud-managed |
| Multitenancy | Multiple customers share same infrastructure; data is isolated between tenants |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Domain 2 — Networking**, covering cloud characteristics including internal/external deployment, metered utilization, elasticity, availability, file synchronization, and multitenancy.
