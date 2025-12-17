---
title: Security Analysis of Ambulance Communication and Onboard Systems
description: Modern ambulances are increasingly digitized and connected, enabling faster and more efficient emergency response. These vehicles rely on integrated IT systems, including onboard tablets for patient data entry, routers for mobile connectivity, APIs for exchanging data with hospital servers, and continuous communication links between the ambulance and healthcare infrastructure. While this connectivity improves healthcare delivery, it also introduces significant cybersecurity risks. Ambulances form part of a critical healthcare infrastructure, and a successful attack on their systems could lead to data breaches, loss of patient information, or even disruption of emergency medical services. The combination of Internet of Things (IoT) devices, mobile networks, and medical data systems makes ambulances an attractive target for cyber adversaries.

weight: 2
bookFlatSection: true
bookHidden: true
draft: true
---

# Secure Vibe Coding

- **Thesis ID:** 25-05
- **Research Proposal:** Security Analysis of Ambulance Communication and Onboard Systems
- **Collaboration company/organization:** Region Västerbotten and Umeå University
- Good to Know
  - **Location:** This research will be conducted at Umeå University
  - **Team Size:** 2–4 students will be selected to work collaboratively on this project
  - **Start Date:** As soon as possible

## Abstract

Modern ambulances are increasingly digitized and connected, enabling faster and more efficient emergency response. These vehicles rely on **integrated IT systems**, including onboard tablets for patient data entry, routers for mobile connectivity, APIs for exchanging data with hospital servers, and continuous communication links between the ambulance and healthcare infrastructure.

While this connectivity improves healthcare delivery, it also introduces **significant cybersecurity risks**. Ambulances form part of a **critical healthcare infrastructure**, and a successful attack on their systems could lead to data breaches, loss of patient information, or even disruption of emergency medical services. The combination of **Internet of Things (IoT) devices**, **mobile networks**, and **medical data systems** makes ambulances an attractive target for cyber adversaries.


<details>
<summary>Details</summary>

## **Research Problem**

There is currently a lack of systematic cybersecurity research addressing the **attack surfaces** and **vulnerabilities** of ambulance systems. These systems are often composed of multiple interconnected devices and communication channels supplied by different vendors, making security assurance complex. The problem this project addresses is identifying and analyzing potential vulnerabilities within the hardware, software, and communication infrastructure of ambulances and assessing their potential impact.

## **Research Objectives**

1. Identify and categorize the **attack surfaces** within ambulance systems (hardware, software, communication, and APIs).
2. Perform a **security assessment** of selected components, such as onboard tablets, routers, and communication modules.
3. Analyze **data transmission between ambulances and hospital systems** to identify potential vulnerabilities in APIs and network protocols.
4. Propose **mitigation strategies and security best practices** to enhance the resilience of ambulance IT systems.

## **Methodology**

1. **System Mapping:**

   * Document the architecture of the ambulance IT ecosystem, including hardware (e.g., tablets, routers), software (medical apps, data entry systems), and network components (LTE/5G modules, hospital APIs).
   * Identify interfaces, communication protocols, and data flows between the ambulance and the hospital.

2. **Threat Modeling:**

   * Apply frameworks such as **MITRE ATT&CK for ICS/IoT** to map potential threats and adversarial techniques.
   * Identify potential entry points and misuse scenarios (e.g., man-in-the-middle attacks, API exploitation, or router compromise).

3. **Security Testing:**

   * Conduct **vulnerability analysis** and **penetration testing** (in a controlled test environment or using simulated systems) by using **PatrIoT** as a guideline.
   * Evaluate the **router configuration and firmware**, **tablet application security**, and **API authentication and encryption mechanisms**.

4. **Communication Link Analysis:**

   * Capture and analyze network traffic between the ambulance and the hospital system to assess encryption strength, potential for data leakage, and resilience to replay or injection attacks.

5. **Evaluation**

   * Rank identified vulnerabilities by risk level.

## **Expected Contributions**

* A comprehensive **threat and vulnerability analysis** of ambulance IT systems.
* A taxonomy of **attack surfaces** and possible exploitation techniques for emergency medical vehicles.
* A set of **practical recommendations** and security guidelines for manufacturers, hospitals, and emergency service providers.
* Contribution to the broader field of **cybersecurity for connected medical and transport systems**.

## **Tentative Timeline (6 Months)**

1. **Months 0–1:** Literature review, stakeholder interviews, and system mapping.
2. **Months 2–3:** Threat modeling and defining test scenarios.
3. **Months 3–4:** Security testing and data collection.
4. **Months 4–5:** Analysis of results, mitigation design.
5. **Months 5-6:** Documentation and thesis completion.

## **Expected Outcome**

This research will produce a **systematic security analysis framework** for ambulances and similar emergency response systems. The findings will highlight key vulnerabilities in communication and IT systems, allow stakeholders to take practical countermeasures, and ultimately strengthen **cyber resilience in healthcare-critical operations**.

</details>
