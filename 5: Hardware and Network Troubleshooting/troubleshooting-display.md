# CompTIA A+ 220-1201 — Troubleshooting Display Issues

> **Exam Domain Reference** | Core 1 (220-1201) — Hardware (Domain 3)  
> Topics: No signal, input selection, projector bulbs, fuzzy images, burn-in/image sticking, dead pixels, flashing screens, color problems, audio from monitor, dim display, scaling

---


---

## No Signal / Black Screen

**Troubleshoot in order:**

1. **Check video cable** — both ends firmly seated (HDMI, DisplayPort, DVI, VGA)
2. **Check monitor power cable** — monitor must be powered on
3. **Check input selection** — monitor must be set to the input the cable is connected to (HDMI ≠ VGA)
4. **Check brightness/contrast** — screen may be on but too dim to see
5. **Swap with known-good monitor** — if problem persists, issue is with the computer, not the monitor
6. **Video boots then goes black** → try **VGA mode** (press F8 during boot) — uses generic video driver compatible with all monitors

---

## LCD Projector Bulb Issues

LCD projectors use a **metal halide bulb** that reaches ~1,000°C during operation.

**Normal behavior:**
- Fan runs continuously during use — keeps bulb cool
- Fan continues running **after shutdown** — gradually cools the bulb to prevent damage

**Bulb failure:**
- Dim or no image output
- Replace the bulb (usually user-replaceable and modular)
- When replacing a ceiling-mounted projector bulb, also **clean dust and replace air filters** to ensure adequate cooling

**Premature shutdown:** Temperature sensors trigger automatic shutdown if the projector overheats — usually caused by clogged air filters or fan failure.

---

## Fuzzy / Incorrect Resolution

**Cause:** Operating system resolution does not match the display's **native resolution**.

- LCDs have a fixed pixel grid — native resolution is always the sharpest setting
- Running at a non-native resolution causes the monitor to scale the image, resulting in fuzzy text and graphics

**Fix:** Set OS display resolution to match the monitor's native resolution.

**Alternative:** Use a whole-number multiple of the native resolution if native is not desired.

---

## Burn-In / Image Sticking

**Burn-in (also called image sticking on LCD):** A static image displayed for an extended period leaves a ghost image visible on the screen.

**Prevention:**
- Enable **pixel shift** in monitor settings (slightly moves the image a few pixels to prevent static display)
- Use a screensaver or turn off the display when idle

**Possible recovery (LCD):** Display a **white screen for an extended period** (e.g., overnight) — may reduce image sticking.

> **Note:** Burn-in was historically a CRT problem; image sticking on modern LCDs is less severe but still occurs.

---

## Dead Pixels

A **dead pixel** is a permanently dark (black) pixel — always off, never lights up.

**Cause:** Manufacturing defect.

**Diagnosis:** Clean the screen first — dirt or smudges can resemble dead pixels.

**Fix:** Dead pixels **cannot be repaired**. The only solution is to replace the entire display.

> **Practical note:** A dead pixel in a corner may be tolerable; one in the center of the screen typically warrants replacement under warranty.

---

## Flashing / Flickering Screen

**Troubleshooting steps:**

1. **Check cable connections** — reseat or replace the video cable
2. **Swap monitor** — test with a known-good monitor
3. **Check OS display settings** — ensure resolution and refresh rate are compatible with the monitor's specs
4. **Match native resolution** — wrong resolution/refresh rate can cause flickering
5. **Disable hardware acceleration** — GPU hardware acceleration can cause flickering in some configurations
6. **Update or roll back video driver** — incorrect driver can cause screen issues

**Extensive flickering/lines across full screen:** Likely hardware failure of the display — replace the monitor.

---

## Incorrect Colors

**Symptoms:** Colors appear too blue, green, or otherwise incorrect.

**Fixes:**
1. Adjust **tint/color settings** in monitor OSD (On-Screen Display)
2. Use **factory reset** option in monitor settings to return to default color profile
3. Check OS **color settings** — confirm tint/calibration is not skewed
4. Disable **Night Mode / Night Light** (OS feature that shifts colors warm/blue based on time of day)

---

## No Audio from Monitor

Many monitors include built-in speakers.

**Troubleshooting:**
1. Check **monitor volume control** — may be muted or turned down
2. Verify **audio input matches video input** — if video is HDMI, audio source should also be set to HDMI
3. Check OS audio output settings — confirm audio is routed to the HDMI/DisplayPort output
4. If monitor has analog audio input — configure OS to send video via HDMI and audio via analog separately

---

## Dim Display

**Causes and fixes:**

| Cause | Fix |
|---|---|
| Brightness/contrast setting too low | Adjust in monitor OSD |
| OS auto-dimming feature | Disable in OS display settings |
| Laptop unplugged → power save mode | Connect to AC power or adjust power plan |
| Driver brightness setting | Check GPU driver control panel |
| Backlight failure (partial or full) | Replace backlight components or entire display |

**Backlight failure symptom:** Part of the screen is bright, other parts are dark — indicates a partial backlight failure.

---

## Display Scaling Issues

**Issue 1 — Image too small on screen:**
- Enable **scaling** in OS display settings to expand image to fill the monitor

**Issue 2 — 4K resolution with tiny icons/text:**
- Set scaling percentage in OS (e.g., 100% → 200% → 300%) to enlarge UI elements while maintaining native resolution
- Keeps sharpness of native resolution while making text/icons readable

---

## Extensive Screen Artifacts / Lines

Persistent lines or blocks across the screen = likely hardware failure of the LCD panel.

**Before replacing:**
1. Swap the display cable
2. Try a different video adapter/GPU if available
3. Update or reinstall the video driver

If artifacts persist after all these steps → replace the display.

**Test patterns:** Technicians use test patterns to evaluate sharpness, color accuracy, and identify the location of display defects before deciding to repair vs. replace.

---

## Troubleshooting Quick Reference

| Symptom | Likely Cause | First Fix |
|---|---|---|
| Black screen / no signal | Cable disconnected, wrong input | Check connections; check input selection |
| Works during boot, black at Windows | Video driver issue | Boot in VGA mode (F8) |
| Dim image, can see with flashlight | Backlight failure | Replace backlight / monitor |
| Projector suddenly shuts off | Overheating | Clean filters; check fans |
| Projector dim output | Bulb dying | Replace bulb |
| Fuzzy text | Wrong resolution | Set to native resolution |
| Ghost image / old text visible | Burn-in / image sticking | Enable pixel shift; try white screen overnight |
| Single black dot that won't go away | Dead pixel | Clean screen first; if confirmed → replace monitor |
| Screen flashes on and off | Loose cable or bad cable | Reseat/replace video cable |
| Colors wrong (too blue/green) | Color settings or Night Mode | Adjust monitor OSD; disable Night Mode |
| No sound from monitor | Volume muted, wrong audio input | Check volume; match audio to video input |
| Dim display (laptop) | Power saving throttle | Plug in AC; adjust power plan |
| Small image on large screen | Scaling disabled | Enable scaling in OS display settings |
| Tiny icons on 4K screen | Scaling at 100% | Increase scaling % in OS display settings |
| Lines/blocks across full screen | LCD hardware failure | Swap cable/GPU first; then replace display |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| No signal | Check cable, power, input selection — in that order |
| VGA mode | F8 during boot; generic driver; works with any monitor |
| Projector bulb | Metal halide; ~1,000°C; fan cools after shutdown; user-replaceable |
| Native resolution | Always the sharpest setting for an LCD |
| Non-native resolution | Causes fuzzy/blurry text and graphics |
| Burn-in / image sticking | Static image leaves ghost; use pixel shift to prevent |
| Dead pixel | Always black; cannot be repaired; replace monitor |
| Flickering | Cable, driver, hardware acceleration, or hardware failure |
| Hardware acceleration | Disable if causing display artifacts |
| Incorrect colors | Adjust monitor OSD or disable Night Mode |
| Dim display | Check backlight — partial failure = some areas bright, others dark |
| Scaling | Adjusts UI size without changing resolution |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Hardware Troubleshooting**, covering display issues including no signal, projector bulbs, resolution/blur, burn-in, dead pixels, flickering, color problems, audio, dim displays, and scaling.
