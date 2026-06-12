# CompTIA A+ 220-1201 — Troubleshooting Printers

> **Exam Domain Reference** | Core 1 (220-1201) — Hardware (Domain 3)  
> Topics: Test pages, bad output, garbled prints, paper jams, pickup rollers, print spooler, grinding noises, finishing issues, orientation, paper trays, network connectivity

---

## Table of Contents

1. [Starting Point — Print Test Pages](#starting-point--print-test-pages)
2. [Bad Output Quality](#bad-output-quality)
3. [Garbled / Corrupt Output](#garbled--corrupt-output)
4. [Paper Jams](#paper-jams)
5. [Paper Feed Issues](#paper-feed-issues)
6. [Print Spooler Issues](#print-spooler-issues)
7. [Grinding Noises](#grinding-noises)
8. [Finishing Issues (Stapling, Hole Punch, Collating)](#finishing-issues-stapling-hole-punch-collating)
9. [Wrong Orientation (Portrait / Landscape)](#wrong-orientation-portrait--landscape)
10. [Paper Tray Issues](#paper-tray-issues)
11. [Network Connectivity for Printers](#network-connectivity-for-printers)
12. [Troubleshooting Quick Reference](#troubleshooting-quick-reference)
13. [Key Takeaways](#key-takeaways)

---

## Starting Point — Print Test Pages

Before blaming the printer or the application, isolate the problem layer:

| Test | What It Tests | How |
|---|---|---|
| **Windows test page** | OS + printer driver | Printer Properties → Print Test Page |
| **Printer-level test page** | Printer hardware only (bypasses OS and driver) | Use button sequence on the printer itself |

- **If printer test page looks good but Windows test fails** → driver or OS issue
- **If printer test page is also bad** → hardware issue with the printer
- **If both test pages are fine but application output is bad** → application is sending bad data

---

## Bad Output Quality

| Symptom | Likely Cause | Fix |
|---|---|---|
| Single vertical line down the page (inkjet) | Dirty print head | Clean the print head |
| Single vertical line down the page (laser) | Scratch on photosensitive (OPC) drum | Replace toner cartridge / drum |
| Faded or light output | Low toner or ink | Replace toner/ink cartridge |
| Double images / ghosting (laser) | OPC drum not cleaning properly | Clean drum; check fuser; replace cartridge |
| Speckles on page | Drum not cleaning properly | Same as ghosting — cleaning issue |

**Ghosting explanation:** The laser drum picks up toner, transfers to paper, then is cleaned. If cleaning fails, residual toner from the previous rotation leaves a faint repeated image (ghost) lower on the page.

---

## Garbled / Corrupt Output

Unreadable or random characters on the page.

**Possible causes:**
- Wrong printer driver installed — driver sends wrong page description language (e.g., sending PostScript to a PCL-only printer)
- Corrupted print driver
- Application sending malformed data

**Diagnosis:**
1. Run a printer-level test — if this is also garbled, the hardware is the problem
2. Run a Windows/driver test page — if this is garbled but the printer test is fine, driver/OS is the problem
3. Try printing from a different application — if only one app garbles, the app is the problem

**Fix:** Install the correct driver for the printer model; verify PCL vs. PostScript compatibility.

---

## Paper Jams

- **Do NOT forcefully pull jammed paper** — this tears the paper and leaves fragments inside
- Open the printer cover first — many printers release the paper path mechanism when opened, making jam removal easier
- After clearing a jam, check thoroughly that **no paper fragments remain** inside the paper path

---

## Paper Feed Issues

| Symptom | Cause | Fix |
|---|---|---|
| No paper feeds | Worn or dirty pickup rollers | Clean rollers; replace during scheduled maintenance |
| Multiple pages feed at once | Worn pickup rollers | Replace pickup rollers (included in maintenance kits) |
| Creases in output | Wrong paper weight; paper path obstruction | Use manufacturer-recommended paper weight |

**Pickup rollers:** Wear over time; included in manufacturer maintenance kits for replacement at scheduled intervals.

---

## Print Spooler Issues

The **print spooler** is a Windows service that acts as the intermediary between applications and the printer. Applications send jobs to the spooler; the spooler queues and sends them to the printer.

**Problem:** A corrupted print job can freeze or crash the spooler — all subsequent jobs in the queue stop printing.

**Windows spooler behavior:**
- 1st failure → auto-restarts
- 2nd failure → auto-restarts
- 3rd failure → stops completely; requires administrator intervention

**Troubleshooting:**
1. Check **Windows Event Viewer → Windows Print Service** for error details
2. Identify and **delete the corrupted print job** from the queue
3. Or move the problem job to the end of the queue and let others print first
4. Restart the Print Spooler service manually if needed (Services.msc)

---

## Grinding Noises

Printers should not grind. Grinding indicates a mechanical problem:

- Paper jam caught in the mechanism
- Ink cartridge not properly seated — carriage rubs against it during movement
- Worn or broken internal component (may require a specialist)

**Action:** Check for jams and reseat all cartridges. If grinding continues, consult manufacturer documentation or a printer specialist.

---

## Finishing Issues (Stapling, Hole Punch, Collating)

High-end printers include finishing options: collating, stapling, binding, hole punching.

**Staple jam:**
- Remove the jam per the printer's documentation — process varies by model
- Clear all staple fragments before resuming

**Hole punch misalignment:**
- Hole position is defined by the application and the driver
- Update the print driver if holes are not in the expected location
- Confirm the correct paper size is configured in both the application and driver

---

## Wrong Orientation (Portrait / Landscape)

Output prints in the wrong orientation (expected portrait, got landscape).

**Troubleshooting:**
1. Check **print driver default orientation** settings
2. Check the **application's print settings** when initiating the job
3. Update the print driver — orientation bugs are fixed in driver updates
4. Set the **default orientation on the printer itself** — affects all future jobs from all sources

---

## Paper Tray Issues

Most office printers have multiple paper trays for different paper types and sizes.

**Common issues:**
- Sending letter-size output to a legal-size tray (or vice versa)
- Print driver tray configuration doesn't match what's physically loaded

**Best practice:**
- Confirm the driver's list of available trays matches the trays physically installed on the printer
- Specify the tray and paper size in the driver properties
- If paper size mismatches, the printer will display an error and pause

---

## Network Connectivity for Printers

Network printers require standard network troubleshooting in addition to printer-specific steps.

**Check:**
1. **Wired vs. wireless** — determine which connection type is in use (affects troubleshooting path)
2. **Link light** on the Ethernet port — confirms physical connection
3. **IP configuration** — IP address, subnet mask, default gateway, DNS
4. **Print server status** — most printers have a built-in print server with a web management interface; restart it if needed
5. **Printer web interface** — view and manage the print queue; stop/start the print server; check network status

---

## Troubleshooting Quick Reference

| Symptom | Likely Cause | First Action |
|---|---|---|
| Vertical line on every page | Laser: scratched drum; Inkjet: dirty head | Laser: replace drum; Inkjet: clean print head |
| Faded/light output | Low toner or ink | Replace cartridge |
| Ghost/double image | Drum not cleaning | Check fuser/drum; run cleaning cycle |
| Garbled output | Wrong driver / wrong PDL | Install correct driver; check PCL vs. PostScript |
| Paper jam | Paper caught in mechanism | Open cover; remove gently; check for fragments |
| No paper feeds | Worn pickup rollers | Clean or replace rollers |
| Multiple pages feed | Worn pickup rollers | Replace rollers |
| Creases in output | Wrong paper weight | Use manufacturer-specified paper weight |
| Jobs stuck in queue | Spooler frozen/crashed | Delete corrupted job; restart Print Spooler service |
| Grinding noise | Cartridge unseated, jam, or bad part | Reseat cartridge; check for jam; consult manual |
| Staple jam | Staple caught in finishing unit | Remove per printer documentation |
| Wrong orientation | Driver or app setting | Check driver defaults; update driver |
| Paper tray mismatch | Wrong tray selected or wrong paper size | Configure tray in driver; load correct paper |
| Printer not on network | IP config issue, bad cable | Check link light; verify IP config; restart print server |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| Print test page | Isolates whether the issue is hardware, driver/OS, or application |
| Vertical line (laser) | Scratched OPC drum → replace drum/cartridge |
| Vertical line (inkjet) | Dirty print head → clean print head |
| Ghosting / double image | OPC drum cleaning failure |
| Garbled output | Wrong print driver or page description language mismatch |
| Paper jam | Never force-pull torn paper; open printer cover first |
| Pickup rollers | Wear over time; cause no-feed or multi-feed; replaced with maintenance kit |
| Print spooler | Windows service between apps and printer; corrupted job can freeze it |
| Spooler 3rd failure | Stops completely — requires administrator to restart |
| Grinding noise | Unseated cartridge or mechanical failure |
| Orientation issues | Check driver defaults and application settings; update driver |
| Paper tray | Must match paper size in driver to avoid mismatch errors |
| Network printer | Check link light, IP config, print server status |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Hardware Troubleshooting**, covering printer output quality, paper handling, print spooler management, finishing issues, orientation, paper trays, and network printer connectivity.
