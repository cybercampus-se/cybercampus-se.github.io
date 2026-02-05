---
title: Developing proposal
description: How to develop thesis proposal.
weight: 1
# bookToc: false
---

# Developing Proposal

After developing your proposal, follow this [manual](../apply-thesis) to submit it.

## Preliminary research

You complete an exploratory research before drafting your proposal.

1. Read the literature (current methods)
2. Select a few good them to replicate
3. Conduct an empirical study to address a couple of preliminary research questions that explore the challenges of replicated methods
4. Think of how to improve what you implemented
5. Write your proposal

{{% hint info %}}
- Note that: We provide description (pre-proposal) of our research topics.
- It is just to inform you about the research topic.
- You should develop your own proposal.
- You can use the template provided by your school, otherwise you can follow your own template.
- Overleaf filename of your proposal: Abbreviation of your university - Abbreviation of your department - Abbreviation of your degree - Your name and surname
  - Example: KTH - CS - MS - Emre Süren 
{{% /hint %}}

**Why preliminary research is required?**

- The purpose of the preliminary work before the thesis work begins is to understand the challenges of current methods and get experience in the field
- The preliminary work may contain following outputs, for example:
  - For vulnerability research studies (i.e., ethical hacking), you need to include a complete threat model or describe the attacks that will be performed
  - For other studies, the data should be collected in advance
- It is strongly recommended that students apply for job postings in which they have **experience**
  - You are not expected to be an expert, but you are expected to be experienced
  - If you do not have experience, preliminary research will prepare yourself, for example:
  - For a vulnerability research study (i.e., IoT hacking) you will get experience in hacking an IoT device
  - For an LLM security study (i.e., Hacking with LLM) you will get experience in data sanitization (reducing token counts); fine-tuning; LangChain; LangGraph; LLM assistant APIs; Agents; RAG; MCP; etc.

## Common Mistakes

Before starting your master's thesis, you must complete a **Research Methodology and Scientific Writing** course required by all schools where you are expected to learn how to develop a thesis proposal. One cannot begin thesis work without these prerequisites. However, we frequently observe that many applicants simply submit our pre-proposal text with minor modifications, or fail to properly formulate their own research questions.

- When conducting research, you will encounter and solve many problems, but your thesis proposal should clearly state the main research questions. 
- Focus on articulating **how your work contributes to the literature and how you improve upon existing methods**. 
- If your research involves multiple related questions, prioritize those that must be solved next.

{{% hint warning %}}
Since 2024, we have repeatedly seen poorly defined research questions in proposals. Notably, if you use our pre-proposal as input for tools like ChatGPT, you will likely receive similarly vague questions below. Avoid this by developing specific, well-defined research questions tailored to your study.
{{% /hint %}}

**1 What are the vulnerabilities of the device ABC?**

- While discovering new vulnerabilities contributes to the literature, this question is too broad and lacks specificity regarding the context or scope. 
- *Simply applying existing tools and methods* to identify vulnerabilities and reporting the results does not meet academic standards for a master's thesis. 
- Instead, focus on identifying limitations in current approaches and proposing improvements on existing tools or novel techniques to address those gaps.

**2 What hardware-level and firmware-level vulnerabilities exist in the IoT device ABC?**

- While identifying hardware and firmware vulnerabilities is important, this question is typically addressed during the evaluation phase of the thesis. 
- For a strong proposal, main research questions should clearly refer to the methodology and implementation sections. 
- Focus on specifying which aspects of hardware and firmware you will investigate, the techniques you will use, and how the approach advances current methods.

**3 What are the key components and interfaces in the hardware and software architecture of the IoT device ABC, and how do they influence its attack surface?**

- It is partly a preliminary research question and partly answered in the evaluation section.
- While identifying the key components and interfaces is an essential step in understanding the device's architecture and potential weaknesses, this question is primarily addressed in a very early step, the information gathering phase. 
- As it is a mandatory step in vulnerability research, one should not state it as a main research question. For a master's level thesis, the research question should go beyond mapping the attack surface and focus on analyzing functionalities. 
- Consider refining the question to investigate how specific architectural features contribute to vulnerabilities, or how novel methods can be developed to discover weaknesses associated with these components and interfaces.

**4 Which communication protocols are used by the device ABC, and what vulnerabilities or weaknesses exist in their implementation or configuration?**

- It is partly a preliminary research question and partly answered in the evaluation section.
- While identifying and analyzing communication protocols is a necessary initial step in vulnerability research, this question is primarily focused on information gathering rather than forming a central research question. 
- For a master's thesis, the main research question should go beyond listing protocols and their weaknesses. 
- Instead, consider investigating how specific protocol implementations contribute to security risks, and propose an evaluation of novel methods for discovering vulnerabilities in these protocols. Aim to formulate a research question that indicates a gap in current approaches and demonstrates a clear contribution to the field.

**5 What built-in or third-party security measures are present on the IoT device ABC, and how effective are they against common attack vectors?**

- While evaluating the security posture of the device is relevant, it is not our main focus.
- Instead, use it to support the main research by analyzing the effectiveness of existing security measures as part of the evaluation. 
- Consider refining the proposal to address how the research contributes to improving current discovery methods or assessing these security mechanisms in a novel way.

**6 What security enhancements can be proposed to harden the IoT device ABC against the identified vulnerabilities?**

- While proposing security enhancements is valuable, it is not our main concern. 
- Instead, one may use it to support the main research by evaluating the effectiveness of the proposed solutions in mitigating specific vulnerabilities. 
- Ensure that the proposal clearly explains how the approach advances current practices.

## Examples

The following questions can be considered as research questions that are addressed in the methodology and implementation sections.

- To what extent can open-source tools (ABC) perform vulnerability research tasks (ABC) on attack surfaces (ABC)?
- What are the reasons for the failure of vulnerability research using open-source tools (ABC), for weaknesses (ABC)?
- How do open-source tools (ABC) perform in the different phases of vulnerability research (ABC) on attack surfaces (ABC)?

When drafting a thesis proposal, consider including evaluation questions that demonstrate the impact and effectiveness of the work. These questions are typically addressed in the Evaluation section and help clarify how the research advances the field. Examples include:

- How does the proposed method compare to baseline or off-the-shelf tools in terms of performance and reliability?
- What is the effectiveness of the proposed approach when applied to real-world scenarios?
- What is the contribution of each developed module, ABC, to the overall performance of the proposed method in practical tasks?


## Recommendations

### 1 Collaboration

- If we collaborate with a company in a thesis topic, we state it in the proposal description
- If the topic you selected does not involve a company, you are free to find one 
- If you develop your own proposal we also suggest you to find a collaborating company

### 2 Quality & Publication matters

- The work you perform in our lab must be of a quality that can be published in a journal
- Students who want to publish in a conferences/journals over others are prioritized
  - Publications are submitted to the conferences/journals that we approve
- As long as we have funding, we finance students producing publications
  - Either during the study with a 20% paid work
  - Or after the thesis study, by recruiting full time for 3 months
  - Financial compensation is not fixed, changes depending on our current funds

### 3 Pace & Timeline

- Students are strongly encouraged to begin research on the topic of interest at least 6 months before the expected start of the study.
- It is strongly recommended that students apply at least 3 months before the expected start of the study.
- You are expected to spend at least 20 hours per week on our work during the study period. However, based on our experience, we recommend that you devote your full attention and time to your thesis work.
- We can only provide a tentative timeline for every project that is based on our experience, but the exact timeline depends on the qualifications and performance of the student.

More questions? Check out the **frequently asked** [questions](../../contact/faq)