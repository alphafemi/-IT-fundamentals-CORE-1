# CompTIA A+ 220-1201 — TPM & HSM

> **Exam Domain Reference** | Core 1 (220-1201) — Hardware (Domain 3)  
> Topics: Trusted Platform Module (TPM), Hardware Security Module (HSM), encryption keys, root of trust, BitLocker

---



## Why Hardware Encryption Matters

Encryption protects data using well-known, public standards — the algorithm isn't the secret. The **cryptographic key** is the secret. Without the correct key, encrypted data is unreadable.

**The key protection problem:** If the data is encrypted but the key is stored on the same unprotected system, an attacker who gains access to the system gets the key and the data. The solution is to store and protect cryptographic keys in dedicated, tamper-resistant hardware.

---

## TPM — Trusted Platform Module

A **TPM (Trusted Platform Module)** is a standardized hardware chip dedicated to cryptographic functions and secure key storage — built into or attached to the motherboard.

- Managed by standards from the **TCG (Trusted Computing Group)**
- Available as TPM 1.2 (older) or **TPM 2.0** (current standard)
- Can be built directly into the motherboard, or installed as a separate module via a pin header

### What's Inside a TPM

| Component | Function |
|---|---|
| **Cryptographic processor** | Performs encryption/decryption in hardware |
| **Random number generator** | Generates cryptographically secure random numbers |
| **Key generator** | Creates cryptographic keys |
| **Persistent memory** | Stores keys burned in at manufacture — unique to this TPM |
| **Versatile memory** | Stores additional keys and data |
| **Password protection** | Prevents unauthorized access to stored keys |

### What TPM Enables

**Full-disk encryption (e.g., BitLocker):**
- The TPM holds the encryption key for the drive
- If the drive is removed and placed in another computer, it cannot be decrypted — the key stays in the original TPM
- Ties the encrypted data to a specific physical machine

**Root of trust:**
- The TPM contains a unique key that identifies the specific hardware
- Used to verify across a network that the device connecting is genuinely the expected physical machine
- Can detect if hardware or firmware has changed since last verified

**Remote attestation:**
- The TPM can report to a remote system that the local hardware configuration is unchanged — confirming the device's integrity

### TPM in the BIOS

TPM settings are found under **Security** in the BIOS/UEFI:
- Enable or disable TPM functionality
- Clear TPM data (removes stored keys — use with caution)
- Configure TPM version (1.2 vs. 2.0 on compatible hardware)

> **Note:** Windows 11 requires **TPM 2.0** to install.

---

## HSM — Hardware Security Module

An **HSM (Hardware Security Module)** is a dedicated high-performance device for managing cryptographic keys at scale — designed for data centers and enterprise environments.

**Why HSMs exist:** A TPM secures one device. An organization with hundreds or thousands of servers needs a centralized, high-assurance solution for managing all those keys.

**HSM capabilities:**
- Centralized, secure storage for keys from many systems
- **Hardware cryptographic acceleration** — offloads encryption/decryption from software, improving performance
- Protects keys for web servers, certificate authorities (CAs), databases, and more
- Tamper-resistant hardware; FIPS 140-2/3 certified in enterprise deployments

**HSM form factors:**

| Type | Use Case |
|---|---|
| **Data center appliance** | High-end server with cryptographic hardware; manages keys for entire infrastructure |
| **Personal/portable HSM** | Lightweight USB or card device; stores individual keys (e.g., cryptocurrency hardware wallets) |

---

## TPM vs. HSM Comparison

| Feature | TPM | HSM |
|---|---|---|
| **Scope** | Single device | Many devices / entire infrastructure |
| **Location** | Built into motherboard or module | Dedicated appliance or portable device |
| **Primary use** | Protect local device encryption keys | Centralize and manage keys across many systems |
| **Cryptographic acceleration** | No | Yes (hardware-accelerated) |
| **Example use** | BitLocker, phone screen lock, full-disk encryption | Web server TLS keys, certificate authority keys |
| **Scale** | One system | Enterprise / data center |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| TPM | Hardware chip for cryptographic functions and key storage; unique per device |
| TPM managed by | TCG — Trusted Computing Group |
| TPM 2.0 | Required for Windows 11 |
| Persistent memory | Stores keys burned in at manufacture; unique to that TPM |
| Root of trust | TPM uniquely identifies a physical machine; can't be cloned |
| BitLocker + TPM | Drive encrypted with key stored in TPM; removing drive to another PC won't decrypt it |
| Remote attestation | TPM can verify device integrity to a remote system |
| TPM in BIOS | Found under Security; enable/disable; clear stored data |
| HSM | Hardware Security Module; centralized key management for many systems |
| HSM acceleration | Offloads cryptographic processing from software to dedicated hardware |
| Personal HSM | Portable device (e.g., cryptocurrency wallet); stores personal keys |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Hardware Domain**, covering TPM and HSM technologies, their components, use cases, and the difference between single-device and enterprise-scale cryptographic key management.
