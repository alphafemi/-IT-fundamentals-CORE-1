# CompTIA A+ 220-1201 — Troubleshooting Networks

> **Exam Domain Reference** | Core 1 (220-1201) — Networking (Domain 2)  
> Topics: Connectivity troubleshooting steps, limited/no connectivity, APIPA, jitter, VoIP quality, port flapping, latency, wireless interference, SNR, authentication issues, intermittent problems

---



---

## Network Connectivity Troubleshooting Steps

Use this systematic ping sequence to identify where connectivity breaks down:

| Step | Action | What It Tests |
|---|---|---|
| 1 | Check **link light** on Ethernet port | Physical layer — cable and port connected |
| 2 | Ping **127.0.0.1** (loopback) | IP stack on the local device functioning |
| 3 | Ping **local IP address** | Local NIC and configuration working |
| 4 | Ping **default gateway** | Communication to another device on the local network |
| 5 | Ping a **remote IP address** (e.g., 8.8.8.8, 9.9.9.9, 1.1.1.1) | Communication outside the local network (internet) |

**Where pings fail = where the problem is.**

> **Exam Tip:** The loopback ping (127.0.0.1) tests the IP stack, not the physical network. If this fails, the issue is with the OS network configuration — not the cable or switch.

---

## Limited or No Connectivity

**Windows alert: "Limited or no connectivity" / "No Internet access"**

**Likely cause:** APIPA address assigned — DHCP server was unreachable.

**Check:**
- What IP address does the device have?
- If `169.254.x.x` → APIPA address → DHCP server problem
- If valid IP → continue pinging through the gateway and beyond to find the break

**Troubleshooting path:**
1. Check local IP → is it APIPA or a valid DHCP/static address?
2. Ping the default gateway → can you reach the local router?
3. Ping a remote IP → can you reach the internet?
4. At the step where pings fail → investigate that segment

---

## Wireless Connectivity Issues

**Intermittent wireless — common causes and fixes:**

| Cause | Fix |
|---|---|
| Channel interference from nearby networks | Change access point channel (manual or auto-select) |
| Too far from access point | Move closer; relocate AP to a more central position |
| Multipath interference | Reposition AP; try different antenna configurations |
| Frequency congestion (2.4 GHz) | Switch to 5 GHz band if supported |

**Multipath interference:** Wireless signals bouncing off flat surfaces arrive at slightly different times, causing interference with themselves.

**General wireless tips:**
- Move the AP to a centralized location
- Try external antennas on the AP or client device
- Use AP auto-channel selection to avoid congested channels

---

## Jitter & VoIP Quality

**Jitter:** The variation in time delay between packets arriving — a measure of consistency.

- **Low jitter** = packets arrive at consistent intervals → smooth voice/video
- **High jitter** = packets arrive in bursts with gaps → choppy audio, frozen video

**Why it matters for real-time traffic:** VoIP and video conferencing cannot buffer and replay missed packets. When packets are delayed or lost, the conversation degrades immediately.

**Troubleshooting high jitter / poor VoIP quality:**
- Run a speed test — identify slow links
- Check network utilization at each hop — congested links cause jitter
- Review QoS (Quality of Service) settings — real-time traffic should be prioritized
- Perform a packet capture to analyze inter-packet timing and packet loss
- Consider upgrading switches/routers if hardware is aging and can't handle load

---

## Port Flapping

**Port flapping:** A network port repeatedly cycling up and down — link light appears, disappears, reappears.

**Causes and fixes:**

| Cause | Fix |
|---|---|
| Bad Ethernet cable | Replace the cable |
| Damaged cable connector | Re-crimp or replace connector |
| Bad switch port | Move cable to a different port on the switch |

**Diagnosis:** Move the cable to a different switch port. If the problem follows the cable → cable is bad. If the problem stays at the original port → switch port is bad.

---

## High Latency

**Latency:** The delay between sending a request and receiving a response.

- Can be microseconds (fast) to seconds (slow)
- Some latency is always present — data must travel, be processed, and a response returned
- Consistently high latency = performance problem

**Troubleshooting:**
- Ping with timestamps to measure response times
- Traceroute to identify which hop has the delay
- Packet capture to measure application response time vs. network transit time
- Check each link for utilization, errors, and throughput

---

## Wireless Interference & SNR

**Wireless interference sources:**
- Fluorescent lights
- Microwave ovens
- Cordless telephones (2.4 GHz)
- Neighboring wireless networks
- Other high-power RF devices

**SNR (Signal-to-Noise Ratio):** Measures how much real signal you receive relative to background noise/interference.

| Condition | SNR | Experience |
|---|---|---|
| High SNR | Signal >> Noise | Excellent wireless performance |
| Low SNR | Signal ≈ Noise | Poor performance, dropped connections |

**Ideal SNR:** Much more signal than noise — a large ratio.

**One-to-one SNR (equal signal and noise):** Very poor — connection will be unreliable.

> **Key insight:** If you cannot control the interference source (e.g., neighbor's microwave), try moving to the 5 GHz band where these interference sources don't operate.

---

## Authentication Issues

If connectivity seems fine but resources are inaccessible:

- **Authentication may have failed or timed out** — re-enter credentials
- **Background service credentials** — a service may be running with expired or incorrect credentials silently
- **Packet capture** — will show immediate "access denied" responses if authentication is the problem

---

## Intermittent Connectivity Problems

The hardest to troubleshoot — the network works sometimes and not others.

**Strategies:**
- Run a **continuous ping** (ping with no stop, updating every second) to detect when connectivity drops
- Run **periodic traceroutes** to track which hop is failing
- Run **periodic speed tests** to correlate slowdowns with time of day
- Work with third parties (ISP, cloud provider) and reference the **Service Level Agreement (SLA)** for uptime expectations and support response times

---

## Troubleshooting Quick Reference

| Symptom | Likely Cause | First Action |
|---|---|---|
| No link light | Bad cable or port | Replace cable; try different switch port |
| Ping 127.0.0.1 fails | OS IP stack broken | Reinstall/repair network stack |
| Ping gateway fails | Local network issue | Check IP config; check cable; check switch |
| Ping internet fails | WAN/routing issue | Traceroute to find where it breaks |
| 169.254.x.x IP address | APIPA — DHCP failed | Check DHCP server; renew IP |
| "Limited connectivity" alert | APIPA or bad config | Check IP address; follow ping sequence |
| Intermittent wireless | Channel interference, distance | Change AP channel; move closer |
| Choppy VoIP / video | High jitter | Check link utilization; QoS; speed test |
| Port flapping | Bad cable or switch port | Replace cable; move to different port |
| High latency | Congested link or slow hop | Traceroute; check each hop's utilization |
| SNR is nearly 1:1 | Severe interference | Change frequency band; relocate AP |
| Resource access denied | Authentication failure | Re-enter credentials; check service accounts |
| Works sometimes, not others | Intermittent fault | Continuous ping; periodic traceroute/speed test |

---

## Key Takeaways

| Topic | Key Fact |
|---|---|
| Ping sequence | Loopback → local IP → gateway → remote IP |
| Loopback (127.0.0.1) | Tests IP stack; not the physical network |
| APIPA (169.254.x.x) | DHCP failed; local connectivity only; no internet |
| Jitter | Variation in packet arrival times; causes choppy VoIP/video |
| Port flapping | Link light cycling up/down; usually bad cable or port |
| SNR | Signal-to-Noise Ratio; want much more signal than noise |
| Low SNR | Poor wireless; look for interference sources |
| Latency | Delay between request and response; traceroute to find slow hops |
| Multipath interference | Wireless signals bounce off surfaces; repositioning AP can help |
| Intermittent issues | Use continuous ping + traceroute + speed tests to capture the problem |
| SLA | Service Level Agreement — defines uptime expectations with third parties |

---

> 📚 **Study Resource:** This document maps to **CompTIA A+ Core 1 (220-1201) Domain 2 — Networking**, covering network troubleshooting methodology, connectivity issues, wireless problems, jitter, latency, port flapping, and SNR.
