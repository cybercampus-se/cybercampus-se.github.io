---
title: AirSnitch on eduroam (Wi-Fi Client Isolation Bypass)
description: AirSnitch shows that Wi-Fi client isolation (AP isolation) can be bypassed due to cross-layer weaknesses in Wi-Fi encryption, switching, and routing. This thesis will evaluate whether these bypass primitives can be demonstrated on the university `eduroam` network under explicit authorization, and will propose mitigation recommendations tailored to real deployments.
weight: 2
bookFlatSection: true
bookHidden: true
draft: false
---

# Wi-Fi Client Isolation Bypass

- **Thesis ID:** 25-06
- **Research Proposal:** Evaluating Client Isolation Bypass on eduroam Wi-Fi 
- **Requirements:**
  - You should have experience with at least one of: Linux networking, Wi-Fi/802.11 fundamentals, packet analysis, or wireless testbed setup.
  - Supervisor must obtain written authorization from the university (IT/network administration) and have a documented scope for the test (no impact to other users).
  - Experiments must use only your own devices and dedicated test accounts/traffic patterns; do not capture or interfere with other users' data.
  - All findings must be reported responsibly (including potential mitigations and vendor/network feedback where appropriate).

## Abstract

Client isolation (also called AP isolation) is widely deployed in Wi-Fi networks to prevent malicious clients from attacking other clients connected to the same network. AirSnitch (NDSS 2026) demonstrates that these isolation guarantees are not consistent across real-world deployments, because weaknesses exist across multiple Wi-Fi layers and their cross-layer interactions. Building on AirSnitch, this thesis will assess whether and how client isolation can be bypassed on the university `eduroam` network, under explicit authorization. The student is expected to attempt the paper's bypass primitives in a controlled manner using only their own devices, to evaluate feasibility, quantify impact, and produce mitigation recommendations for defenders.

<details>
<summary>Details</summary>

## 1. Introduction

### 1.1 Background

Wi-Fi client isolation is intended to reduce insider risk by blocking direct communication between clients. However, AirSnitch shows that isolation is not standardized, and that real router/AP implementations can enforce isolation only partially, or enforce it in a way that breaks under cross-layer interactions. As a result, attackers may regain the ability to intercept and/or inject traffic, restoring machine-in-the-middle capabilities that isolation was meant to prevent.

### 1.2 Problem Statement

`eduroam` is a campus-scale Wi-Fi deployment where incorrect or inconsistent isolation enforcement could allow unauthorized interception of traffic between clients (even when AP isolation is enabled). This thesis aims to evaluate the practical security effectiveness of `eduroam` client isolation against the AirSnitch bypass primitives, while ensuring tests remain ethical, authorized, and non-impactful to other users.

### 1.3 Objectives

1. Determine whether client isolation on `eduroam` can be bypassed in an authorized, limited experiment using AirSnitch's identified bypass categories.
2. Characterize which AirSnitch root cause(s) best explain any observed failures (e.g., group-key related behavior, isolation enforced at only one layer, or weak identity synchronization across layers).
3. Quantify the feasibility and impact of any demonstrated bypass (e.g., whether interception of own test traffic is possible; what traffic metadata becomes observable), without exposing or collecting sensitive data from other users.
4. Propose mitigation recommendations aligned with the paper's defenses, adapted to the constraints of an enterprise campus network.

## 2. Literature Review

### 2.1 Wi-Fi Client Isolation in Practice

Survey how AP isolation is implemented across common vendors and how the lack of standardized enforcement can lead to inconsistent guarantees.

### 2.2 Wi-Fi Cross-Layer Interactions

Review Wi-Fi encryption and keying (including group/broadcast key handling), AP switching/forwarding behavior, and how identity (MAC/IP/keys) is represented across network layers and SSIDs/BSSIDs.

### 2.3 AirSnitch Attack Surface and Defenses

Review AirSnitch's structured analysis and the bypass primitives it designs and evaluates, including the paper's discussion of practical mitigations (e.g., stronger network isolation, spoofing prevention, and group-key hardening).

## 3. Research Methodology

### 3.1 Phase 1: Authorization, Ethics, and Safety Setup

1. Define a written test plan with the university to minimize risk and scope impact.
2. Establish measurement and containment procedures (only own devices/test traffic; avoid capturing other users' data).
3. Choose metrics and success criteria that map to the paper's threat model, but remain ethical and safe for in-situ testing.

### 3.2 Phase 2: Baseline Characterization of eduroam

1. Identify relevant `eduroam` configuration aspects: security mode(s) (WPA2/WPA3-Enterprise), topology relevant to isolation behavior (APs/BSSIDs), and observed client isolation behavior for authorized test accounts.
2. Determine experimental constraints (e.g., roaming behavior, multi-band/multi-BSSID deployment details).

### 3.3 Phase 3: Replication in a Local, Controlled Testbed

1. Build a local Wi-Fi testbed that mirrors key characteristics relevant to AirSnitch's cross-layer analysis (enterprise-like isolation domains).
2. Validate the measurement pipeline and confirm which bypass categories are feasible in a controlled environment using only test clients.

### 3.4 Phase 4: Authorized Evaluation on eduroam

1. Attempt only the bypass primitives under the approved scope, using only the student's devices and test traffic.
2. Collect evidence that demonstrates feasibility (or failure) in a reproducible manner, focused on the experiment's defined metrics.
3. If results indicate security weaknesses, document the conditions and responsible remediation steps without expanding scope to other users.

### 3.5 Phase 5: Mitigation Design and Recommendations

1. Evaluate defense options discussed in AirSnitch and assess which mitigations are realistically applicable for campus deployments.
2. Produce a mitigation report for defenders, including: what should be changed, where in the network stack it applies, and expected operational trade-offs.

## 4. Expected Outcomes

1. A reproducible assessment of whether `eduroam` client isolation resists the AirSnitch bypass primitives under authorized testing conditions.
2. A classification of any observed failures by AirSnitch's root-cause categories, with clear experimental justification.
3. Quantitative and qualitative measurements of feasibility and impact for the student's own test traffic.
4. A practical mitigation and verification checklist tailored to an enterprise campus Wi-Fi context.

## 5. Timeline

| Phase | Duration |
|---|---|
| Authorization, scope definition, and baseline setup | 1 month |
| Local testbed replication and measurement validation | 2-3 months |
| Authorized evaluation on eduroam | 1-2 months |
| Mitigation design, reporting, and thesis writing | 1-2 months |

## 6. Conclusion

This thesis will translate AirSnitch's findings into an authorized, campus-scale security assessment of `eduroam`. By evaluating the feasibility of client-isolation bypass primitives and producing actionable mitigation recommendations, the project aims to improve defender understanding and strengthen the security of real-world enterprise Wi-Fi networks.

## 7. References

1. AirSnitch (NDSS 2026) paper: [https://papers.mathyvanhoef.com/ndss2026-airsnitch.pdf](https://papers.mathyvanhoef.com/ndss2026-airsnitch.pdf)
2. NDSS symposium page: [https://www.ndss-symposium.org/ndss-paper/airsnitch-demystifying-and-breaking-client-isolation-in-wi-fi-networks/](https://www.ndss-symposium.org/ndss-paper/airsnitch-demystifying-and-breaking-client-isolation-in-wi-fi-networks/)
3. Open-source code (mirrors): [https://github.com/vanhoefm/airsnitch](https://github.com/vanhoefm/airsnitch), [https://github.com/zhouxinan/airsnitch](https://github.com/zhouxinan/airsnitch)

</details>

