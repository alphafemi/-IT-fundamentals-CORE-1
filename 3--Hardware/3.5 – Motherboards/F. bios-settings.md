# CompTIA A+ 220-1201 — BIOS Settings & Configuration

> **Exam Domain Reference** | Core 1 (220-1201) — Hardware (Domain 3)  
> Topics: Accessing BIOS, fast startup, boot order, USB control, fan/cooling, Secure Boot, BIOS passwords, CMOS, jumper reset, temperature monitoring, virtualization (VT/AMD-V)

---


## Accessing the BIOS

Press a specific key during POST to enter BIOS setup. Common keys:
- **Delete**, **F1**, **F2**
- Key combinations such as **Ctrl+S** or **Ctrl+Alt+S**

**Windows Fast Startup problem:** Windows 10/11 does not fully power down by default — it uses **fast startup** to partially hibernate the system. This bypasses the BIOS entry window.

**How to force a full restart for BIOS access:**
- Hold **Shift** while clicking Restart
- Go to **Settings → Update & Security → Recovery → Advanced Startup → Restart Now**
- Use **msconfig** (System Configuration) to modify startup behavior
- **Interrupt the boot process 3 times in a row** — the 4th boot will start from the beginning

> **Safety reminder:** Always document BIOS changes before making them — a photo of the screen is quick and effective. A misconfigured BIOS can prevent the system from booting.

---

## Boot Order Configuration

The BIOS boot order tells the system which storage device to try first when loading an operating system.

**Common boot devices:**
- SATA drives (HDD/SSD)
- M.2 drives
- USB drives
- Network (PXE boot)
- Optical drives

**How to configure:** In BIOS, navigate to the **Startup** or **Boot** menu → arrange devices in the desired sequence (top = first tried).

**Common scenarios:**
- Move a **USB drive** to the top to boot a live OS or installer
- Move an **M.2 SSD** up after installing a new OS to that drive

---

## USB Configuration

The BIOS can **enable or disable USB ports** — useful for security hardening.

**Why disable USB:**
- Prevents unauthorized USB storage devices from being connected
- Real-world example: In 2008, the **U.S. Department of Defense banned USB flash drives for 15 months** after the **SillyFDC worm** spread through DOD systems via an infected USB drive

**BIOS USB options typically include:**
- Enable/disable specific ports or all USB ports
- Control USB storage vs. non-storage devices
- Set USB protocol support levels

---

## Fan & Cooling Settings

Motherboards include temperature sensors and **integrated fan controllers** — all configurable in BIOS.

**Common fan control modes:**

| Mode | Description |
|---|---|
| **Best Performance** | Fans run fast; maximum cooling |
| **Best Experience** | Fans optimized to minimize noise |
| **Full Speed** | All fans run at 100% constantly |

- Fans connect directly to the motherboard (labeled CPU_FAN1, SYS_FAN, etc.)
- The BIOS monitors temperatures in real time and adjusts fan speeds automatically
- Data center environments typically use **Full Speed** for maximum cooling

---

## Secure Boot

**Secure Boot** is a UEFI feature (not available in legacy BIOS) that uses **digital signatures** to verify software before it runs during startup.

**What Secure Boot verifies:**
1. **BIOS firmware** — checks the manufacturer's public key against the firmware's digital signature; prevents unauthorized BIOS overwrites
2. **Bootloader** — verifies the bootloader's digital signature against a trusted certificate
3. **Operating system** — verifies the OS has a known, trusted digital signature

**If verification fails:** Secure Boot halts the boot process — preventing malware from loading before the OS.

**Old OS issue:** Legacy or unsigned operating systems may not have a recognized digital signature. In this case, Secure Boot must be **temporarily disabled** to run the old OS.

**BIOS location:** Security → Secure Boot → Enable/Disable + manage keys

---

## BIOS Passwords

Two types of BIOS passwords provide different levels of protection:

| Password Type | Also Called | What It Does |
|---|---|---|
| **Boot password** | User password, Power-on password | Requires a password before the system will boot any OS |
| **Supervisor password** | BIOS password | Prevents access to BIOS configuration without the correct password |

**Use case:** An admin disables USB ports in the BIOS for security, then sets a supervisor password to prevent users from re-enabling them.

**If password is forgotten:** A full BIOS reset is required. The process varies by manufacturer — typically involves a physical jumper on the motherboard.

---

## CMOS & BIOS Storage

**CMOS (Complementary Metal Oxide Semiconductor)** is the historical term for the volatile memory that stored BIOS configuration — kept alive by a small coin-cell battery on the motherboard.

**Modern reality:**
- BIOS firmware (the software itself) is stored in **flash memory** on the motherboard
- BIOS configuration settings are also stored in **non-volatile flash memory**
- A battery is **no longer required** to maintain BIOS settings

> **Exam Tip:** "CMOS" is still used as a shorthand term for BIOS settings in older documentation and conversation — but in modern systems, removing the CMOS battery does **not** reset the BIOS configuration.

**To actually reset BIOS settings** on a modern system → use a physical jumper on the motherboard (see below).

---

## Resetting the BIOS

Since BIOS configuration is stored in non-volatile flash, a battery removal won't reset it. A **physical jumper** is required.

**Process (varies by manufacturer):**
1. Power off the system and unplug it
2. Locate the BIOS reset jumper on the motherboard (often labeled **CLR_CMOS**, **CLRTC**, or similar)
3. Move the jumper to the reset position (or briefly short the pins)
4. Power on the system — BIOS resets to factory defaults
5. Return the jumper to its normal position

> Check the motherboard manual for the exact jumper location and procedure.

---

## Temperature Monitoring

The BIOS provides a built-in temperature monitoring view — no OS or third-party software needed.

**Sensors available:**
- CPU temperature
- Memory temperature
- Motherboard/system temperature
- Individual component sensors

**Use case:** After installing new hardware, check the BIOS temperature monitor before booting the OS to confirm adequate cooling.

---

## Virtualization Settings

Hardware virtualization support is built into the CPU and must be **enabled in BIOS** before hypervisors can use it.

| CPU Manufacturer | BIOS Setting Name |
|---|---|
| **Intel** | Intel Virtualization Technology (VT / VT-x) |
| **AMD** | AMD Virtualization (AMD-V) / Secure Virtual Machine (SVM) |

**BIOS location:** Advanced → CPU Setup → enable virtualization option

Enabling hardware virtualization makes virtual machines run faster and more stably than software-only emulation.

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| BIOS access keys | Delete, F1, F2 — or key combos; timing is critical during POST |
| Fast startup | Windows 10/11 feature that bypasses full shutdown; prevents BIOS key entry |
| Boot order | Configured in BIOS Startup menu; determines which device is tried first |
| USB disable | BIOS can disable USB ports; DoD did this in 2008 after SillyFDC worm |
| Fan control | Motherboard sensors + BIOS fan controller; modes: performance / experience / full speed |
| Secure Boot | UEFI only; verifies firmware, bootloader, OS with digital signatures |
| Boot password | Prevents OS from loading without a password |
| Supervisor password | Prevents BIOS config access without a password |
| CMOS | Historical term for BIOS settings memory; now stored in flash (no battery needed) |
| BIOS reset | Requires physical jumper on motherboard; removing battery does NOT work on modern systems |
| Temperature monitoring | Viewable in BIOS without OS or third-party tools |
| Intel VT / AMD-V | CPU virtualization; must be enabled in BIOS for hypervisors to use hardware acceleration |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Hardware Domain**, covering BIOS/UEFI configuration settings including boot order, USB control, Secure Boot, passwords, CMOS, BIOS reset, temperature monitoring, and virtualization enablement.
