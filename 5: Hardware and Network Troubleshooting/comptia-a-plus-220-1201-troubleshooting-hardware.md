# CompTIA A+ 220-1201 — Troubleshooting Hardware

> **Exam Domain Reference** | Core 1 (220-1201) — Hardware (Domain 3)  
> Topics: POST/beep codes, BSoD, blank screen, no power, sluggish performance, overheating, random shutdowns, application errors, unusual noises, capacitor failure, CMOS battery

---

## Table of Contents

1. [POST & Beep Codes](#post--beep-codes)
2. [Blue Screen of Death (BSoD)](#blue-screen-of-death-bsod)
3. [Proprietary & Application Error Messages](#proprietary--application-error-messages)
4. [Blank / Black Screen](#blank--black-screen)
5. [No Power](#no-power)
6. [Sluggish Performance](#sluggish-performance)
7. [Overheating & Random Shutdowns](#overheating--random-shutdowns)
8. [Unusual Noises](#unusual-noises)
9. [Capacitor Failure](#capacitor-failure)
10. [CMOS Battery Failure](#cmos-battery-failure)
11. [Troubleshooting Quick Reference](#troubleshooting-quick-reference)
12. [Key Takeaways](#key-takeaways)

---

## POST & Beep Codes

The **POST (Power-On Self-Test)** runs at every startup and checks:
- CPU installed and communicating with BIOS
- Video subsystem operational
- RAM installed and functional

**If POST fails:**
- Error message displayed on screen (if video is working)
- **Beep codes** — series of long and short beeps from the motherboard

> **Exam Tip:** Beep codes are **manufacturer-specific** — the same beep pattern means different things on different motherboards. Always reference the manufacturer's documentation. Do not memorize specific beep codes.

**Beeping + black screen:** Likely bad video, bad RAM, or bad CPU — without these, nothing can be displayed.

**BIOS prompting for date/time at every boot:** CMOS battery has failed — see [CMOS Battery Failure](#cmos-battery-failure).

**Booting from wrong device:** Check BIOS boot order — move the preferred drive (e.g., internal SSD) to the top of the boot sequence.

---

## Blue Screen of Death (BSoD)

The **BSoD (Blue Screen of Death)** is a Windows **stop error** — the OS cannot recover and halts completely.

**Common causes:**
- Bad hardware
- Corrupt or incompatible device driver
- Malfunctioning application

**Information on the BSoD:**
- **Stop code** (e.g., `0xC0000135`) — searchable at `windows.com/stopcode`
- Driver name (if driver-related)

**Troubleshooting steps:**
- If caused by a recent change: use **Last Known Good Configuration**, **System Restore**, or **roll back the driver**
- If occurs at startup: try **Safe Mode**
- Reseat adapter cards and RAM modules — poor connections can cause BSoDs
- Run **hardware diagnostics** (from BIOS or manufacturer tools)

---

## Proprietary & Application Error Messages

Applications may display their own error screens with cryptic codes.

**Best practices:**
- **Document everything** — write down or screenshot the full error message including all error codes
- Provide the screenshot to the application manufacturer for faster diagnosis
- Check **Windows Event Viewer** and application-specific log files for additional context
- Use **Windows Reliability Monitor** — shows a history of application crashes with dates and times, integrated with Event Viewer

**Application simply disappears / crashes silently:** Check Event Viewer for logged errors even if no message was shown.

**Reinstalling the application** resolves issues caused by corrupt installation files and ensures the latest version is used.

---

## Blank / Black Screen

Troubleshoot in this order:

1. **Check physical connections** — both ends of the video cable (HDMI, DisplayPort, USB-C, DVI, VGA) and the power cable to the monitor
2. **Check input selection on monitor** — verify the monitor is set to the correct input (e.g., HDMI vs. VGA)
3. **Check brightness/contrast** — dim but visible image = check monitor settings
4. **Swap with a known-good monitor** — if a different monitor also shows black, the problem is the computer, not the monitor
5. **Video driver issue** — if Windows boots but immediately shows a black screen, boot with **VGA mode** (F8 during boot) to use a generic video driver

---

## No Power

Symptoms: system won't turn on, no lights, no fan activity.

**Troubleshooting path:**

| Check | How |
|---|---|
| Wall outlet | Use a multimeter or plug in a different device |
| Power cord | Try a known-good cable |
| Power supply output | Use a multimeter to test DC voltage outputs |
| Partial power (fans spin, nothing else) | Check PSU voltage outputs — fans need little power; motherboard needs more |

**Fans spinning, no video / POST:** Likely a POST failure — suspect motherboard or video card.

---

## Sluggish Performance

**First check: Task Manager**
- CPU, RAM, Disk, Network columns show what's consuming resources
- **Performance tab** shows graphical history over 60 seconds

**Additional steps:**

| Step | Purpose |
|---|---|
| Windows Update | Ensure OS and drivers are current |
| Check disk space | OS needs free space to operate efficiently |
| Run Disk Defrag | For HDDs only (not SSDs) |
| Check power plan | Laptop battery-saver mode throttles CPU |
| Run anti-malware scan | Malware consumes resources silently |
| Clean fans and vents | Dust-clogged fans → thermal throttling → slow performance |

---

## Overheating & Random Shutdowns

**Random shutdown with no warning:** Thermal protection triggered — CPU/component reached critical temperature.

**Troubleshooting:**
1. Check fans — are they spinning and clean?
2. Check heatsink — is it still properly seated?
3. Check thermal paste — re-apply if dried or missing
4. Use monitoring software (e.g., **HW Monitor** at cpuid.com) to view live sensor temperatures
5. Check Event Viewer for temperature-related events logged before shutdown
6. Check Device Manager — recently added hardware may be causing instability

**Symptom of thermal throttling:** System becomes progressively slower as temperatures rise, then shuts down.

---

## Unusual Noises

| Sound | Likely Cause |
|---|---|
| **Rattling** (when moving case) | Loose component inside — often a heatsink; reseat with thermal paste |
| **Scraping** | Hard drive mechanical failure — back up data immediately |
| **Clicking** (rhythmic) | Object caught in a fan — inspect and clean fans |
| **Popping + smoke/smell** | Capacitor failure — power off immediately |

---

## Capacitor Failure

Capacitors are small cylindrical components on the motherboard that store and regulate power.

**Symptoms of failing capacitors:**
- Top of capacitor is **bulging** (should be flat)
- Popping sound
- Smoke or burning smell

**Action:** Power off immediately to prevent further damage. Failed capacitors almost always require component/motherboard replacement.

---

## CMOS Battery Failure

The CMOS battery (small coin-cell battery on the motherboard) maintains the system date and time when the computer is unplugged.

**Symptom:** System prompts for date and time entry on every startup.

**Fix:** Replace the CMOS battery (usually CR2032 or similar) — available at most stores.

> **Important:** On modern systems, removing the CMOS battery does **not** reset BIOS configuration (including passwords). A physical jumper is required for a full BIOS reset.

---

## Troubleshooting Quick Reference

| Symptom | Most Likely Cause | First Step |
|---|---|---|
| Beeping + black screen | Bad RAM, CPU, or video | Check POST beep code in manufacturer docs |
| Date/time prompt every boot | CMOS battery dead | Replace CMOS battery |
| BSoD | Bad driver, hardware, or app | Note stop code; search windows.com/stopcode |
| Black screen, computer running | Cable disconnected, wrong input, driver issue | Check connections, input select, VGA mode |
| No power | PSU, cord, outlet | Multimeter test of outlet and PSU outputs |
| Fans spin, nothing else | POST failure — motherboard or GPU | Check POST codes; reseat cards |
| Sluggish performance | High CPU/RAM usage, malware, throttling, dust | Task Manager → Performance tab |
| Random shutdowns | Overheating | Check fans, heatsink, thermal paste, temperatures |
| Rattling noise | Loose heatsink | Reseat heatsink with thermal paste |
| Scraping noise | HDD failure | Back up data immediately; replace drive |
| Clicking noise | Fan obstruction | Inspect and clean fans |
| Popping + smoke | Capacitor failure | Power off immediately; inspect for blown caps |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| POST beep codes | Manufacturer-specific; reference documentation; do not memorize |
| BSoD stop code | Search at windows.com/stopcode; caused by hardware/driver/app failure |
| Safe Mode | Bypass BSoD during boot to troubleshoot drivers |
| Blank screen troubleshooting | Connections → input → brightness → swap monitor → VGA mode |
| No power | Test outlet, cord, PSU DC outputs with multimeter |
| Task Manager | First tool for sluggish performance diagnosis |
| Overheating | Check fans, heatsink, thermal paste; use HW Monitor |
| Random shutdown | Usually thermal protection — check cooling system |
| CMOS battery | Failure = date/time prompt at every boot; easy battery swap |
| CMOS battery reset | Does NOT reset BIOS config on modern systems |
| Capacitor bulge | Warning sign of imminent failure; popping + smoke = failed cap |
| Reliability Monitor | Hidden Windows tool; history of app crashes with dates/times |
| HW Monitor | Third-party temperature monitoring at cpuid.com |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Hardware Troubleshooting**, covering POST errors, BSoD, blank screens, power issues, sluggish performance, overheating, noise diagnosis, capacitor failure, and CMOS battery failure.
