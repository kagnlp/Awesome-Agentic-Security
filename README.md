# Awesome Agentic Security Papers 📑

<p align="center">
  <a href="https://arxiv.org/abs/2510.06445">
    <img src="https://img.shields.io/badge/arXiv-2510.06445-b31b1b.svg" />
  </a>
  <a href="https://opensource.org/licenses/MIT">
    <img src="https://img.shields.io/badge/License-MIT-yellow.svg" />
  </a>
  <a href="http://makeapullrequest.com">
    <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" />
  </a>
</p>


<p align="center"><strong>A Survey on Agentic Security: Applications, Threats and Defenses
</strong></p>
<p align="center"></p>
<!-- First Part (Original) -->
<p align="center"><strong>Authors:</strong> Asif Shahriar*, Md Nafiu Rahman*, Sadif Ahmed*, Farig Sadeque, Md Rizwan Parvez</p>
<p align="center">BRAC University, Qatar Computing Research Institute (QCRI)</p>

<div align="center">
    <img src="./assets/figure1_overview.png" style="zoom:80%"/>
</div>

<hr/>

If you find this survey or repository useful, please cite our work:

```bibtex
@article{shahriar2025agentic,
  title={A Survey on Agentic Security: Applications, Threats and Defenses},
  author={Shahriar, Asif and Rahman, Md Nafiu and Ahmed, Sadif and Sadeque, Farig and Parvez, Md Rizwan},
  journal={arXiv preprint arXiv:2510.06445},
  year={2025}
}
```
## Contributing to this paper list

Feel free to **open an issue/PR** or e-mail [asif.asr11@gmail.com](mailto:asif.asr11@gmail.com) if you find any missing areas, papers, or benchmarks. We will keep updating this list and survey.

## Survey Introduction

The move from passive language models to autonomous LLM-agents marks a major shift in cybersecurity. These agents can act on their own. They can help with both attacking and defending systems, yet they also create new risks because they make decisions and interact with the world in more complex ways. This gives attackers more paths to mislead or control them.

This repository gathers the resources, taxonomy, and papers linked to the survey “A Survey on Agentic Security: Applications, Threats and Defenses.” The survey offers a clear overview of the security issues that come with autonomous agents. It centers on three questions. What agents can do for security. How agents can be attacked. How they can be protected.

In the survey. we explain the agentic security landscape through three main points:

1. How agents help with offensive and defensive security tasks.

2. Where agents are vulnerable, such as hidden prompts in outside content or harmful data written into memory.

3. How defenders can protect agents so they act safely and reliably.

This overview aims to support more research on agentic security. The goal is to use the strengths of autonomous agents while reducing the risks they bring. This will guide the development of systems that deliver real benefits while keeping harm low.


---

## Table of Contents

* [Survey Introduction](#survey-introduction)
* [Table of Contents](#table-of-contents)
* [Related Surveys for LLMs Evaluation](#related-surveys-for-llms-evaluation)
* [Papers](#papers)
    * [Applications](#applications)
        * [Red-Teaming](#red-teaming)
          * [Autonomous Penetration Testing](#autonomous-penetration-testing)
          * [Automated Vulnerability Discovery & Fuzzing](#automated-vulnerability-discovery--fuzzing)
          * [Exploit Generation](#exploit-generation)
        * [Blue-Teaming](#blue-teaming)
          * [Autonomous Threat Detection](#autonomous-threat-detection)
          * [Intelligent Threat Hunting](#intelligent-threat-hunting)
          * [Automated Forensics](#automated-forensics)
          * [Autonomous Patching](#autonomous-patching)
        * [Domain-Specific Applications](#domain-specific-applications)
          * [Cloud & Infrastructure Security](#cloud--infrastructure-security)
          * [Web & Application Security](#web--application-security)
          * [Specialized Domains](#specialized-domains)
       
      
    * [Threats](#threats)
        * [Attack Surface](#attack-surface)
          * [Injection Attacks](#injection-attacks)
          * [Poisoning & Extraction Attacks](#poisoning--extraction-attacks)
          * [Jailbreak Attacks](#jailbreak-attacks)
          * [Agent Manipulation Attacks](#agent-manipulation-attacks)
          * [Red-Teaming Attacks](#red-teaming-attacks)
        * [Evaluation](#evaluation)
          * [Adversarial Benchmarks](#adversarial-benchmarks)
          * [Execution Environments](#execution-environments)
      
    * [Defenses](#defenses)
        * [Defense & Operations](#defense--operations)
          * [Secure-by-Design Architectures](#secure-by-design-architectures)
          * [Multi-Agent Security](#multi-agent-security)
          * [Runtime Protection](#runtime-protection)
          * [Security Operations](#security-operations)
        * [Evaluation](#evaluation-1)
          * [Benchmarking Platforms](#benchmarking-platforms)
          * [Defense Testing](#defense-testing)
      
    * [LLM Leaderboards](#llm-leaderboards)
    
    * [Contributors](#contributors)

## Papers

### Applications

#### Red-Teaming

##### Autonomous Penetration Testing

1.  PentestGPT: **"PentestGPT: An LLM-empowered Automatic Penetration Testing Tool"**. 
    *Gelei Deng et al.* USENIX Security 2024. [[Paper](https://www.usenix.org/system/files/usenixsecurity24-deng.pdf)]

2.  PentestAgent: **"PentestAgent: Incorporating LLM Agents to Automated Penetration Testing"**.
    *Xiangmin Shen et al.* ASIA CCS 2025. [[Paper](https://dl.acm.org/doi/10.1145/3708821.3733882)]

3.  Vulnbot: **"VulnBot: Autonomous Penetration Testing for A Multi-Agent Collaborative Framework"**. 
    *He Kong et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2501.13411)]

4.  Aracne: **"Aracne: An LLM-based Autonomous Shell Pentesting Agent"**.
    *Tomas Nieponice et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2502.18528)]

5.  Enterprise-Test: **"Can LLMs Hack Enterprise Networks? Autonomous Assumed Breach Penetration-Testing Active Directory Networks"**. 
    *Andreas Happe and Jürgen Cito.* ACM Trans. Softw. Eng. Methodol. 2025. [[Paper](https://dl.acm.org/doi/10.1145/3766895)]

6.  HackSynth: **"Hacksynth: LLM Agent and Evaluation Framework for Autonomous Penetration Testing"**. 
    *Lajos Muzsai et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2412.01778)]

7.  AutoPentest: **"AutoPentest: Enhancing Vulnerability Management with Autonomous LLM Agents"**. 
    *Julius Henke.* arXiv 2025. [[Paper](https://arxiv.org/abs/2505.10321)]

8.  LLM-Pentest-Efficacy: **"On the Surprising Efficacy of LLMs for Penetration-Testing"**. 
    *Andreas Happe and Jürgen Cito.* arXiv 2025. [[Paper](https://arxiv.org/abs/2507.00829)]

9.  Incalmo: **"Incalmo: An Autonomous LLM-assisted System for Red Teaming Multi-Host Networks"**. 
    *Brian Singer et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2501.16466)]

10. xOffense: **"xOffense: An AI-Driven Autonomous Penetration Testing Framework with Offensive Knowledge-Enhanced LLMs and Multi Agent Systems"**. 
    *Phung Duc Luong et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2509.13021)]

11. AutoPenBench: **"AutoPenBench: Benchmarking Generative Agents for Penetration Testing"**. 
    *Luca Gioacchini et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2410.03225)]

12. AI-Pentest-Benchmark: **"Towards automated penetration testing: Introducing LLM Benchmark, Analysis, and Improvements"**. 
    *Isamu Isozaki et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2410.17141)]

##### Automated Vulnerability Discovery & Fuzzing

1.  Locus: **"Locus: Agentic Predicate Synthesis for Directed Fuzzing"**.
    *Jie Zhu et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.21302)]

2.  ChatAFL: **"Large Language Model Guided Protocol Fuzzing"**. 
    *Ruijie Meng et al.* NDSS 2024. [[Paper](https://www.ndss-symposium.org/ndss-paper/large-language-model-guided-protocol-fuzzing/)]

3.  One-Day-Exploits: **"LLM Agents Can Autonomously Exploit One-Day Vulnerabilities"**. [cite: 52, 430]
    *Richard Fang et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2404.08144)]

4.  Zero-Day-Teams: **"Teams of LLM Agents Can Exploit Zero-Day Vulnerabilities"**. 
    *Yuxuan Zhu et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2406.01637)]

5.  Android-Discovery: **"Agentic Discovery and Validation of Android App Vulnerabilities"**. 
    *Ziyue Wang and Liyi Zhou.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.21579)]

6.  Sec-Bench: **"Sec-bench: Automated Benchmarking of LLM Agents on Real-World Software Security Tasks"**. 
    *Hwiwon Lee et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2506.11791)]

7.  CVE-Bench (Web): **"CVE-Bench: A Benchmark for AI Agents' Ability to Exploit Real-World Web Application Vulnerabilities"**. 
    *Yuxuan Zhu et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2503.17332)]

8.  CVE-bench (Repair): **"CVE-bench: Benchmarking LLM-based Software Engineering Agent's Ability to Repair Real-World CVE Vulnerabilities"**. 
    *Peiran Wang et al.* NAACL 2025. [[Paper](https://aclanthology.org/2025.naacl-long.212/)]

9.  ExCyTInBench: **"Excytin-bench: Evaluating LLM Agents on Cyber Threat Investigation"**. 
    *Yiran Wu et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2507.14201)]

10. LLM-Fuzzer: **"LLM-Fuzzer: Scaling Assessment of Large Language Model Jailbreaks"**. 
    *Jiahao Yu et al.* USENIX Security 2024. [[Paper](https://www.usenix.org/system/files/usenixsecurity24-yu-jiahao.pdf)]

11. TitanFuzz: **"Large Language Models Are Zero-Shot Fuzzers: Fuzzing Deep-Learning Libraries via Large Language Models"**. 
    *Yinlin Deng et al.* ISSTA 2023. [[Paper](https://dl.acm.org/doi/10.1145/3597926.3598067)]

12. FuzzGPT: **"Large Language Models Are Edge-Case Generators: Crafting Unusual Programs for Fuzzing Deep Learning Libraries"**.
    *Yinlin Deng et al.* ICSE 2024. [[Paper](https://dl.acm.org/doi/10.1145/3597503.3623343)]

##### Exploit Generation

1.  Dark-Side-Agents: **"The Dark Side of LLMs: Agent-Based Attacks for Complete Computer Takeover"**. 
    *Matteo Lupinacci et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2507.06850)]

2.  MalGen: **"MalGen: A Generative Agent Framework for Modeling Malicious Software in Cybersecurity"**. 
    *Bikash Saha and Sandeep Kumar Shukla.* arXiv 2025. [[Paper](https://arxiv.org/abs/2506.07586)]

3.  AiTM: **"Red-Teaming LLM Multi-Agent Systems via Communication Attacks"**. 
    *Pengfei He et al.* ACL 2025. [[Paper](https://aclanthology.org/2025.findings-acl.349/)]

4.  CVE-Genie: **"From CVE Entries to Verifiable Exploits: An Automated Multi-Agent Framework for Reproducing CVEs"**. 
    *Saad Ullah et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2509.01835)]

5.  LLM4CVE: **"LLM4CVE: Enabling Iterative Automated Vulnerability Repair with Large Language Models"**. 
    *Mohamad Fakih et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2501.03446)]

#### Blue-Teaming

##### Autonomous Threat Detection

1.  RAG-Incident-Response: **"Advancing Autonomous Incident Response: Leveraging LLMs and Cyber Threat Intelligence"**. 
    *Amine Tellache et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.10677)]

2.  IRCopilot: **"RCopilot: Automated Incident Response with Large Language Models"**. 
    *Xihuan Lin et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2505.20945)]

3.  CORTEX: **"Cortex: Collaborative LLM Agents for High-Stakes Alert Triage"**.
    *Bowen Wei et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2510.00311)]

4.  AutoBnB: **"AutoBnB: Multi-Agent Incident Response with Large Language Models"**. 
    *Zefang Liu.* ISDFS 2025. [[Paper](https://ieeexplore.ieee.org/document/11012055)]

5.  SOC-Empirical-Study: **"LLMs in the SOC: An Empirical Study of Human-AI Collaboration in Security Operations Centres"**. 
    *Ronal Singh et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.18947)]

6.  CyberSOCEval: **"CyberSOCEval: Benchmarking LLMs Capabilities for Malware Analysis and Threat Intelligence Reasoning"**.
    *Lauren Deason et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2509.20166)]

7.  Log-Analysis-Survey: **"Automated Threat Detection and Response Using LLM Agents"**.
    *Ramasankar Molleti et al.* World Journal of Advanced Research and Reviews 2024. [[Paper](https://wjarr.com/sites/default/files/WJARR-2024-3329.pdf)]

##### Intelligent Threat Hunting

1.  ProvSEEK: **"LLM-Driven Provenance Forensics for Threat Investigation and Detection"**. 
    *Kunal Mukherjee and Murat Kantarcioglu.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.21323)]

2.  CTI-Vulnerabilities: **"Uncovering Vulnerabilities of LLM-Assisted Cyber Threat Intelligence"**. 
    *Yuqiao Meng et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2509.23573)]

3.  LLMCloudHunter: **"LLMCloudHunter: Harnessing LLMs for Automated Extraction of Detection Rules from Cloud-Based CTI"**. 
    *Yuval Schwartz et al.* WWW 2025. [[Paper](https://dl.acm.org/doi/10.1145/3696410.3714798)]

##### Automated Forensics

1.  RepoAudit: **"RepoAudit: An Autonomous LLM-Agent for Repository-Level Code Auditing"**. 
    *Jinyao Guo et al.* ICML 2025. [[Paper](https://openreview.net/pdf?id=TXcifVbFpG)]

2.  Cloud-Forensics: **"LLM-Powered Automated Cloud Forensics: From Log Analysis to Investigation"**. 
    *Dalal Alharthi and Rozhin Yasaei.* IEEE CLOUD 2025 . [[Paper](https://ieeexplore.ieee.org/document/11120597)]

3.  CyberSleuth: **"CyberSleuth: Autonomous Blue-Team LLM Agent for Web Attack Forensics"**. 
    *Stefano Fumero et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.20643)]

4.  GALA: **"GALA: Can Graph-Augmented Large Language Model Agentic Workflows Elevate Root Cause Analysis?"**. 
    *Yifang Tian et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.12472)]

5.  MAST: **"Why Do Multiagent Systems Fail?"**. 
    *Melissa Z Pan et al.* ICLR Workshop 2025. [[Paper](https://openreview.net/pdf?id=wM521FqPvI)]

6.  CIAF: **"Cloud Investigation Automation Framework (CIAF): An AI-Driven Approach to Cloud Forensics"**. 
    *Dalal Alharthi and Ivan Roberto Kawaminami Garcia.* arXiv 2025. [[Paper](https://arxiv.org/abs/2510.00452)]

##### Autonomous Patching

1.  CVE-Bench (Repair): **"CVE-Bench: A Benchmark for AI Agents’ Ability to Exploit Real-World Web Application Vulnerabilities"**. 
    *Yuxuan Zhu et al.* ICML 2025. [[Paper](https://openreview.net/pdf?id=3pk0p4NGmQ)]

2.  RepairAgent: **"RepairAgent: An Autonomous, LLM-Based Agent for Program Repair"**. 
    *Islem Bouzenia et al.* ICSE 2025. [[Paper](https://dl.acm.org/doi/10.1109/ICSE55347.2025.00157)]

3.  Gemini-Patching: **"AI-Powered Patching: The Future of Automated Vulnerability Fixes"**. 
    *Jan Keller and Jan Nowakowski.* Technical Report 2024. [[Link](https://research.google/pubs/ai-powered-patching-the-future-of-automated-vulnerability-fixes/)]

4.  IaC-Remediation: **"LLM Agentic Workflow for Automated Vulnerability Detection and Remediation in Infrastructure-as-Code"**. 

    *Dheer Toprani and Vijay K. Madisetti.* IEEE Access 2025. [[Paper](https://ieeexplore.ieee.org/document/10965635)]

#### Domain-Specific Applications

##### Cloud & Infrastructure Security

1.  Cloud-Infra-AI: **"Cloud Infrastructure Management in the Age of AI Agents"**. 
    *Zhenning Yang et al.* ACM SIGOPS Operating Systems Review 2025. [[Paper](https://dl.acm.org/doi/10.1145/3759441.3759443)]

2.  KubeIntellect: **"KubeIntellect: A Modular LLM-Orchestrated Agent Framework for End-to-End Kubernetes Management"**. 
    *Mohsen Seyedkazemi Ardebili and Andrea Bartolini.* 2025. [[Paper](https://arxiv.org/abs/2509.02449)]

3.  LLMSecConfig: **"LLMSecConfig: An LLM-Based Approach for Fixing Software Container Misconfigurations"**.
    *Ziyang Ye et al.* 2025. [[Paper](https://www.computer.org/csdl/proceedings-article/msr/2025/018300a629/27vTruUNcXe)]

4.  BARTPredict: **"BARTPredict: Empowering IoT Security with LLM-Driven Cyber Threat Prediction"**. 
    *Alaeddine Diaf et al.* 2025. [[Paper](https://ieeexplore.ieee.org/document/10901770)]

5.  IaC-Remediation: **"LLM Agentic Workflow for Automated Vulnerability Detection and Remediation in Infrastructure-as-Code"**. 
    *Dheer Toprani and Vijay K. Madisetti.* IEEE Access 2025. [[Paper](https://ieeexplore.ieee.org/document/10965635)]

##### Web & Application Security

1.  MAPTA: **"Multi-Agent Penetration Testing AI for the Web"**. 
    *Isaac David and Arthur Gervais.* 2025. [[Paper](https://arxiv.org/abs/2508.20816)]

2.  Browsing-Dangers: **"The Hidden Dangers of Browsing AI Agents"**. 
    *Mykyta Mudryi et al.* 2025. [[Paper](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5290351)]

3.  AIOS: **"AIOS: LLM Agent Operating System"**. 
    *Kai Mei et al.* Conference on Language Modeling 2025. [[Paper](https://openreview.net/pdf?id=L4HHkCDz2x)]

4.  OS-Agents-Survey: **"OS Agents: A Survey on MLLM-based Agents for Computer, Phone and Browser Use"**. 
    *Xueyu Hu et al.* 2025. [[Paper](https://aclanthology.org/2025.acl-long.369/)]

5.  Prompt-Flow-Integrity: **"Prompt Flow Integrity to Prevent Privilege Escalation in LLM Agents"**. 
    *Juhee Kim et al.* 2025. [[Paper](https://arxiv.org/abs/2503.15547)]

6.  Progent: **"Progent: Programmable Privilege Control for LLM Agents"**. 
    *Tianneng Shi et al.* 2025. [[Paper](https://arxiv.org/abs/2504.11703)]

##### Specialized Domains

1.  LISA: **"LISA Technical Report: An Agentic Framework for Smart Contract Auditing"**. 
    *Izaiah Sun et al.* 2025. [[Paper](https://arxiv.org/abs/2509.24698)]

2.  SmartLLM: **"SmartLLM: Smart Contract Auditing Using Custom Generative AI"**. 
    *Jun Kevin and Pujianto Yugopuspito.* 2025. [[Paper](https://ieeexplore.ieee.org/document/11019687)]

3.  FineTuning-Auditing: **"Combining Fine-Tuning and LLM-Based Agents for Intuitive Smart Contract Auditing with Justifications"**. 
    *Wei Ma et al.* 2024. [[Paper](https://dl.acm.org/doi/10.1109/ICSE55347.2025.00027)]

4.  AuditGPT: **"AuditGPT: Auditing Smart Contracts with ChatGPT"**. 
    *Shihao Xia et al.* 2024. [[Paper](http://arxiv.org/abs/2404.04306)]

5.  HIPAA-Agent: **"Towards a HIPAA Compliant Agentic AI System in Healthcare"**. 
    *Subash Neupane et al.* 2025. [[Paper](https://arxiv.org/abs/2504.17669)]

6.  OneShield: **"Deploying Privacy Guardrails for LLMs: A Comparative Analysis of Real-World Applications"**. 
    *Shubhi Asthana et al.* 2025. [[Paper](https://arxiv.org/abs/2501.12456)]

7.  Embodied-AI-Security: **"Towards Robust and Secure Embodied AI: A Survey on Vulnerabilities and Attacks"**. 
    *Wenpeng Xing et al.* 2025. [[Paper](https://arxiv.org/abs/2502.13175)]

### Threats

#### Attack Surface

##### Injection Attacks

##### Poisoning & Extraction Attacks

##### Jailbreak Attacks

##### Agent Manipulation Attacks

##### Red-Teaming Attacks

#### Evaluation

##### Adversarial Benchmarks

##### Execution Environments

### Defenses

#### Defense & Operations

##### Secure-by-Design Architectures

##### Multi-Agent Security

##### Runtime Protection

##### Security Operations

#### Evaluation

##### Benchmarking Platforms

##### Defense Testing


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

## 📞 Contact
For inquiries regarding the survey, dataset updates, or collaboration, please contact:

Asif Shahriar 📧 asif.asr11@gmail.com 

---

## 📝 Citation


