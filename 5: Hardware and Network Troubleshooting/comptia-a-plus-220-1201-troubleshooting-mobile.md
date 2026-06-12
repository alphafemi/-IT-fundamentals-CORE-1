# CompTIA A+ 220-1201 — Troubleshooting Mobile Devices

> **Exam Domain Reference** | Core 1 (220-1201) — Mobile Devices (Domain 1)  
> Topics: Battery issues, swollen battery, broken screen, improper charging, liquid damage (LCI), overheating, unresponsive device, damaged ports, malware, cursor drift, app install failures, stylus issues, poor performance

---

## Table of Contents

1. [Battery Issues](#battery-issues)
2. [Swollen Battery](#swollen-battery)
3. [Broken Screen](#broken-screen)
4. [Improper Charging](#improper-charging)
5. [Liquid Damage & LCI](#liquid-damage--lci)
6. [Overheating](#overheating)
7. [Unresponsive / Frozen Device](#unresponsive--frozen-device)
8. [Damaged Ports (USB / Charging Interface)](#damaged-ports-usb--charging-interface)
9. [Malware on Mobile Devices](#malware-on-mobile-devices)
10. [Cursor Drift](#cursor-drift)
11. [App Install Failures](#app-install-failures)
12. [Stylus Issues](#stylus-issues)
13. [Poor Performance / Slow Device](#poor-performance--slow-device)
14. [Troubleshooting Quick Reference](#troubleshooting-quick-reference)
15. [Key Takeaways](#key-takeaways)

---

## Battery Issues

**Rapid battery drain — common causes:**
- Device in poor signal area — constantly polling for cellular signal
- Background apps consuming CPU and battery
- Wi-Fi, Bluetooth, or GPS enabled when not needed

**Fixes:**
- Enable **Airplane Mode** in poor signal areas
- Disable unused wireless features (Wi-Fi, Bluetooth, GPS)
- Check battery usage stats: **Settings → Battery** (iOS, iPadOS, Android)
  - Shows which apps consume the most battery
  - Shows battery health and estimated replacement timing

---

## Swollen Battery

A battery that has swollen has accumulated internal gas — a serious safety hazard.

**Signs:**
- Device case is bulging, popped open, or distorted
- Battery visually expanded beyond normal size

**Actions:**
- **Do not pierce, open, or puncture** the battery — fire and toxic fume risk
- **Power off the device immediately**
- **Replace the battery as soon as possible**
- Even if the device still works, do not continue using a swollen battery

> **Exam Tip:** A swollen battery is a **fire hazard** — always treat it as an emergency requiring immediate replacement.

---

## Broken Screen

Mobile screens combine the display and glass into one integrated assembly.

**Key points:**
- The glass and display are usually **fused together** — you cannot replace just the glass
- Replacing the screen = replacing the entire display assembly
- Broken glass has **sharp edges** — do not use fingers on a cracked screen
- Use **screen protector** or **glass tape** to cover sharp edges before handling

**Before repair:** Back up the device in case something goes wrong during the replacement.

---

## Improper Charging

Device plugged in but not charging — check in order:

1. **Charging port (device side)** — inspect for debris blocking the connector; clear with non-conductive tool
2. **Charging cable** — cables wear out; test with a known-good cable
3. **Power adapter** — test with a multimeter or swap with a known-good adapter
4. **Wall outlet** — verify it has power

---

## Liquid Damage & LCI

**LCI (Liquid Contact Indicator):** A small sticker inside the device (charging port, SIM slot) that **changes color when exposed to liquid**. Technicians check this during repair intake.

**Liquid damage response:**
1. **Power off immediately** — do not try to turn it on
2. **Do not connect to power**
3. Remove the case, SIM card, and battery (if removable)
4. **Use desiccant packets** (not rice — rice does not absorb water effectively)
5. **Leave the device alone for 24 hours** — do not heat it, move it excessively, or attempt to power it on
6. After 24 hours, if dry, attempt to power on

> **Rice myth:** Rice in a bag leaves the phone alone for 24 hours (which is what helps), but the rice itself provides minimal moisture absorption. **Desiccant packets are far more effective.**

---

## Overheating

**Causes:**
- Excessive ambient heat (sun, dashboard, hot car)
- Charging + heavy app usage simultaneously
- Poor signal area → device works harder to maintain connection

**What happens:** Device automatically shuts down to protect electronics.

**Fixes:**
- Move device out of direct sunlight or heat sources
- Close high-CPU/battery apps
- Check battery stats for apps consuming excessive resources
- Allow device to cool before using again

---

## Unresponsive / Frozen Device

Device screen is black or unresponsive to touch.

**Soft reset methods:**

| Platform | Method |
|---|---|
| **iOS/iPadOS** | Power button → Slide to power off → Power back on |
| **iOS (force reset)** | Hold Power + Home (or Volume) for ~10 seconds |
| **Android** | Remove and reinsert battery (if removable); or hold Power + Volume for reset |

Note: Android reset button combinations vary by manufacturer — check device documentation.

---

## Damaged Ports (USB / Charging Interface)

If the charging/data port is physically damaged:
- Intermittent or no charging
- Cannot transfer data to/from device

**Cause:** Physical damage from rough handling of charging cables.

**Repair:** On most phones, the charging port is **not modular** — requires replacing the **entire system board**.

---

## Malware on Mobile Devices

**Signs of mobile malware:**
- Unknown or unexpected apps running
- Unusually high data usage
- A single app consuming excessive CPU or battery

**Response:**
- Run **anti-malware / antivirus** software designed for mobile devices
- Review installed apps for anything unrecognized
- Consider factory reset if infection is confirmed

---

## Cursor Drift

**Definition:** Apps opening or the cursor moving on screen with **no user input** — as if the screen is being touched on its own.

**Cause:** Failing digitizer or display hardware — not malware.

**Fixes:**
1. Run **touch screen calibration** (available on some older devices)
2. If calibration fails or option unavailable → replace the display assembly

---

## App Install Failures

Possible causes and fixes:

| Cause | Fix |
|---|---|
| Not enough storage | Delete unused apps or data to free space |
| Poor network connectivity | Retry on a stronger connection |
| Incompatible OS version | Update OS or check app compatibility requirements |
| Authentication required | Sign in with correct App Store / Google Play credentials |

---

## Stylus Issues

**Not working — check in order:**
1. **Battery** — stylus battery may be dead; charge it
2. **Bluetooth pairing** — verify stylus is paired with the device
3. **Physical damage** — inspect the stylus body and tip for damage
4. **Replace the tip** — stylus tips are often replaceable
5. **Reset** — reset the mobile device and the stylus; re-pair

---

## Poor Performance / Slow Device

**Troubleshooting steps:**

| Step | Reason |
|---|---|
| Check and update OS + apps | Outdated software causes bugs and performance issues |
| Check available storage | Low storage = severe slowdown and unexpected restarts |
| Close background apps | Apps using CPU/RAM in background drain resources |
| Run anti-malware scan | Malware consumes resources silently |
| Check hardware health | Damaged storage causes slow read/write |
| Consider hardware age | Old devices may simply not support current apps |

---

## Troubleshooting Quick Reference

| Symptom | Likely Cause | First Action |
|---|---|---|
| Battery drains rapidly | Bad signal, background apps, Wi-Fi/BT on | Check Settings → Battery; disable unused features |
| Swollen battery | Chemical degradation | Power off immediately; replace battery |
| Broken screen | Physical impact | Tape sharp edges; back up; replace display |
| Not charging | Dirty port, bad cable, bad adapter | Clear port; swap cable; test adapter |
| Liquid damage | Water/liquid exposure | Power off; remove battery; use desiccant; wait 24 hr |
| LCI triggered | Liquid contact | Technician check during repair intake |
| Overheating | Heat source, heavy use, poor signal | Remove from heat; close apps; allow to cool |
| Frozen / unresponsive | OS hang | Soft reset (Power off/on); force reset if needed |
| Damaged charging port | Physical wear | Likely requires system board replacement |
| Unexpected app activity | Malware suspected | Run mobile anti-malware; review installed apps |
| Cursor drift | Failing digitizer | Calibrate touch; if persists → replace display |
| App won't install | Storage, connectivity, compatibility, auth | Free storage; check OS version; sign in |
| Stylus not working | Battery, pairing, damage | Charge; re-pair; inspect tip; reset |
| Slow performance | Storage full, outdated SW, background apps | Update; free storage; close apps |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| Battery drain | Check Settings → Battery; disable Wi-Fi/BT/GPS when not needed |
| Swollen battery | Fire hazard; power off; replace immediately; do NOT pierce |
| LCI | Liquid Contact Indicator; changes color on liquid exposure; checked during repair |
| Liquid damage | Power off; use desiccant (not rice); wait 24 hours |
| Broken screen | Glass + display are integrated; cannot replace glass alone |
| Charging port damage | Usually requires system board replacement |
| Cursor drift | Failing digitizer; not malware; calibrate or replace display |
| App install failure | Check storage, connectivity, OS compatibility, authentication |
| Stylus | Check battery and Bluetooth pairing first |
| Performance | Update OS/apps; free storage; close background apps |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Domain 1 — Mobile Devices**, covering mobile device troubleshooting including battery, screen, charging, liquid damage, overheating, and performance issues.
