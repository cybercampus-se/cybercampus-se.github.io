---
title: LLM-Powered Honeypots
description: Honeypots have long been used as a valuable tool in cybersecurity to attract, detect, and study adversarial behavior. Traditional honeypots, however, are limited by their static responses, limited protocol coverage, and susceptibility to fingerprinting. As attackers become increasingly sophisticated, especially with the rise of AI-assisted attacks, there is a need for adaptive and intelligent honeypot designs. Large Language Models (LLMs), such as GPT-based architectures, offer new possibilities for simulating realistic system and service responses. By dynamically generating context-aware interactions, LLM-powered honeypots could provide a more convincing and robust deception environment. This would make it significantly harder for attackers to distinguish honeypots from real systems, thereby improving threat intelligence gathering.
weight: 2
bookFlatSection: true
bookHidden: true
draft: false
---

# LLM-Powered Honeypots

- **Thesis ID:** 25-02
- **Research Proposal:** Developing LLM-Powered Honeypots for Next-Generation Cyber Threat Detection
- **Collaboration company/organization:** -

## Abstract

Honeypots have long been used as a valuable tool in cybersecurity to attract, detect, and study adversarial behavior. Traditional honeypots, however, are limited by their static responses, limited protocol coverage, and susceptibility to fingerprinting. As attackers become increasingly sophisticated, especially with the rise of AI-assisted attacks, there is a need for adaptive and intelligent honeypot designs.

Large Language Models (LLMs), such as GPT-based architectures, offer new possibilities for simulating realistic system and service responses. By dynamically generating context-aware interactions, LLM-powered honeypots could provide a more convincing and robust deception environment. This would make it significantly harder for attackers to distinguish honeypots from real systems, thereby improving threat intelligence gathering.

<details>
<summary>Details</summary>


## 1. Problem Statement

The core challenge this research addresses is how to design, implement, and evaluate honeypots that leverage LLMs for dynamic response generation while minimizing risks such as unintended data leakage, performance overhead, and adversarial manipulation.

## 2. Objectives

- **Design an LLM-Powered Honeypot Architecture** – Integrating open-source LLMs into honeypots to simulate realistic interactions across multiple protocols.
- **Evaluate Fingerprinting Resistance** – Testing whether adversaries can reliably distinguish between LLM-generated responses and genuine system responses.
- **Threat Intelligence Extraction** – Measuring the effectiveness of LLM-powered honeypots in capturing novel attack vectors, payloads, and adversarial strategies.
- **Risk Mitigation** – Identifying potential risks (e.g., prompt injection, model exploitation) and proposing defensive measures.
- **Performance Benchmarking** – Evaluating the computational efficiency and scalability of deploying LLMs in real-world honeypot settings.

## 3. Research Methodology

* **Testbed Setup:** Deploy honeypots using containerized environments (e.g., Docker, Kubernetes).
* **LLM Integration:** Fine-tune or adapt open-source LLMs (e.g., HuggingFace models) for generating protocol-specific responses (SSH, HTTP, SMTP).
* **Adversarial Testing:** Simulate attacks to assess believability, adaptability, and resistance to fingerprinting.
* **Data Analysis:** Extract, classify, and cluster captured attacks to enhance cyber threat intelligence.

## 4. Expected Outcomes

* A prototype of an **LLM-powered honeypot framework**.
* An evaluation of the **effectiveness and limitations** of LLMs in deception-based security.
* Novel insights into **adversarial behavior against AI-driven defenses**.
* Recommendations for safe deployment of LLM-enhanced honeypots in research and operational settings.

## 5. Timeline

| Phase                        | Duration   |
|------------------------------|------------|
| Literature review, design of architecture.                    | 2 weeks    |
| Implementation of LLM-based honeypot prototype.               | 2 months   |
| Controlled adversarial testing and evaluation.                | 2 months   |
| Data analysis, refinement of model and defense strategies.    | 2 weeks    |
| Thesis Writing and Submission                                 | 2 weeks    |

## 6. References

- 2025, [Decoypot: A Large Language Model-Driven Web Api Honeypot for Realistic Attacker Engagement](https://www.sciencedirect.com/science/article/abs/pii/S0167404825001476)
- 2024, [HoneyGPT: Breaking the Trilemma in Terminal Honeypots with Large Language Model](https://arxiv.org/html/2406.01882v2)
- 2024, [LLM in the Shell: Generative Honeypots](https://arxiv.org/html/2309.00155v3)
- 2024, [HoneyLLM: A Large Language Model-Powered Medium-Interaction Honeypot](https://link.springer.com/chapter/10.1007/978-981-97-8801-9_13)
- 2024, [HoneyLLM: Enabling Shell Honeypots with Large Language Models](https://mcn.cse.psu.edu/paper/guan-chongqi/cns24-chongqi.pdf)
- 2024, [A Modular Generative Honeypot Shell](https://ieeexplore.ieee.org/abstract/document/10679411/references#references)
- 2024, [Honeypot and Generative AI](https://webthesis.biblio.polito.it/secure/33140/1/tesi.pdf)

</details>

