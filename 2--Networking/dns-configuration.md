# CompTIA A+ 220-1201 — DNS Records & Configuration

> **Exam Domain Reference** | Core 1 (220-1201) — Networking (Domain 2)  
> Topics: DNS hierarchy, resource records, A/AAAA, CNAME, MX, TXT, SPF, DKIM, DMARC, dig, nslookup

---


## Overview

DNS (Domain Name System) is one of the most critical services on any network. Without it, users would need to memorize IP addresses for every resource they want to reach. DNS translates human-readable names (like `www.professormesser.com`) into IP addresses automatically — and stores many other types of records beyond simple address lookups.

DNS is a **distributed, hierarchical database** — no single server holds the entire database. Portions are spread across thousands of servers worldwide.

> **Caution:** Misconfiguring a DNS record can make services unreachable to the entire internet. Always keep a backup before making changes and know how to revert quickly.

---

## DNS Hierarchy

```
. (Root)
├── .com  (Generic Top-Level Domain / gTLD)
│   └── professormesser
│       ├── www.professormesser.com
│       ├── mail.professormesser.com
│       └── katie.east.professormesser.com
├── .org
├── .net
└── Country Codes (~275 total)
    ├── .us  (United States)
    ├── .ca  (Canada)
    └── .uk  (United Kingdom)
```

**Root servers:** 13 root server clusters exist, made up of over 1,000 physical servers worldwide. These are the starting point for all DNS lookups.

**Generic Top-Level Domains (gTLDs):** `.com`, `.org`, `.net`, `.edu`, `.gov`, etc.

**Country Code TLDs (ccTLDs):** Approximately 275 country-specific domains (`.us`, `.ca`, `.uk`, etc.)

---

## DNS Tools

### dig

`dig` (Domain Information Groper) is the standard DNS query tool on **Linux and macOS** (also installable on Windows).

```bash
# Query the IPv4 address for a hostname
dig www.professormesser.com

# Query TXT records
dig professormesser.com TXT

# Query MX records
dig professormesser.com MX
```

Output includes:
- The question asked
- The answer(s) returned (IP addresses or record data)
- TTL (Time to Live) for each record

### nslookup

`nslookup` is the built-in DNS query tool on **Windows** (also available on Linux/macOS).

```bash
# Basic hostname lookup
nslookup professormesser.com

# Query TXT records
nslookup -type=txt google.com

# Query MX records
nslookup -type=mx professormesser.com
```

Both tools return the same information — use whichever is available on your platform.

---

## DNS Resource Records

DNS stores information in **Resource Records (RR)**. Each record type serves a specific purpose.

### A Record (IPv4)

Maps a **hostname to an IPv4 address**.

```
www.professormesser.com.   IN   A   162.159.246.164
```

| Field | Value |
|---|---|
| Name | `www.professormesser.com` |
| Type | `A` |
| Address | `162.159.246.164` |
| TTL | e.g., 15 minutes |

**TTL (Time to Live):** How long a client caches this record before re-querying. A 15-minute TTL means changes propagate across the internet within 15 minutes.

Multiple A records for the same hostname = **redundancy** (multiple IPs for one domain, like a web server farm).

### AAAA Record (IPv6)

Maps a **hostname to an IPv6 address**. "Quad-A" record.

```
www.example.com.   IN   AAAA   2001:db8::1
```

Same structure as an A record but stores a 128-bit IPv6 address instead of a 32-bit IPv4 address.

### CNAME — Canonical Name

Maps an **alias hostname to a canonical (real) hostname**.

**Example:** One physical server hosts web, FTP, chat, and mail services:

```
mail.example.com.   IN   A      123.12.41.41
www.example.com.    IN   CNAME  mail.example.com.
ftp.example.com.    IN   CNAME  mail.example.com.
chat.example.com.   IN   CNAME  mail.example.com.
```

**Benefit:** If the server's IP changes, only the A record for `mail.example.com` needs updating — all CNAME records point to it and automatically resolve to the new IP.

### MX — Mail Exchanger

Specifies the **mail server responsible for receiving email** for a domain.

```
example.com.   IN   MX   mail.example.com.
mail.example.com.   IN   A   123.12.41.41
```

**How inbound email works:**
1. Remote mail server wants to send email to `james@professormesser.com`
2. It queries DNS for the MX record of `professormesser.com`
3. MX record returns `mail.example.com`
4. A second lookup resolves `mail.example.com` → IP address
5. Remote server delivers email to that IP

> **Exam Tip:** MX records reference a **hostname**, not an IP address directly. A second A record lookup is required to get the IP.

### TXT — Text Records

Stores **human-readable or machine-readable text** in DNS. Used for:
- Domain ownership verification (e.g., Stripe, Google verification)
- Email security records (SPF, DKIM, DMARC)
- Any custom information the domain owner wants to publish

```bash
# View all TXT records for a domain
dig professormesser.com TXT
nslookup -type=txt google.com
```

---

## Email Authentication Records

Three TXT-based record types work together to fight email spoofing and spam:

### SPF — Sender Policy Framework

An SPF record lists **all mail servers authorized to send email on behalf of a domain**.

```
example.com.   IN   TXT   "v=spf1 ip4:203.0.113.1 include:mailprovider.com ~all"
```

**How it works:**
- When a server receives email claiming to be from `@professormesser.com`, it checks the SPF record
- If the sending server's IP is **in the SPF list** → email is from an authorized source
- If the sending server's IP is **not in the SPF list** → likely spoofed or unauthorized

### DKIM — DomainKeys Identified Mail

DKIM uses a **cryptographic digital signature** to verify that an email genuinely originated from the claimed domain.

```
selector._domainkey.example.com.   IN   TXT   "v=DKIM1; k=rsa; p=<public key>"
```

**How it works:**
1. The domain's email server signs all outgoing messages with a **private key**
2. The **public key** is published in a DNS TXT record
3. The receiving mail server retrieves the public key from DNS
4. It verifies the digital signature on the message
5. A valid signature confirms the message was sent by the official email server

### DMARC — Domain-Based Message Authentication, Reporting & Conformance

DMARC tells receiving mail servers **what to do with messages that fail SPF or DKIM checks** — and can request reports on those failures.

```
_dmarc.example.com.   IN   TXT   "v=DMARC1; p=quarantine; rua=mailto:reports@example.com"
```

**DMARC policy options (`p=`):**

| Policy | Action |
|---|---|
| `none` | Take no action; report only |
| `quarantine` | Send to spam/junk folder |
| `reject` | Block the message entirely |

**Reporting (`rua=`):** An email address where disposition reports are sent, allowing the domain owner to track how many messages passed or failed authentication.

### How SPF, DKIM, and DMARC Work Together

```
Incoming email from "professormesser.com"
        │
        ├── SPF Check: Is sending server in the authorized list?
        │
        ├── DKIM Check: Is the digital signature valid?
        │
        └── DMARC Policy: If SPF or DKIM fail → quarantine / reject / allow?
                          + send report to domain owner
```

---

## DNS Record Quick Reference

| Record Type | Purpose | Example |
|---|---|---|
| **A** | Hostname → IPv4 address | `www` → `162.159.246.164` |
| **AAAA** | Hostname → IPv6 address | `www` → `2001:db8::1` |
| **CNAME** | Alias → canonical hostname | `ftp` → `mail.example.com` |
| **MX** | Domain → mail server hostname | `@` → `mail.example.com` |
| **TXT** | Free-form text / verification / email auth | SPF, DKIM, DMARC, domain verification |
| **SOA** | Start of Authority — zone metadata | Identifies the primary DNS server for a zone |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| DNS | Distributed hierarchical database; translates FQDNs to IPs |
| Root servers | 13 clusters; 1,000+ physical servers; top of the DNS hierarchy |
| gTLD | Generic top-level domains (.com, .org, .net, etc.) |
| ccTLD | Country code TLDs (~275); .us, .ca, .uk, etc. |
| A record | Hostname → IPv4 address |
| AAAA record | Hostname → IPv6 address |
| CNAME | Alias pointing to a canonical hostname; simplifies IP changes |
| MX record | Points to the mail server for a domain; requires a separate A record lookup |
| TXT record | Free-form text; used for verification, SPF, DKIM, DMARC |
| TTL | How long a record is cached; shorter TTL = faster propagation of changes |
| SPF | Lists authorized sending mail servers; prevents spoofing |
| DKIM | Digital signature on outgoing email; public key stored in DNS TXT |
| DMARC | Policy for failed SPF/DKIM: none / quarantine / reject; enables reporting |
| dig | Linux/macOS DNS query tool |
| nslookup | Windows DNS query tool |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Domain 2 — Networking**, covering DNS record types, DNS query tools, and email authentication mechanisms used to combat spam and spoofing.
