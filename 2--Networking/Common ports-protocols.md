# CompTIA A+ 220-1201 — Common Ports & Protocols

> **Exam Domain Reference** | Core 1 (220-1201) — Networking (Domain 2)  
> Topics: FTP, SSH, Telnet, SMTP, DNS, DHCP, HTTP/HTTPS, POP3, IMAP, SMB, LDAP, RDP — port numbers and use cases

> **Exam Priority:** Port numbers and their associated protocols are **directly tested** on the A+ exam. Know the port number, the protocol name, the transport (TCP/UDP), and what the protocol is used for.

---

## Table of Contents

1. [Quick Reference — All Ports](#quick-reference--all-ports)
2. [Protocol Deep Dives](#protocol-deep-dives)
   - [FTP — File Transfer Protocol](#ftp--file-transfer-protocol)
   - [SSH — Secure Shell](#ssh--secure-shell)
   - [Telnet](#telnet)
   - [SMTP — Simple Mail Transfer Protocol](#smtp--simple-mail-transfer-protocol)
   - [DNS — Domain Name System](#dns--domain-name-system)
   - [DHCP — Dynamic Host Configuration Protocol](#dhcp--dynamic-host-configuration-protocol)
   - [HTTP & HTTPS](#http--https)
   - [POP3 — Post Office Protocol v3](#pop3--post-office-protocol-v3)
   - [IMAP — Internet Message Access Protocol](#imap--internet-message-access-protocol)
   - [SMB / CIFS & NetBIOS](#smb--cifs--netbios)
   - [LDAP / LDAPS](#ldap--ldaps)
   - [RDP — Remote Desktop Protocol](#rdp--remote-desktop-protocol)
3. [Key Takeaways](#key-takeaways)

---

## Quick Reference — All Ports

| Port | Protocol | Transport | Purpose |
|---|---|---|---|
| **20** | FTP (Data) | TCP | Active file data transfer |
| **21** | FTP (Control) | TCP | FTP commands / administration |
| **22** | SSH | TCP | Encrypted remote command line |
| **23** | Telnet | TCP | Unencrypted remote command line (legacy) |
| **25** | SMTP | TCP | Sending email between servers |
| **53** | DNS | UDP | Domain name to IP resolution |
| **67** | DHCP (Server) | UDP | Server assigns IP to client |
| **68** | DHCP (Client) | UDP | Client requests IP from server |
| **80** | HTTP | TCP | Unencrypted web traffic |
| **110** | POP3 | TCP | Download email to local client |
| **137** | NetBIOS Name | UDP | NetBIOS name resolution |
| **139** | NetBIOS Session | TCP | NetBIOS file/session transfer |
| **143** | IMAP | TCP | Email access with server sync |
| **389** | LDAP | TCP | Directory services access |
| **443** | HTTPS | TCP | Encrypted web traffic |
| **445** | SMB (Direct) | TCP | Windows file/printer sharing (modern) |
| **3389** | RDP | TCP | Remote desktop access (Windows) |

---

## Protocol Deep Dives

### FTP — File Transfer Protocol

**Ports:** TCP 20 (data), TCP 21 (control)

FTP is a general-purpose file transfer protocol supported across many operating systems.

- **Port 21** — Control channel: login, commands, directory listing
- **Port 20** — Data channel: actual file transfer (active mode)
- Supports **authentication** (username/password) or **anonymous login** (open to anyone)
- Full-featured: transfer files, list directories, add, delete, rename files

> **Exam Tip:** FTP uses **two** ports — 20 for data, 21 for control. Know both.

---

### SSH — Secure Shell

**Port:** TCP 22

SSH provides an **encrypted** command-line connection to remote devices.

- Used by administrators to manage servers and network devices remotely
- Replaces the older, insecure Telnet protocol
- All data — including username/password — is encrypted in transit
- Available on virtually all modern operating systems

---

### Telnet

**Port:** TCP 23

Telnet provides remote command-line access but with **no encryption** — all data is sent in plaintext.

- Functionally identical to SSH (command line, login, remote administration)
- Major security risk: credentials and data are visible to anyone intercepting the traffic
- Still found on very old or legacy devices that do not support SSH
- Most organizations **block Telnet** and require SSH instead

> **Exam Tip:** SSH = encrypted (use this). Telnet = unencrypted (avoid). Both provide remote CLI access.

---

### SMTP — Simple Mail Transfer Protocol

**Port:** TCP 25

SMTP is the protocol used to **send** email from one mail server to another.

- Also used by email clients to submit outgoing mail to their mail server
- Works alongside POP3 or IMAP (which handle receiving email)
- Configured on both mail servers and local email clients

---

### DNS — Domain Name System

**Port:** UDP 53

DNS translates human-readable domain names into IP addresses.

- Without DNS, users would need to memorize IP addresses for every website
- Example: `www.example.com` → `93.184.216.34`
- Organizations run **multiple DNS servers** for redundancy — a DNS outage makes the internet effectively unreachable for users

---

### DHCP — Dynamic Host Configuration Protocol

**Ports:** UDP 67 (server), UDP 68 (client)

DHCP automatically assigns network configuration to devices when they connect.

**What DHCP assigns:**
- IP address
- Subnet mask
- Default gateway
- DNS server addresses

**How it works:**
1. Device connects to the network and broadcasts a DHCP request (UDP 68)
2. DHCP server responds with configuration (UDP 67)
3. Device receives a **lease** — a temporary assignment of the IP address
4. Lease is renewed or the IP is returned to the pool when expired

**DHCP Reservations:** Administrators can bind a specific IP to a device's MAC address so it always receives the same IP (useful for printers, servers).

---

### HTTP & HTTPS

**Ports:** TCP 80 (HTTP), TCP 443 (HTTPS)

These protocols power web browsing.

| Protocol | Port | Encryption | Use |
|---|---|---|---|
| HTTP | TCP 80 | None (plaintext) | Standard web traffic |
| HTTPS | TCP 443 | Yes (TLS/SSL) | Secure web traffic |

The vast majority of modern websites use HTTPS. HTTP traffic on port 80 still exists but is increasingly rare and generally discouraged for any sensitive content.

---

### POP3 — Post Office Protocol v3

**Port:** TCP 110

POP3 is used by email clients to **download** messages from a mail server.

- Downloads email to the local device and typically **removes it from the server**
- Simple protocol with limited features
- Does not synchronize across multiple devices — an email read on one device won't show as read on another

---

### IMAP — Internet Message Access Protocol

**Port:** TCP 143

IMAP is a more modern email retrieval protocol that **keeps email on the server** and synchronizes across all devices.

- Create folders, move messages, mark as read — all changes sync across every client
- Better suited for users accessing email from multiple devices (phone, laptop, tablet)
- Generally preferred over POP3 for modern use

> **Exam Tip — POP3 vs. IMAP:**  
> POP3 (110) = downloads and removes from server, no sync.  
> IMAP (143) = stays on server, syncs across all devices.

---

### SMB / CIFS & NetBIOS

SMB (Server Message Block), also called CIFS (Common Internet File System), is used by Windows for file sharing, printer access, and inter-device communication.

**Ports:**

| Port | Transport | Protocol | Purpose |
|---|---|---|---|
| 137 | UDP | NetBIOS Name Service | Name resolution (legacy, like DNS for NetBIOS) |
| 139 | TCP | NetBIOS Session | File/session transfer (legacy) |
| 445 | TCP | SMB Direct (NetBIOS-less) | Modern Windows file/printer sharing |

Modern Windows devices communicate directly over TCP/IP using **port 445**, bypassing the older NetBIOS ports 137 and 139.

---

### LDAP / LDAPS

**Port:** TCP 389 (LDAP), TCP 636 (LDAPS — secure)

LDAP (Lightweight Directory Access Protocol) provides access to **directory services** — centralized databases of users, devices, and resources on a network.

**Directory structure example:**
```
Organization: Messer Studios
├── Organizational Unit: Production
├── Organizational Unit: Support
│   └── Common Name: Sam
│   └── Common Name: Daniel
└── Organizational Unit: Engineering
    └── Resource: tech docs
```

- Most commonly used by **Microsoft Active Directory**
- Used for authentication, user lookups, and resource access
- LDAPS (port 636) adds encryption to the LDAP connection

---

### RDP — Remote Desktop Protocol

**Port:** TCP 3389

RDP allows administrators and support staff to **view and control a remote Windows desktop** across the network.

- Primarily used to access Windows systems remotely
- Can control the full desktop or run a single remote application
- RDP clients are available for Windows, macOS, Linux, iOS, Android, and more

> **Use case:** A technician supporting a remote user can use RDP to see exactly what's on their screen and make changes directly — no physical visit required.

---

## Key Takeaways

| Port(s) | Protocol | Transport | Remember This |
|---|---|---|---|
| 20 / 21 | FTP | TCP | 20 = data, 21 = control |
| 22 | SSH | TCP | Encrypted CLI; always prefer over Telnet |
| 23 | Telnet | TCP | Unencrypted CLI; legacy only |
| 25 | SMTP | TCP | Sends email |
| 53 | DNS | UDP | Name-to-IP resolution |
| 67 / 68 | DHCP | UDP | Automatic IP assignment |
| 80 | HTTP | TCP | Unencrypted web |
| 110 | POP3 | TCP | Downloads email; no sync |
| 137 / 139 | NetBIOS | UDP / TCP | Legacy Windows name/file sharing |
| 143 | IMAP | TCP | Email with server sync |
| 389 | LDAP | TCP | Directory services (Active Directory) |
| 443 | HTTPS | TCP | Encrypted web |
| 445 | SMB | TCP | Modern Windows file/printer sharing |
| 3389 | RDP | TCP | Remote Windows desktop access |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Domain 2 — Networking**. Memorizing these port numbers and understanding their associated protocols is directly tested on the exam and essential for real-world network troubleshooting and firewall configuration.
