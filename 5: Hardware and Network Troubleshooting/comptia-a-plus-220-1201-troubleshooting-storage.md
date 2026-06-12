# CompTIA A+ 220-1201 — Troubleshooting Storage Devices

> **Exam Domain Reference** | Core 1 (220-1201) — Hardware (Domain 3)  
> Topics: Read/write errors, clicking/grinding noise, drive not recognized, data loss, RAID failure, S.M.A.R.T., IOPS, missing drive letters, drive controller failure

---

## Table of Contents

1. [Read/Write Errors & Physical Drive Failure](#readwrite-errors--physical-drive-failure)
2. [Drive Not Recognized / Boot Failures](#drive-not-recognized--boot-failures)
3. [Data Loss & Corruption](#data-loss--corruption)
4. [RAID Troubleshooting](#raid-troubleshooting)
5. [S.M.A.R.T. Monitoring](#smart-monitoring)
6. [IOPS — Storage Performance Measurement](#iops--storage-performance-measurement)
7. [Missing Drive Letters (Network Drives)](#missing-drive-letters-network-drives)
8. [Drive Controller Failure](#drive-controller-failure)
9. [Troubleshooting Quick Reference](#troubleshooting-quick-reference)
10. [Key Takeaways](#key-takeaways)

---

## Read/Write Errors & Physical Drive Failure

**Symptom:** "Cannot read from source disk" error; extremely slow performance; system freezes during disk access.

**What's happening:** The drive is continuously retrying failed reads/writes to a damaged sector — each retry adds significant delay.

**HDD-specific failure sounds:**

| Sound | Meaning |
|---|---|
| **Clicking** ("click of death") | Actuator arm / read-write head mechanical failure |
| **Grinding** | Metal-on-metal contact between platters and heads — severe failure |

**Immediate action:** Stop using the drive and **back up data immediately** before the drive fails completely.

**Troubleshooting steps (after backup):**
1. Reseat data and power cables
2. Check system temperatures — overheating can cause read/write failures
3. Verify the power supply provides adequate wattage for all components
4. Run manufacturer's drive diagnostics (downloaded from manufacturer's website)
5. Check S.M.A.R.T. data for warning indicators

---

## Drive Not Recognized / Boot Failures

| Error Message | Meaning |
|---|---|
| "Drive not recognized" / "Boot device not found" | System cannot detect the drive at all |
| "Operating system not found" | Drive is detected, but no bootable OS found on it |
| No lights, no response | Drive completely unresponsive |

**Troubleshooting:**
1. Reseat power and data cables (SATA data + SATA power)
2. Check BIOS boot order — ensure correct drive is first in sequence
3. Check if USB drive is plugged in — system may be trying to boot from it instead
4. Try a known-good cable to isolate cable as the cause
5. Move drive to a different computer to test whether the problem follows the drive or stays with the original system
6. Check BIOS for drive detection — confirm the BIOS sees the drive in its storage configuration

---

## Data Loss & Corruption

**HDD:** When the drive fails physically, data may be inaccessible or unrecoverable. Professional data recovery services exist but are expensive.

**SSD:** When an SSD fails, it often becomes **read-only** — data can frequently still be read even when writing is no longer possible.

**Prevention:** The only reliable protection against data loss is a **current, tested backup**.

---

## RAID Troubleshooting

**First step:** Identify what RAID level is in use — this determines fault tolerance and recovery options.

| RAID Level | Min Drives | Drives That Can Fail | Recovery |
|---|---|---|---|
| **RAID 0** | 2 | 0 — any failure = total data loss | Restore from backup after replacing drive |
| **RAID 1** | 2 | 1 | Replace bad drive; array rebuilds automatically |
| **RAID 5** | 3 | 1 | Replace bad drive; re-sync array |
| **RAID 6** | 4 | 2 | Replace bad drives; re-sync array |
| **RAID 10** | 4 | 1 per mirrored pair | Replace bad drive(s); array rebuilds |

**RAID troubleshooting process:**
1. Check RAID controller for error messages, alerts, and email/text notifications
2. Identify which **specific physical drive** has failed (do not accidentally replace a healthy drive)
3. Check drive power connections and data cables
4. Replace the identified failed drive
5. Allow the RAID array to re-sync/rebuild
6. Reset the RAID controller log if applicable

**RAID 0 reminder:** Zero redundancy — any single drive failure destroys the entire array. Restore from backup.

---

## S.M.A.R.T. Monitoring

**S.M.A.R.T. (Self-Monitoring, Analysis, and Reporting Technology)** is built into most modern drives and collects health and performance statistics over time.

**Key S.M.A.R.T. attributes:**
- Power_On_Hours — total hours the drive has been running
- Power_Cycle_Count — number of times power has been cycled
- Temperature_Celsius — current drive temperature
- Reallocated sectors, pending sectors — indicators of physical media problems

**How to use it:**
- **Raw SMART data** — viewable with third-party tools; requires knowing which attributes are important
- **Third-party analysis software** — interprets SMART data and flags warning indicators; can schedule daily/weekly checks
- **RAID controllers** — many have SMART monitoring built in with email/text alerting

**Why it matters:** SMART trends can identify a drive that is degrading **before** it fails completely — giving time to replace it and avoid data loss.

---

## IOPS — Storage Performance Measurement

**IOPS (Input/Output Operations Per Second)** measures the raw number of read/write operations a storage device can perform per second.

| Storage Type | Approximate IOPS |
|---|---|
| **HDD (spinning)** | ~200 IOPS |
| **SSD** | ~1,000,000 IOPS |

The difference explains why replacing a hard drive with an SSD dramatically improves system performance — 5,000× more operations per second.

**Use case:** Compare drives during purchasing decisions; benchmark existing drives to identify performance bottlenecks.

---

## Missing Drive Letters (Network Drives)

If a user's drive letter is missing (e.g., Z: drive), the issue may not be a physical drive at all — it may be a **mapped network drive** that failed to reconnect.

**Check:**
- Is the user's **login script** or manual mapping configured correctly?
- Is the **network share** available on the server?

**Windows Map Network Drive settings:**
- Drive letter (e.g., Z:)
- Server path (e.g., `\\gateroom\mission_reports`)
- **Reconnect at sign-in** checkbox — should be enabled for persistent mappings

---

## Drive Controller Failure

The **drive controller** (especially on servers using RAID cards like the Dell PERC) may fail independently of the drives themselves.

**Symptoms:**
- Error messages during POST from the RAID/HBA BIOS
- Messages like "Integrated RAID exception detected" or volume status showing "INACTIVE"
- Drives visible but inaccessible

**Investigation:** Enter the RAID controller's configuration utility during POST to assess volume status and identify failed components.

---

## Troubleshooting Quick Reference

| Symptom | Likely Cause | First Action |
|---|---|---|
| Slow performance + clicking | HDD physical failure | Back up data immediately |
| "Cannot read from source disk" | Bad sectors / failing drive | Back up; run manufacturer diagnostics |
| "Boot device not found" | Drive not detected | Reseat cables; check BIOS |
| "Operating system not found" | Drive detected; no OS | Check boot order; check OS installation |
| No drive lights | Drive unresponsive | Check power + data cables |
| RAID drive failed | Single drive failure | Check RAID type; identify correct drive; replace + rebuild |
| RAID 0 failure | No redundancy | Restore from backup |
| SMART warning | Drive degrading | Back up now; plan drive replacement |
| Slow vs. SSD | HDD ~200 IOPS | Replace with SSD (~1M IOPS) |
| Missing drive letter | Network drive not remapped | Check login script; remap manually |
| RAID controller error | Controller or volume issue | Enter RAID BIOS utility for diagnosis |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| Click of death | HDD actuator/head failure; data recovery very difficult |
| "Cannot read" error | Drive retries = extreme slowdown; back up immediately |
| "OS not found" | Drive detected; OS missing or corrupt |
| "Drive not recognized" | Drive not detected; check cables and BIOS |
| RAID 0 failure | Any single drive = total data loss; no redundancy |
| RAID 1 | Survives 1 drive failure; replace and auto-rebuild |
| RAID 5 | Survives 1 failure; replace and re-sync |
| RAID 6 | Survives 2 failures; replace and re-sync |
| RAID 10 | Survives 1 per mirrored pair |
| S.M.A.R.T. | Built-in drive health monitoring; use third-party tools to analyze |
| IOPS | HDD ~200; SSD ~1,000,000 — SSD is 5,000× faster |
| SSD failure | Often becomes read-only — data may still be readable |
| Missing drive letter | Often a network drive mapping issue, not a physical drive |
| Backup | The only true protection against data loss from any failure type |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Hardware Troubleshooting**, covering storage device failure symptoms, RAID recovery, S.M.A.R.T. monitoring, IOPS, and drive controller issues.
