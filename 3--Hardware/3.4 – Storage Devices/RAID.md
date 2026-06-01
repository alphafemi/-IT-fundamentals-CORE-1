# CompTIA A+ 220-1201 — RAID

> **Exam Domain Reference** | Core 1 (220-1201) — Hardware (Domain 3)  
> Topics: RAID 0, RAID 1, RAID 5, RAID 6, RAID 10 (RAID 1+0) — redundancy, performance, drive requirements

---

## Table of Contents

1. [What Is RAID?](#what-is-raid)
2. [RAID 0 — Striping](#raid-0--striping)
3. [RAID 1 — Mirroring](#raid-1--mirroring)
4. [RAID 5 — Striping with Parity](#raid-5--striping-with-parity)
5. [RAID 6 — Striping with Double Parity](#raid-6--striping-with-double-parity)
6. [RAID 10 (RAID 1+0) — Stripe of Mirrors](#raid-10-raid-10--stripe-of-mirrors)
7. [RAID Comparison Table](#raid-comparison-table)
8. [Key Takeaways](#key-takeaways)

---

## What Is RAID?

**RAID (Redundant Array of Independent Disks)** — also called *Redundant Array of Inexpensive Disks* — combines multiple physical drives to improve performance, provide redundancy, or both.

> **Critical exam point: RAID is NOT a backup.** RAID protects against drive failure, but it does not protect against accidental deletion, ransomware, fire, theft, or other data loss scenarios. A separate backup process is always required.

**Two core RAID concepts:**
- **Striping** — data is split across multiple drives for speed
- **Mirroring** — data is duplicated across drives for redundancy

---

## RAID 0 — Striping

**How it works:** Data is split into blocks and written alternately across all drives simultaneously.

```
File blocks:  1A  2A  3A  4A  5A  6A ...
Disk 0:       1A      3A      5A
Disk 1:           2A      4A      6A
```

| Property | Value |
|---|---|
| Minimum drives | 2 |
| Redundancy | **None** |
| Fault tolerance | 0 drives |
| Speed | Fastest read/write of all RAID types |
| Usable capacity | 100% of all drives combined |

**Risk:** Losing **any single drive** makes all data inaccessible — every block is needed to reconstruct the full file.

> **"RAID 0" = zero redundancy.** Use only when speed is critical and data loss is acceptable.

---

## RAID 1 — Mirroring

**How it works:** Every write is duplicated to two (or more) drives simultaneously. Both drives contain an exact copy of all data.

```
Disk 0:  A  B  C  D ...
Disk 1:  A  B  C  D ...  (exact mirror)
```

| Property | Value |
|---|---|
| Minimum drives | 2 |
| Redundancy | Yes |
| Fault tolerance | 1 drive failure |
| Speed | Read can be faster; writes slightly slower (two writes per operation) |
| Usable capacity | 50% (half the total is used for the mirror) |

**Recovery:** If one drive fails, the other continues operating normally. Replace the failed drive and rebuild the mirror.

---

## RAID 5 — Striping with Parity

**How it works:** Data is striped across drives like RAID 0, but **parity data** is also written and distributed across all drives. Parity allows reconstruction of lost data if a drive fails.

```
4-drive example:
Disk 0:  A1   B1   C1   P(D)
Disk 1:  A2   B2   P(C) D1
Disk 2:  A3   P(B) C2   D2
Disk 3: P(A)  B3   C3   D3
(parity blocks distributed across all drives)
```

| Property | Value |
|---|---|
| Minimum drives | 3 |
| Redundancy | Yes |
| Fault tolerance | **1 drive failure** |
| Speed | Good read performance; write requires parity calculation (some CPU overhead) |
| Usable capacity | (n − 1) drives — one drive's worth of space used for parity |

**Recovery:** Surviving drives + parity data = lost data is mathematically reconstructed. Performance is degraded during rebuild.

**Limitation:** If a **second drive fails** before the array is rebuilt, all data is lost.

---

## RAID 6 — Striping with Double Parity

**How it works:** Identical to RAID 5 but with **two independent sets of parity data** distributed across the array.

| Property | Value |
|---|---|
| Minimum drives | 4 |
| Redundancy | Yes |
| Fault tolerance | **2 drive failures** |
| Speed | Slightly slower writes than RAID 5 (two parity calculations) |
| Usable capacity | (n − 2) drives — two drives' worth of space used for parity |

**Advantage over RAID 5:** Provides time to replace a failed drive without risking total data loss if a second drive also fails during the rebuild window.

---

## RAID 10 (RAID 1+0) — Stripe of Mirrors

**How it works:** Combines RAID 0 (striping) and RAID 1 (mirroring). Data is striped across mirrored pairs — each striped set has a complete mirror.

```
Stripe across 3 pairs:
Pair 1: Disk A  ←mirror→  Disk B    (contains stripe segment 1)
Pair 2: Disk C  ←mirror→  Disk D    (contains stripe segment 2)
Pair 3: Disk E  ←mirror→  Disk F    (contains stripe segment 3)
```

| Property | Value |
|---|---|
| Minimum drives | 4 |
| Redundancy | Yes |
| Fault tolerance | Can survive **one failure per mirrored pair** simultaneously |
| Speed | Excellent — full stripe speed of RAID 0 |
| Usable capacity | 50% (mirroring halves usable space) |

**Example fault tolerance:** In a 6-drive RAID 10 (three mirrored pairs), losing one drive from each pair (up to 3 drives total, one per pair) still leaves the array fully operational.

---

## RAID Comparison Table

| RAID Level | Min Drives | Redundancy | Max Drive Failures Tolerated | Usable Capacity | Best For |
|---|---|---|---|---|---|
| **RAID 0** | 2 | No | 0 | 100% of all drives | Maximum speed; no data protection needed |
| **RAID 1** | 2 | Yes | 1 | 50% | Simple redundancy; two-drive setups |
| **RAID 5** | 3 | Yes | 1 | (n−1) drives | Balance of speed, capacity, and redundancy |
| **RAID 6** | 4 | Yes | 2 | (n−2) drives | Higher fault tolerance than RAID 5 |
| **RAID 10** | 4 | Yes | 1 per mirrored pair | 50% | Best performance + redundancy combination |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| RAID ≠ backup | RAID protects against drive failure only; a separate backup is still required |
| RAID 0 | Striping; fastest; zero redundancy; lose any drive = lose all data |
| RAID 1 | Mirroring; 50% usable capacity; survives 1 drive failure |
| RAID 5 | Striping + distributed parity; (n−1) capacity; survives 1 drive failure |
| RAID 6 | Striping + double parity; (n−2) capacity; survives 2 drive failures |
| RAID 10 | Stripe of mirrors; 50% capacity; survives 1 failure per mirrored pair |
| RAID 5 CPU overhead | Parity calculation adds CPU load, especially during rebuild |
| RAID 6 vs. RAID 5 | One extra drive of parity; allows a second drive to fail safely |
| RAID 10 minimum | 4 drives required |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Hardware Domain**, covering RAID levels 0, 1, 5, 6, and 10 — including redundancy, fault tolerance, capacity, and use cases.
