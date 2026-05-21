# CompTIA A+ 220-1201 — Mobile Device Management (MDM) & Deployment Models

> **Exam Domain Reference** | Core 1 (220-1201) — Mobile Devices  
> Topics: MDM, BYOD, COPE, CYOD, device policies, synchronization, application management

---

## Table of Contents

1. [Overview](#overview)
2. [Mobile Device Management (MDM)](#mobile-device-management-mdm)
   - [What MDM Controls](#what-mdm-controls)
   - [MDM Console Features](#mdm-console-features)
3. [Mobile Device Deployment Models](#mobile-device-deployment-models)
   - [BYOD — Bring Your Own Device](#byod--bring-your-own-device)
   - [COPE — Corporate Owned, Personally Enabled](#cope--corporate-owned-personally-enabled)
   - [CYOD — Choose Your Own Device](#cyod--choose-your-own-device)
4. [Synchronization & Data Management](#synchronization--data-management)
5. [Deployment Model Comparison](#deployment-model-comparison)
6. [Key Takeaways](#key-takeaways)

---

## Overview

Organizations with employees using mobile phones — whether company-issued or personal — need a centralized way to enforce security policies, manage applications, and protect corporate data. **Mobile Device Management (MDM)** software provides this capability, working across a range of deployment models depending on who owns the device.

---

## Mobile Device Management (MDM)

An MDM is specialized software that allows a system administrator to centrally manage all mobile devices in an organization from a single console.

MDM can manage:
- **Company-owned devices** (purchased and assigned by the organization)
- **Personally-owned devices** (employee's own phone used for work — BYOD)

### What MDM Controls

**Security Policies:**
- Enforce screen locks with PIN or other authentication
- Require two-factor / multifactor authentication (MFA)
- Set policies on data encryption

**Application Management:**
- Specify which apps are **allowed** or **forbidden**
- **Push applications** to devices automatically without user action

**Hardware Feature Control (Restrictions):**

| Feature | MDM Can Enable/Disable |
|---|---|
| Camera | Yes |
| FaceTime / video calling | Yes |
| Voice dialing | Yes |
| Virtual assistants (e.g., Siri) | Yes |
| Printing | Yes |
| GPS | Yes |

**Data Partitioning (BYOD):**
- Creates a **separated corporate container** on a personal device
- Personal data remains private; corporate data is isolated and managed
- Policies can define what happens to corporate data when the device is lost, sold, or upgraded

### MDM Console Features

From the MDM dashboard, administrators can view and manage:

| Field | Description |
|---|---|
| Device name | Identifies the specific device |
| Platform | iOS, Android, etc. |
| Username | Employee associated with the device |
| Email / contact info | User contact details |
| IMEI | Unique hardware identifier for the device |
| OS version | Current operating system and patch level |
| Security status | Which security features are enabled or disabled |
| Network summary | Current network connectivity details |

> **Exam Tip:** **IMEI (International Mobile Equipment Identity)** is the unique identifier for a physical mobile device. It is separate from the SIM and does not change when you swap a SIM card.

---

## Mobile Device Deployment Models

### BYOD — Bring Your Own Device

The employee uses their **personally owned phone** for work purposes.

**Benefits:**
- Employees only carry one device
- No hardware cost to the organization

**Challenges:**
- Corporate data lives on a personal device
- Must balance **employee privacy** with **corporate data security**
- Policies must address what happens to corporate data when the device is sold, upgraded, or lost

**MDM role in BYOD:**
- Partitions the device into personal and corporate areas
- Enforces security policies only on the corporate partition
- Can remotely wipe corporate data without affecting personal data

### COPE — Corporate Owned, Personally Enabled

The **company purchases and owns** the device, then assigns it to an employee who may also use it personally.

**Key characteristics:**
- Organization has **full control** over the device
- Employee is permitted to use it as a personal device
- Company manages all aspects — storage policies, data retention, remote wipe
- Similar in management approach to how organizations manage laptops and desktops

### CYOD — Choose Your Own Device

A variation of COPE where the **employee selects a device** from a company-approved list.

- Company still purchases and manages the device
- Employee has limited choice of hardware within pre-approved options
- Balances user preference with organizational control

---

## Synchronization & Data Management

MDM controls how and when devices sync data back to corporate systems — critical since mobile devices are rarely plugged into a central facility.

### What Can Be Synchronized

- Email (e.g., Microsoft Outlook, Gmail)
- Contacts
- Calendar
- Reminders and notes
- Corporate account credentials

### Sync Network Controls

| Setting | Options |
|---|---|
| Sync over Wi-Fi only | Prevents cellular data usage (cost control) |
| Sync over cellular | Allowed, but may incur carrier charges |
| Automatic download size limit | Restrict large app downloads to Wi-Fi only |

> **Best Practice:** Check your carrier data contract before enabling unrestricted cellular sync. Many organizations limit cellular sync to control costs.

### Per-Service Sync Configuration

Different corporate services can have different sync settings. For example:
- **Microsoft Exchange** — sync mail, calendar, contacts on a specific schedule
- **Google Mail** — sync mail only, no calendar integration

Each account type is configured separately within the device's account settings, giving administrators granular control over exactly what data flows where and when.

### Data Recovery Considerations

MDM sync settings also determine how a device is **restored** after loss, damage, or replacement:
- What data was backed up and where it is stored
- Whether backups occur over Wi-Fi, cellular, or both
- How quickly a replacement device can be provisioned from backup

---

## Deployment Model Comparison

| Model | Who Owns Device | Personal Use Allowed | Company Control Level |
|---|---|---|---|
| **BYOD** | Employee | Yes (it's their phone) | Partial (corporate partition only) |
| **COPE** | Company | Yes (permitted) | Full |
| **CYOD** | Company | Yes (permitted) | Full (from approved device list) |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| MDM | Centrally manages all mobile devices; enforces policies and controls features |
| BYOD | Employee's own device; MDM partitions personal vs. corporate data |
| COPE | Company-owned; employee may use personally; full corporate control |
| CYOD | Company-owned; employee picks from approved device list |
| IMEI | Unique device identifier; visible in MDM console; does not change with SIM swap |
| App management | MDM can allow, block, or push-install applications |
| Sync controls | MDM specifies what syncs, when, and over which network (Wi-Fi vs. cellular) |
| Data partitioning | Separates personal and corporate data on BYOD devices |
| Screen lock enforcement | MDM can require PIN/password or MFA across all managed devices |
| Remote wipe | MDM can clear corporate data from a lost or decommissioned device |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201)**, covering the **Mobile Devices** domain — specifically mobile device management, deployment models (BYOD/COPE/CYOD), and synchronization configuration.
