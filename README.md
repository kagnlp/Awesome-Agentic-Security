# A Survey on Agentic Security: Applications, Threats, and Defenses

[![arXiv](https://img.shields.io/badge/arXiv-2510.06445-b31b1b.svg)](https://arxiv.org/abs/2510.06445)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

**Authors:** Asif Shahriar\*, Md Nafiu Rahman\*, Sadif Ahmed\*, Farig Sadeque, Md Rizwan Parvez  
*BRAC University, Qatar Computing Research Institute (QCRI)*

---

## 📖 Overview

The transition from passive LLMs to autonomous **LLM-agents** marks a paradigm shift in cybersecurity. While these agents can act as powerful tools for both offensive and defensive operations, the very agentic context introduces a new class of inherent security risks.

This repository maintains the resources, taxonomy, and paper list associated with our survey: **"A Survey on Agentic Security: Applications, Threats and Defenses"**.

In this work we present the first holistic survey of the agentic security landscape, structured to answer three key questions a security researcher would ask: 

- _“What can agents do for my security?”_
- _“How can they be attacked?”_
- _“How do I stop them?”_

To this end, we define three pillars of taxonomy:
1.  **Applications:** How agents are used in Red/Blue teaming.
2.  **Threats:** Vulnerabilities inherent to agentic systems (e.g., indirect injection, memory poisoning).
3.  **Defenses:** Countermeasures to harden agentic systems.

![Agentic Security Overview](assets/figure1_overview.png)
*(Figure 1: Overview of the Agentic Security Landscape)*

---

## 🗂️ Taxonomy & Paper List

Below is the classification of the 150+ papers analyzed in our work.

### 🛡️ I. Applications
**Red Teaming (Offensive Security)**
* **Autonomous Penetration Testing:** Agents that perform recon and exploitation (e.g., PentestGPT, HackSynth)
* **Automated Vuln Discovery & Fuzzing:** Reasoning-driven fuzzing (e.g., Locus, ChatAFL).
* **Exploit Generation:** Malware and exploit adaptation (e.g., MalGen, CVE-Genie).

**Blue Teaming (Defensive Security)**
* **Autonomous Threat Detection:** Agentic SOC frameworks (e.g., IRCopilot, CORTEX).
* **Intelligent Threat Hunting:** Hypothesis generation and querying (e.g., ProvSEEK).
* **Automated Forensics:** RCA and log analysis (e.g., RepoAudit, CyberSleuth).
* **Autonomous Patching:** Repair and remediation (e.g., RepairAgent).

**Domain-Specific**
* **Cloud & Infrastructure:** (e.g., KubeIntellect).
* **Web & Application:** (e.g., MAPTA, Progent).
* **Specialized:** Blockchain, Healthcare, Privacy (e.g., LISA, HIPAA-compliant agents).

### ⚠️ II. Threats
**Attack Surface**
* **Injection Attacks:** Direct and Indirect Prompt Injection (e.g., AgentDojo, PromptInfection).
* **Poisoning & Extraction:** Memory corruption and model stealing (e.g., AgentPoison).
* **Jailbreak Attacks:** Bypassing safety guardrails (e.g., BrowserArt, JAWS-BENCH).
* **Agent Manipulation:** Goal hijacking and reward hacking (e.g., PromptInject).
* **Red-Teaming Attacks:** Agent-in-the-Middle and multi-agent adversarial flows.

**Evaluation**
* **Adversarial Benchmarks:** (e.g., AgentHarm, SafeArena, ASB).
* **Execution Environments:** Sandboxes for testing (e.g., DoomArena).

### 🛡️ III. Defenses
**Defense & Operations**
* **Secure-by-Design:** Architecture isolation and permissions (e.g., ACE, Task Shield).
* **Multi-Agent Security:** Trust and collaboration protocols (e.g., D-CIPHER).
* **Runtime Protection:** Monitoring and guardrails (e.g., R-Guard, AgentSpec).
* **Security Operations:** Formal verification and incident response.

**Evaluation**
* **Benchmarking Platforms:** (e.g., RAS-Eval).
* **Defense Testing:** Testing resilience of defenses.

---

## 📊 Key Insights

A cross-cutting analysis of the literature reveals clear structural patterns.
* **Architecture and Autonomy:**  The field is shifting towards planner–executor (39.8%) and hybrid architectures (14%). It reflects a growing appreciation of decomposed cognitive pipelines, where planning, execution, and verification can be modularized to improve interpretability and debugging. In terms of autonomy, more than half of the works implement bounded automation, allowing agents to act independently within predefined limits, eliminating the need for non-scalable human approvals. 
* **Agentic role distribution:**  We note the growing number of tool-caller (42) and governor/mediator (24) agents, which signifies a fundamental shift from monolithic reasoning to layered, self-checking collectives designed for explicit self-regulation and ethical alignment.  
* **Model monopoly:** GPT-family models appear in 83% of studies, establishing de facto benchmark status but raising concerns about monoculture and reproducibility. Claude (71) and LLaMA (63) constitute the next major clusters. Except for LLaMA, other open-weight models like Mistral (30), Qwen (18) and Deepseek (15) are in the minority, suggesting a lack of trust in their agentic capabilities. Moreover, model-specific alignment differences create fragmentation: safety fine-tuning and evaluation pipelines are rarely transferable, hindering cross-model generalization and reproducibility. 
* **Modalities:** Input modality spectrum is dominated by text (covered in 141 works), logs (101) and codes (93). Images (11), network traces (38) and binaries (10) are studied a lot less, which is a limitation since these modalities are often tied to security vulnerabilities and intrusion. This also shows a promising area of future work.
* **Knowledge source:** Pretrained knowledge-bases dominate (132), with limited adoption of adaptive learning paradigms. ICL (66) and RAG (43) show partial adoption, while fine-tuning (38), and RL or preference learning (8) remain niche. This imbalance suggests a community preference for lightweight deployment over continual learning, which is practical for agents but potentially insecure in dynamic threat environments. It also provides future research direction in securing RAG pipelines with verified provenance, incremental fine-tuning, and model distillation. 

![Cross Cutting Analysis](assets/figure2_analysis.png)

---

## 🤝 Contribution
This is an active research area. If you have a paper that fits into this taxonomy, please:

1.  **Fork** the repository.
2.  **Add** your paper to the relevant section in the list.
3.  **Submit** a Pull Request.

--- 

## 📞 Contact
For inquiries regarding the survey, dataset updates, or collaboration, please contact:

Asif Shahriar 📧 asifshahriar@gmail.com 

---

## 📝 Citation

If you find this survey or repository useful, please cite our work:

```bibtex
@article{shahriar2025agentic,
  title={A Survey on Agentic Security: Applications, Threats and Defenses},
  author={Shahriar, Asif and Rahman, Md Nafiu and Ahmed, Sadif and Sadeque, Farig and Parvez, Md Rizwan},
  journal={arXiv preprint arXiv:2510.06445},
  year={2025}
}

