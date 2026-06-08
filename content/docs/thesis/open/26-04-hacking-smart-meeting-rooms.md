---
title: Hacking Smart Meeting Rooms
description: Modern meeting rooms are equipped with networked displays, video-conferencing units, room-booking panels, and access-control devices that collectively form an always-on, sensor-rich infrastructure. Recent research has shown that smart displays silently participate in commercial AI-scraping proxy networks through embedded SDKs, exfiltrating bandwidth and telemetry without meaningful user consent. When such devices are deployed in rooms where sensitive or confidential meetings take place, the implications extend well beyond consumer privacy. This research investigates the attack surface of smart meeting room infrastructure — including large-format displays, video-conferencing endpoints (e.g., Poly), room-booking panels (e.g., Evoko), and entrance access-control units (e.g., StepLock) — with the goal of identifying vulnerabilities that could enable surveillance, lateral movement, or covert data exfiltration in high-value environments.
weight: 2
bookFlatSection: true
bookHidden: true
draft: false
---

# Hacking Smart Meeting Rooms

- **Thesis ID:** 26-04
- **Research Proposal:** Vulnerability Research in Smart Meeting Room Infrastructure: Evaluating Surveillance and Exfiltration Risks in High-Value Environments
- **Requirements:**
  - You should have hands-on experience in at least one of the following:
    - Network traffic analysis (Wireshark, mitmproxy, or similar)
    - Firmware extraction or static/dynamic analysis of embedded Linux or Android-based devices
    - Mobile/IoT application reverse engineering
  - You are expected to conduct authorized experiments only within lab-controlled or explicitly permitted environments; do not test on production meeting room deployments without written approval

## Abstract

Modern meeting rooms have become complex networked environments. Alongside traditional audio-visual equipment, they now host large-format smart displays, cloud-managed video-conferencing endpoints, touchscreen room-booking panels, and IP-connected access-control units. Each of these devices runs a software stack — often based on Android, embedded Linux, or a proprietary OS — that communicates with cloud back-ends, receives over-the-air updates, and in some cases embeds third-party SDKs with opaque data-collection behaviour.

A 2026 investigation by Include Security revealed that major smart TV platforms are enrolled in commercial residential-proxy networks operated by companies such as Bright Data. Embedded SDKs route third-party web-scraping traffic through consumer devices, using the device's IP address as an exit node. The SDK actively circumvents standard network inspection by binding directly to physical interfaces rather than the system routing table, and telemetry transmitted includes screen state, CPU load, connectivity type, and call status. When devices with similar SDK stacks are deployed in meeting rooms at research institutions, companies, or government facilities, the same proxy and telemetry mechanisms may silently exfiltrate sensitive contextual signals — or provide a foothold for further network access.

This research systematically evaluates the attack surface of the four primary device categories found in sensitive meeting rooms: smart displays and monitors, video-conferencing endpoints (e.g., Poly Studio series), room-booking panels (e.g., Evoko Liso), and entrance access-control units (e.g., StepLock). The study will characterise what data these devices collect and transmit, identify SDK-level or firmware-level vulnerabilities, and assess whether any device can be leveraged for lateral movement or covert surveillance of meeting activity.

<details>
<summary>Details</summary>

## Problem Statement

Meeting rooms at research labs, companies, and public institutions regularly host discussions of strategic, commercial, or security-sensitive nature. The devices installed in these rooms — displays, conferencing units, booking panels, and door controllers — are typically procured and managed by IT or facilities teams with limited security review of the firmware and cloud-communication stack. Prior work has focused on consumer smart TVs and home IoT; the meeting-room device category is largely unexamined from a security perspective.

The Include Security findings demonstrate that the threat is not theoretical: devices already deployed in living rooms are enrolled in proxy networks and transmit continuous telemetry. The same firmware lineages and SDK vendors supply enterprise-grade meeting room hardware. This research asks: to what extent are the devices in a sensitive meeting room already participating in covert data flows, and what additional vulnerabilities do they introduce into the local network?

## Research Objectives

1. Identify and characterise all egress network traffic produced by representative devices from each target category (displays, conferencing endpoints, room-booking panels, access controllers) under normal operation.
2. Detect the presence of third-party SDKs or embedded agents (proxy, analytics, telemetry) in device firmware or application layers and evaluate the data they collect and transmit.
3. Assess whether identified SDKs or firmware components employ inspection-bypass techniques (e.g., direct CFNetwork calls, physical interface binding, certificate pinning) that would evade standard enterprise monitoring.
4. Evaluate the potential for lateral movement from a compromised meeting room device into the broader organisational network.
5. Propose detection signatures and network-level mitigations deployable in enterprise environments without replacing existing hardware.

## Methodology

### Phase 1 — Device Selection and Lab Setup

1. Procure or obtain access to representative devices: at least one large-format smart display (e.g., Samsung or LG commercial display), one video-conferencing endpoint (e.g., Poly Studio X series), one room-booking panel (e.g., Evoko Liso), and one access-control unit (e.g., StepLock or similar IP-connected lock controller).
2. Build a controlled network testbed with full traffic capture capability (SPAN port or inline proxy) and an isolated VLAN mirroring a realistic enterprise deployment.
3. Define a threat model covering passive surveillance (audio/video leakage), data exfiltration via proxy SDK, and active lateral movement.

### Phase 2 — Traffic Analysis and SDK Detection

1. Capture and classify all egress traffic per device under: idle, screen-sharing session active, meeting in progress (simulated), and firmware-update conditions.
2. Perform static firmware analysis where firmware can be extracted (UART, JTAG, or vendor update packages): identify embedded SDKs, third-party libraries, and cloud endpoints.
3. Cross-reference discovered SDK names and network endpoints against known residential-proxy and analytics SDK databases (e.g., Exodus Privacy, Include Security findings, academic SDK catalogues).
4. For Android-based devices, apply dynamic instrumentation (Frida or similar) to trace SDK API calls and identify inspection-bypass mechanisms.

### Phase 3 — Vulnerability Assessment

1. Test for known vulnerability classes on each device: unauthenticated APIs, insecure default credentials, unencrypted firmware update channels, debug interfaces left enabled, and command injection in web management interfaces.
2. Evaluate access-control unit separately for physical-security bypass potential (replay attacks on RF/BLE unlock signals, API abuse for remote unlock).
3. Assess inter-device trust: whether a compromised display or booking panel can reach the access-control unit or internal network resources.

### Phase 4 — Mitigation and Detection Development

1. Develop network-based detection rules (Suricata/Zeek signatures, DNS blocklists, TLS SNI patterns) for identified covert SDK traffic.
2. Propose a device-category security baseline (firewall rules, update policy, SDK audit checklist) applicable to enterprise meeting room deployments.
3. Where feasible, validate that proposed mitigations block identified traffic without disrupting legitimate device functionality.

## Expected Contributions

- A structured vulnerability and privacy report for each of the four meeting room device categories, including discovered SDK inventory and egress traffic classification.
- Empirical evidence for or against the presence of residential-proxy or AI-scraping SDK behaviour in enterprise meeting room hardware.
- A set of reusable network detection signatures for covert meeting room device traffic.
- A practitioner-oriented deployment security baseline for IT/facilities teams responsible for meeting room infrastructure.
- Academic publication documenting methodology and findings, contributing to the underexplored intersection of enterprise IoT security and covert SDK ecosystems.

## Tentative Timeline (6 to 9 Months)

| Phase | Duration |
|---|---|
| Threat modelling, device procurement, lab setup | 2 weeks |
| Traffic analysis and SDK detection | 1 months |
| Firmware extraction and static analysis | 1–2 months |
| Vulnerability assessment (all device categories) | 1–2 months |
| Mitigation development and validation | 1 week |
| Thesis writing and publication preparation | 1 week |

## References

1. [The Smart TV in Your Living Room is a Node in the AI-Scraping Economy (Include Security, 2026)](https://blog.includesecurity.com/2026/06/the-smart-tv-in-your-livingroom-is-a-node-in-the-aiscraping-economy/)
2. [I Still Know What You Watched Last Sunday: Privacy of the HbbTV Protocol in the European Smart TV Landscape (NDSS 2023)](https://doi.org/10.14722/ndss.2023.24102)
3. [Smart-TV security: risk analysis and experiments on Smart-TV communication channels (Journal of Computer Virology and Hacking Techniques, 2018)](https://doi.org/10.1007/s11416-018-0320-3)
4. [Static Attribution of Android Residential Proxy Malware Using Graph Kernels (2026)](https://arxiv.org/abs/2604.27302)
5. [Your Signal, Their Data: An Empirical Privacy Analysis of Wireless-scanning SDKs in Android (PoPETs 2025)](https://arxiv.org/abs/2503.15238)

</details>
