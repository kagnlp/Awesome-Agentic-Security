# Awesome Agentic Security Papers

<p align="center">
  <a href="https://openreview.net/forum?id=Od4ZnAUv9T">
    <img src="https://img.shields.io/badge/TMLR-2026-4b44ce.svg" />
  </a>
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
<p align="center"><em>Transactions on Machine Learning Research (TMLR), 2026</em></p>
<!-- First Part (Original) -->
<p align="center"><strong>Authors:</strong> Asif Shahriar*, Md Nafiu Rahman*, Sadif Ahmed*, Farig Sadeque, Md Rizwan Parvez</p>
<p align="center">BRAC University, Qatar Computing Research Institute (QCRI)</p>

<div align="center">
    <img src="./assets/figure1_overview.png" width="90%"/>
</div>

<hr/>

## News

- **[Oct 2026]** Our survey has been accepted to **Transactions on Machine Learning Research (TMLR)** ([OpenReview](https://openreview.net/forum?id=Od4ZnAUv9T)). The paper list, taxonomy and all analysis figures in this repository now follow the camera-ready corpus of **274 papers**, including the new *Interface-Level Attacks* and *Why Alignment Fails in Agentic Settings* sections.

## Contributing to this paper list

Feel free to **open an issue/PR** or e-mail [asif.asr11@gmail.com](mailto:asif.asr11@gmail.com) if you find any missing areas, papers, or benchmarks. We will keep updating this list.

When opening a PR, add the paper to the most relevant subsection under [Papers](#papers), append it to the end of that list, and mark the short name with **†**, since new papers are not part of the survey's analyzed corpus:

```markdown
N.  ShortName†: **"Full Paper Title"**.
    *First Author et al.* Venue Year. [[Paper](https://link-to-paper)][[GitHub](https://link-to-code)]
```

## Survey Introduction

The move from passive language models to autonomous LLM-agents marks a major shift in cybersecurity. These agents can plan, invoke tools, and act in an external environment while observing feedback and adapting their actions. They can help with both attacking and defending systems, yet the same autonomy enlarges the attack surface: the safety alignment of a base model does not reliably transfer once it is given tools, memory, and autonomy.

This repository gathers the resources, taxonomy, and papers linked to the survey "A Survey on Agentic Security: Applications, Threats and Defenses." The survey is the first holistic study of the agentic security landscape, organizing **274 papers** around three questions a security researcher would ask:

1. **Applications** — *What can agents do for my security?* Red-teaming, blue-teaming, and domain-specific security agents.

2. **Threats** — *How can they be attacked?* Attack surfaces inherent to agentic systems and the frameworks used to evaluate them.

3. **Defenses** — *How do I stop them?* Techniques and countermeasures that harden agents, and the platforms used to test them.

For each pillar, the survey reviews the literature and then quantitatively analyzes the corpus (lifecycle coverage, autonomy, and dual-use for applications; entry points, failure stages, agent-specificity, threat models, and benchmarks for threats; strategies, cost trade-offs, and lifecycle placement for defenses), followed by a cross-cutting analysis of defense coverage, agent architecture, backbone models, and data modalities. A summary of these analyses is in the [Analysis](#analysis) section below.

Throughout the survey, an end-to-end agentic operation is modeled as an eight-stage loop, with memory, the tool/environment interface, and the inter-agent channel persisting across it:

<div align="center">
    <img src="./assets/anatomy_2.png" width="90%"/>
</div>

---

## Table of Contents

* [News](#news)
* [Survey Introduction](#survey-introduction)
* [Related Surveys](#related-surveys)
* [Papers](#papers)
    * [Applications](#applications)
        * [Red-Teaming](#red-teaming)
          * [Autonomous Penetration Testing](#autonomous-penetration-testing)
          * [Vulnerability Discovery & Fuzzing](#vulnerability-discovery--fuzzing)
          * [Exploit Generation & Adaptation](#exploit-generation--adaptation)
        * [Blue-Teaming](#blue-teaming)
          * [Autonomous Threat Detection & Incident Response](#autonomous-threat-detection--incident-response)
          * [Intelligent Threat Hunting](#intelligent-threat-hunting)
          * [Automated Forensics & Root Cause Analysis](#automated-forensics--root-cause-analysis)
          * [Autonomous Vulnerability Remediation](#autonomous-vulnerability-remediation)
        * [Domain-Specific Applications](#domain-specific-applications)
          * [Cloud & Infrastructure Security](#cloud--infrastructure-security)
          * [Web & Application Security](#web--application-security)
          * [Specialized Applications](#specialized-applications)
    * [Threats](#threats)
        * [Attack Surface](#attack-surface)
          * [Injection Attacks](#injection-attacks)
          * [Poisoning Attacks](#poisoning-attacks)
          * [Jailbreak Attacks](#jailbreak-attacks)
          * [Agent Manipulation Attacks](#agent-manipulation-attacks)
          * [Pre-execution Cognitive Attacks](#pre-execution-cognitive-attacks)
          * [Red-Teaming Attacks](#red-teaming-attacks)
          * [Interface-Level Attacks](#interface-level-attacks)
        * [Evaluation](#evaluation)
          * [Adversarial Benchmarking](#adversarial-benchmarking)
          * [Execution Environments](#execution-environments)
        * [Why Alignment Fails in Agentic Settings](#why-alignment-fails-in-agentic-settings)
    * [Defenses](#defenses)
        * [Defense & Operations](#defense--operations)
          * [Secure-by-Design](#secure-by-design)
          * [Multi-Agent Security](#multi-agent-security)
          * [Runtime Protection](#runtime-protection)
          * [Security Operations](#security-operations)
        * [Evaluation](#evaluation-1)
          * [Benchmarking Platforms](#benchmarking-platforms)
          * [Defense Testing](#defense-testing)
          * [Domain-Specific Frameworks](#domain-specific-frameworks)
* [Analysis](#analysis)
    * [Corpus Overview](#corpus-overview)
    * [Applications Analysis](#applications-analysis)
    * [Threats Analysis](#threats-analysis)
    * [Defenses Analysis](#defenses-analysis)
    * [Cross-Cutting Trends](#cross-cutting-trends)
* [Contributors](#contributors)

## Related Surveys

1.  Security of AI Agents: **"Security of AI Agents"**.
    *Yifeng He et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2406.08689)]

2.  Trustworthy Agents: **"A Survey on Trustworthy LLM Agents: Threats and Countermeasures"**.
    *Miao Yu et al.* KDD 2025. [[Paper](https://dl.acm.org/doi/10.1145/3637528.3671607)]

3.  TRISM: **"TRISM for Agentic AI: A Review of Trust, Risk, and Security Management in LLM-Based Agentic Multi-Agent Systems"**.
    *Shaina Raza et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2506.04133)]

4.  Agents Under Threat: **"AI Agents Under Threat: A Survey of Key Security Challenges and Future Pathways"**.
    *Zehang Deng et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2406.02630)]

5.  Safety at Scale: **"Safety at Scale: A Comprehensive Survey of Large Model and Agent Safety"**.
    *Xingjun Ma et al.* Foundations and Trends in Privacy and Security 2025. [[Paper](https://www.nowpublishers.com/article/Details/PSEC-030)]

6.  Multi-Agent Challenges: **"Open Challenges in Multi-Agent Security: Towards Secure Systems of Interacting AI Agents"**.
    *Christian Schroeder de Witt.* arXiv 2025. [[Paper](https://arxiv.org/abs/2505.02077)]

7.  Commercial Vulnerabilities: **"Commercial LLM Agents Are Already Vulnerable to Simple Yet Dangerous Attacks"**.
    *Ang Li et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2502.08586)]

8.  Agent Communication: **"A Survey of LLM-Driven AI Agent Communication: Protocols, Security Risks, and Defense Countermeasures"**.
    *Dezhang Kong et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2506.19676)]

9.  Full Stack Safety: **"A Comprehensive Survey in LLM(-Agent) Full Stack Safety: Data, Training and Deployment"**.
    *Kun Wang et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2504.15585)]

10. Agentic AI Security: **"Agentic AI Security: Threats, Defenses, Evaluation, and Open Challenges"**.
    *Anshuman Chhabra et al.* IEEE Access 2026. [[Paper](https://doi.org/10.1109/ACCESS.2026.3675554)]

## Papers

> Papers follow the survey's taxonomy. Entries marked **†** are not part of the survey's 274-paper corpus (for example, papers contributed after publication), so they are not reflected in the [Analysis](#analysis).

### Applications

#### Red-Teaming

##### Autonomous Penetration Testing

1.  PentestGPT: **"PentestGPT: Evaluating and Harnessing Large Language Models for Automated Penetration Testing"**.
    *Gelei Deng et al.* USENIX Security 2024. [[Paper](https://www.usenix.org/system/files/usenixsecurity24-deng.pdf)][[GitHub](https://github.com/GreyDGL/PentestGPT)]

2.  PentestAgent: **"PentestAgent: Incorporating LLM Agents to Automated Penetration Testing"**.
    *Xiangmin Shen et al.* ASIA CCS 2025. [[Paper](https://dl.acm.org/doi/10.1145/3708821.3733882)][[GitHub](https://github.com/nbshenxm/pentest-agent)]

3.  Vulnbot: **"VulnBot: Autonomous Penetration Testing for A Multi-Agent Collaborative Framework"**.
    *He Kong et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2501.13411)][[GitHub](https://github.com/KHenryAegis/VulnBot)]

4.  Aracne: **"Aracne: An LLM-based Autonomous Shell Pentesting Agent"**.
    *Tomas Nieponice et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2502.18528)][[Github](https://github.com/stratosphereips/aracne)]

5.  Cochise: **"Can LLMs Hack Enterprise Networks? Autonomous Assumed Breach Penetration-Testing Active Directory Networks"**.
    *Andreas Happe and Jürgen Cito.* ACM Trans. Softw. Eng. Methodol. 2025. [[Paper](https://dl.acm.org/doi/10.1145/3766895)][[GitHub](https://github.com/andreashappe/cochise)]

6.  RedTeamLLM: **"RedTeamLLM: An Agentic AI Framework for Offensive Security"**.
    *Brian Challita and Pierre Parrend.* arXiv 2025. [[Paper](https://arxiv.org/abs/2505.06913)][[GitHub](https://github.com/lre-security-systems-team/redteamllm)]

7.  Co-RedTeam: **"Co-RedTeam: Orchestrated Security Discovery and Exploitation with LLM Agents"**.
    *Pengfei He et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2602.02164)]

8.  CAI: **"CAI: An Open, Bug Bounty-Ready Cybersecurity AI"**.
    *Víctor Mayoral-Vilches et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2504.06017)][[GIthub](https://github.com/aliasrobotics/cai)]

9.  RapidPen: **"RapidPen: Fully Automated IP-to-Shell Penetration Testing with LLM-based Agents"**.
    *Sho Nakatani.* arXiv 2026. [[Paper](https://arxiv.org/abs/2502.16730)][[Zenodo](https://zenodo.org/records/14908250)]

10. AutoPentester: **"AutoPentester: An LLM Agent-based Framework for Automated Pentesting"**.
    *Yasod Ginige et al.* TrustCom 2025. [[Paper](https://doi.org/10.1109/Trustcom66490.2025.00026)][[Github](https://github.com/YasodGinige/AutoPentester)]

11. PenHeal: **"PenHeal: A Two-Stage LLM Framework for Automated Pentesting and Optimal Remediation"**.
    *Junjie Huang and Quanyan Zhu.* AutonomousCyber 2024. [[Paper](https://doi.org/10.1145/3689933.3690831)]

12. Enhancing Linux Privilege Escalation: **"Enhancing Linux Privilege Escalation Attack Capabilities of Local LLM Agents"**.
    *Benjamin Probst et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2604.27143)]

13. HackSynth: **"Hacksynth: LLM Agent and Evaluation Framework for Autonomous Penetration Testing"**.
    *Lajos Muzsai et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2412.01778)][[Github](https://github.com/aielte-research/HackSynth)]

14. AutoPentest: **"AutoPentest: Enhancing Vulnerability Management with Autonomous LLM Agents"**.
    *Julius Henke.* arXiv 2025. [[Paper](https://arxiv.org/abs/2505.10321)][[Github](https://github.com/JuliusHenke/autopentest)]

15. LLM-Pentest-Efficacy: **"On the Surprising Efficacy of LLMs for Penetration-Testing"**.
    *Andreas Happe and Jürgen Cito.* arXiv 2025. [[Paper](https://arxiv.org/abs/2507.00829)]

16. From-Capabilities-to-Performance: **"From Capabilities to Performance: Evaluating Key Functional Properties of LLM Architectures in Penetration Testing"**.
    *Huang et al.* EMNLP 2025. [[Paper](https://aclanthology.org/2025.emnlp-main.802/)]

17. What-Makes-Good-Agent: **"What Makes a Good LLM Agent for Real-world Penetration Testing?"**.
    *Gelei Deng et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2602.17622)]

18. Incalmo: **"Incalmo: An Autonomous LLM-assisted System for Red Teaming Multi-Host Networks"**.
    *Brian Singer et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2501.16466)][[Github](https://github.com/bsinger98/Incalmo)]

19. xOffense: **"xOffense: An AI-Driven Autonomous Penetration Testing Framework with Offensive Knowledge-Enhanced LLMs and Multi Agent Systems"**.
    *Phung Duc Luong et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2509.13021)]

20. AutoPenBench: **"AutoPenBench: Benchmarking Generative Agents for Penetration Testing"**.
    *Luca Gioacchini et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2410.03225)][[Github](https://github.com/lucagioacchini/auto-pen-bench)]

21. AI-Pentest-Benchmark: **"Towards automated penetration testing: Introducing LLM Benchmark, Analysis, and Improvements"**.
    *Isamu Isozaki et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2410.17141)][[Github](https://github.com/isamu-isozaki/AI-Pentest-Benchmark)]

22. Cybench: **"Cybench: A Framework for Evaluating Cybersecurity Capabilities and Risks of Language Models"**.
    *Andy K Zhang et al.* ICLR 2025. [[Paper](https://openreview.net/forum?id=tc90LV0yRL)][[Github](https://github.com/andyzorigin/cybench)]

23. BountyBench: **"BountyBench: Dollar Impact of AI Agent Attackers and Defenders on Real-World Cybersecurity Systems"**.
    *Andy K Zhang et al.* NeurIPS 2026. [[Paper](https://openreview.net/forum?id=pIsP4lMlFd)][[GitHub](https://github.com/bountybench/bountybench)]

24. EnIGMA: **"EnIGMA: Interactive Tools Substantially Assist LM Agents in Finding Security Vulnerabilities"**.
    *Talor Abramovich et al.* ICML 2025. [[Paper](https://openreview.net/forum?id=Of3wZhVv1R)][[GitHub](https://github.com/SWE-agent/SWE-agent)]

25. CTFAgent: **"CTFAgent: An LLM-powered Agent for CTF Challenge Solving"**.
    *Yuwen Zou et al.* JISA 2026. [[Paper](https://www.sciencedirect.com/science/article/pii/S2214212625003424)]

26. CTF-Dojo: **"Training Language Model Agents to Find Vulnerabilities with CTF-Dojo"**.
    *Terry Yue Zhuo et al.* NeurIPS Workshop 2025. [[Paper](https://openreview.net/forum?id=sQPeclxRBG)][[Github](https://github.com/amazon-science/CTF-Dojo)]

27. Cyber-Zero: **"Cyber-Zero: Training Cybersecurity Agents without Runtime"**.
    *Terry Yue Zhuo et al.* ICLR 2026. [[Paper](https://openreview.net/forum?id=1gRTeAik4G)][[Github](https://github.com/amazon-science/Cyber-Zero)]

##### Vulnerability Discovery & Fuzzing

1.  Locus: **"Locus: Agentic Predicate Synthesis for Directed Fuzzing"**.
    *Jie Zhu et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.21302)][[Github](https://github.com/jiezhuzzz/Locus)]

2.  ChatAFL: **"Large Language Model Guided Protocol Fuzzing"**.
    *Ruijie Meng et al.* NDSS 2024. [[Paper](https://www.ndss-symposium.org/ndss-paper/large-language-model-guided-protocol-fuzzing/)][[Github](https://github.com/ChatAFLndss/ChatAFL)]

3.  FirmAgent: **"FirmAgent: Leveraging Fuzzing to Assist LLM Agents with IoT Firmware Vulnerability Discovery"**.
    *Jiangan Ji et al.* NDSS 2026. [[Paper](https://www.ndss-symposium.org/ndss-paper/firmagent-leveraging-fuzzing-to-assist-llm-agents-with-iot-firmware-vulnerability-discovery/)][[Github](https://github.com/vul337/FirmAgent)]

4.  ChainFuzzer: **"ChainFuzzer: Greybox Fuzzing for Workflow-Level Multi-Tool Vulnerabilities in LLM Agents"**.
    *Jiangrong Wu et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2603.12614)]

5.  One-Day-Exploits: **"LLM Agents Can Autonomously Exploit One-Day Vulnerabilities"**.
    *Richard Fang et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2404.08144)]

6.  Zero-Day-Exploits: **"Teams of LLM Agents Can Exploit Zero-Day Vulnerabilities"**.
    *Yuxuan Zhu et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2406.01637)]

7.  A2: **"Agentic Discovery and Validation of Android App Vulnerabilities"**.
    *Ziyue Wang and Liyi Zhou.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.21579)]

8.  TTPDetect: **"Identifying Adversary Tactics and Techniques in Malware Binaries with an LLM Agent"**.
    *Zhou Xuan et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2602.06325)]

9.  Sec-Bench: **"Sec-bench: Automated Benchmarking of LLM Agents on Real-World Software Security Tasks"**.
    *Hwiwon Lee et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2506.11791)][[Github](https://github.com/SEC-bench/SEC-bench)]

10. CVE-Bench (Web): **"CVE-Bench: A Benchmark for AI Agents' Ability to Exploit Real-World Web Application Vulnerabilities"**.
    *Yuxuan Zhu et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2503.17332)][[Github](https://github.com/uiuc-kang-lab/cve-bench)]

11. CVE-bench (Repair): **"CVE-bench: Benchmarking LLM-based Software Engineering Agent's Ability to Repair Real-World CVE Vulnerabilities"**.
    *Peiran Wang et al.* NAACL 2025. [[Paper](https://aclanthology.org/2025.naacl-long.212/)]

12. CyberGym: **"CyberGym: Evaluating AI Agents' Real-World Cybersecurity Capabilities at Scale"**.
    *Zhun Wang et al.* ICLR 2026. [[Paper](https://openreview.net/forum?id=2YvbLQEdYt)][[Github](https://github.com/sunblaze-ucb/cybergym)][[HuggingFace](https://huggingface.co/datasets/sunblaze-ucb/cybergym)]

13. ZeroDayBench: **"ZeroDayBench: Evaluating LLM Agents on Unseen Zero-Day Vulnerabilities for Cyberdefense"**.
    *Nancy Lau et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2603.02297)]

14. SecRepoBench: **"SecRepoBench: Benchmarking Code Agents for Secure Code Completion in Real-World Repositories"**.
    *Chihao Shen et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2504.21205)][[Github](https://secrepobench.github.io/)]

15. SecVulEval: **"SecVulEval: Benchmarking LLMs for Real-World C/C++ Vulnerability Detection"**.
    *Md Basim Uddin Ahmed et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2505.19828)][[GitHub](https://github.com/basimbd/SecVulEval)]

16. JIT-Vuln-Detection: **"Benchmarking LLMs and LLM-based Agents in Practical Vulnerability Detection for Code Repositories"**.
    *Alperen Yildiz et al.* ACL 2025. [[Paper](https://aclanthology.org/2025.acl-long.1490/)][[Github](https://github.com/alperen21/JitVul)]

17. CWEval: **"CWEval: Outcome-driven Evaluation on Functionality and Security of LLM Code Generation"**.
    *Jinjun Peng et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2501.08200)][[GitHub](https://github.com/Co1lin/CWEval)]

18. LLM-Fuzzer: **"LLM-Fuzzer: Scaling Assessment of Large Language Model Jailbreaks"**.
    *Jiahao Yu et al.* USENIX Security 2024. [[Paper](https://www.usenix.org/system/files/usenixsecurity24-yu-jiahao.pdf)][[Github](https://github.com/sherdencooper/GPTFuzz)]

19. TitanFuzz: **"Large Language Models Are Zero-Shot Fuzzers: Fuzzing Deep-Learning Libraries via Large Language Models"**.
    *Yinlin Deng et al.* ISSTA 2023. [[Paper](https://dl.acm.org/doi/10.1145/3597926.3598067)][[Github](https://github.com/ise-uiuc/TitanFuzz)]

20. FuzzGPT: **"Large Language Models Are Edge-Case Generators: Crafting Unusual Programs for Fuzzing Deep Learning Libraries"**.
    *Yinlin Deng et al.* ICSE 2024. [[Paper](https://dl.acm.org/doi/10.1145/3597503.3623343)][[Github](https://github.com/ise-uiuc/FuzzGPT)]

21. ARTEMIS: **"Comparing AI Agents to Cybersecurity Professionals in Real-World Penetration Testing"**.
    *Justin W. Lin et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2512.09882)][[Github](https://github.com/Stanford-Trinity/ARTEMIS)]

##### Exploit Generation & Adaptation

1.  Dark-Side-Agents: **"The Dark Side of LLMs: Agent-Based Attacks for Complete Computer Takeover"**.
    *Matteo Lupinacci et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2507.06850)]

2.  MalGen: **"MalGen: A Generative Agent Framework for Modeling Malicious Software in Cybersecurity"**.
    *Bikash Saha and Sandeep Kumar Shukla.* arXiv 2025. [[Paper](https://arxiv.org/abs/2506.07586)]

3.  AiTM: **"Red-Teaming LLM Multi-Agent Systems via Communication Attacks"**.
    *Pengfei He et al.* ACL 2025. [[Paper](https://aclanthology.org/2025.findings-acl.349/)][[Github](https://github.com/PengfeiHePower/AiTM)]

4.  AttackLLM: **"AttackLLM: LLM-based Attack Pattern Generation for an Industrial Control System"**.
    *Chuadhry Mujeeb Ahmed.* FMSys 2025. [[Paper](https://doi.org/10.1145/3722565.3727196)]

5.  CVE-Genie: **"From CVE Entries to Verifiable Exploits: An Automated Multi-Agent Framework for Reproducing CVEs"**.
    *Saad Ullah et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2509.01835)][[Github](https://github.com/MaKyOtOx/cve-genie-prompts)]

6.  ReX: **"Prompt to Pwn: Automated Exploit Generation for Smart Contracts"**.
    *ZeKe Xiao et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2508.01371)][[Github](https://github.com/Crimson798/AEG-PoC)]

7.  VulnSage: **"A Multi-Agent Framework for Automated Exploit Generation with Constraint-Guided Comprehension and Reflection"**.
    *Siyi Chen et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2604.05130)][[Github](https://github.com/Vulnsage/VulnSage)]

8.  Smart-Contract-Exploit: **"AI Agent Smart Contract Exploit Generation"**.
    *Arthur Gervais and Liyi Zhou.* arXiv 2026. [[Paper](https://arxiv.org/abs/2507.05558)]

9.  LLM4CVE: **"LLM4CVE: Enabling Iterative Automated Vulnerability Repair with Large Language Models"**.
    *Mohamad Fakih et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2501.03446)][[Link](https://sites.google.com/view/llm4cve)]

#### Blue-Teaming

##### Autonomous Threat Detection & Incident Response

1.  AACT: **"Automated Alert Classification and Triage (AACT): An Intelligent System for the Prioritisation of Cybersecurity Alerts"**.
    *Melissa Turcotte et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2505.09843)]

2.  RAG-Incident-Response: **"Advancing Autonomous Incident Response: Leveraging LLMs and Cyber Threat Intelligence"**.
    *Amine Tellache et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.10677)]

3.  CyberRAG: **"CyberRAG: An Agentic RAG Cyber Attack Classification and Reporting Tool"**.
    *Francesco Blefari et al.* Future Generation Computer Systems 2026. [[Paper](https://doi.org/10.1016/j.future.2025.108186)]

4.  IRCopilot: **"IRCopilot: Automated Incident Response with Large Language Models"**.
    *Xihuan Lin et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2505.20945)][[Code](https://anonymous.4open.science/r/IRCopilot-78A0)]

5.  CORTEX: **"Cortex: Collaborative LLM Agents for High-Stakes Alert Triage"**.
    *Bowen Wei et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2510.00311)]

6.  IDS-Agent: **"IDS-Agent: An LLM Agent for Explainable Intrusion Detection in IoT Networks"**.
    *Yanjie Li et al.* NeurIPS Workshop 2024. [[Paper](https://openreview.net/forum?id=iiK0pRyLkw)]

7.  AutoBnB: **"AutoBnB: Multi-Agent Incident Response with Large Language Models"**.
    *Zefang Liu.* ISDFS 2025. [[Paper](https://ieeexplore.ieee.org/document/11012055)][[Github](https://github.com/zefang-liu/AutoBnB)]

8.  In-Context-Incident-Response: **"In-Context Autonomous Network Incident Response: An End-to-End Large Language Model Agent Approach"**.
    *Yiran Gao et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2602.13156)]

9.  LLM-in-the-SOC-Empirical-Study: **"LLMs in the SOC: An Empirical Study of Human-AI Collaboration in Security Operations Centres"**.
    *Ronal Singh et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.18947)][[Github](https://github.com/eSentire-Labs/LLM-Gateway)]

10. CyberSOCEval: **"CyberSOCEval: Benchmarking LLMs Capabilities for Malware Analysis and Threat Intelligence Reasoning"**.
    *Lauren Deason et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2509.20166)][[Data](https://github.com/CrowdStrike/CyberSOCEval_data)][[Github](https://github.com/meta-llama/PurpleLlama)]

11. CTI-REALM: **"CTI-REALM: Benchmark to Evaluate Agent Performance on Security Detection Rule Generation Capabilities"**.
    *Arjun Chakraborty et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2603.13517)]

12. Log-Analysis-Survey†: **"Automated Threat Detection and Response Using LLM Agents"**.
    *Ramasankar Molleti et al.* World Journal of Advanced Research and Reviews 2024. [[Paper](https://wjarr.com/sites/default/files/WJARR-2024-3329.pdf)]

##### Intelligent Threat Hunting

1.  LLM-Automate-Threat: **"Using LLMs to Automate Threat Intelligence Analysis Workflows in Security Operation Centers"**.
    *PeiYu Tseng et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2407.13093)]

2.  ProvSEEK: **"LLM-Driven Provenance Forensics for Threat Investigation and Detection"**.
    *Kunal Mukherjee and Murat Kantarcioglu.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.21323)][[Github](https://anonymous.4open.science/r/provseek-anonymous-DDDD)]

3.  CTI-Vulnerabilities: **"Uncovering Vulnerabilities of LLM-Assisted Cyber Threat Intelligence"**.
    *Yuqiao Meng et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2509.23573)][[Github](https://github.com/mengyuqiao/LLM-CTI)]

4.  LLMCloudHunter: **"LLMCloudHunter: Harnessing LLMs for Automated Extraction of Detection Rules from Cloud-Based CTI"**.
    *Yuval Schwartz et al.* WWW 2025. [[Paper](https://dl.acm.org/doi/10.1145/3696410.3714798)][[Github](https://github.com/YuvalSchwartz/llm-cloud-hunter)]

5.  Security-Logs-ATT&CK: **"Security Logs to ATT&CK Insights: Leveraging LLMs for High-Level Threat Understanding and Cognitive Trait Inference"**.
    *Soham Hans et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2510.20930)]

6.  Cyber-Defense-Benchmark: **"Cyber Defense Benchmark: Agentic Threat Hunting Evaluation for LLMs in SecOps"**.
    *Alankrit Chona et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2604.19533)][[Github](https://github.com/simbianai/cyber_defense_benchmark)]

##### Automated Forensics & Root Cause Analysis

1.  RepoAudit: **"RepoAudit: An Autonomous LLM-Agent for Repository-Level Code Auditing"**.
    *Jinyao Guo et al.* ICML 2025. [[Paper](https://openreview.net/pdf?id=TXcifVbFpG)][[Github](https://github.com/PurCL/RepoAudit)]

2.  LLM-Cloud-Forensics: **"LLM-Powered Automated Cloud Forensics: From Log Analysis to Investigation"**.
    *Dalal Alharthi and Rozhin Yasaei.* IEEE CLOUD 2025. [[Paper](https://ieeexplore.ieee.org/document/11120597)]

3.  CyberSleuth: **"CyberSleuth: Autonomous Blue-Team LLM Agent for Web Attack Forensics"**.
    *Stefano Fumero et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.20643)][[Github](https://github.com/SmartData-Polito/LLM_Agent_Cybersecurity_Forensic)]

4.  GALA: **"GALA: Can Graph-Augmented Large Language Model Agentic Workflows Elevate Root Cause Analysis?"**.
    *Yifang Tian et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.12472)]

5.  MAST: **"Why Do Multiagent Systems Fail?"**.
    *Melissa Z Pan et al.* ICLR Workshop 2025. [[Paper](https://openreview.net/pdf?id=wM521FqPvI)][[Github](https://github.com/multi-agent-systems-failure-taxonomy/MAST)]

6.  CIAF: **"Cloud Investigation Automation Framework (CIAF): An AI-Driven Approach to Cloud Forensics"**.
    *Dalal Alharthi and Ivan Roberto Kawaminami Garcia.* arXiv 2025. [[Paper](https://arxiv.org/abs/2510.00452)]

##### Autonomous Vulnerability Remediation

1.  RepairAgent: **"RepairAgent: An Autonomous, LLM-Based Agent for Program Repair"**.
    *Islem Bouzenia et al.* ICSE 2025. [[Paper](https://dl.acm.org/doi/10.1109/ICSE55347.2025.00157)][[Github](https://github.com/sola-st/RepairAgent)]

2.  Gemini-Patching†: **"AI-Powered Patching: The Future of Automated Vulnerability Fixes"**.
    *Jan Keller and Jan Nowakowski.* Technical Report 2024. [[Link](https://research.google/pubs/ai-powered-patching-the-future-of-automated-vulnerability-fixes/)]

3.  IaC-Remediation: **"LLM Agentic Workflow for Automated Vulnerability Detection and Remediation in Infrastructure-as-Code"**.
    *Dheer Toprani and Vijay K. Madisetti.* IEEE Access 2025. [[Paper](https://ieeexplore.ieee.org/document/10965635)]

4.  VulnRepairEval: **"VulnRepairEval: An Exploit-Based Evaluation Framework for Assessing Large Language Model Vulnerability Repair Capabilities"**.
    *Weizhe Wang et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2509.03331)]

5.  PatchEval: **"PatchEval: A New Benchmark for Evaluating LLMs on Patching Real-World Vulnerabilities"**.
    *Zichao Wei et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2511.11019)][[GitHub](https://github.com/bytedance/PatchEval)]

6.  Red-Teaming-Repair: **"Red Teaming Program Repair Agents: When Correct Patches Can Hide Vulnerabilities"**.
    *Simin Chen et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2509.25894)][[Github](https://github.com/HeyixInn/SWExploit/tree/main)]

#### Domain-Specific Applications

##### Cloud & Infrastructure Security

1.  Cloud-Infrastructure-AI-Agent: **"Cloud Infrastructure Management in the Age of AI Agents"**.
    *Zhenning Yang et al.* ACM SIGOPS Operating Systems Review 2025. [[Paper](https://dl.acm.org/doi/10.1145/3759441.3759443)]

2.  KubeIntellect: **"KubeIntellect: A Modular LLM-Orchestrated Agent Framework for End-to-End Kubernetes Management"**.
    *Mohsen Seyedkazemi Ardebili and Andrea Bartolini.* 2025. [[Paper](https://arxiv.org/abs/2509.02449)][[Github](https://github.com/MSKazemi/KubeIntellect)]

3.  LLMSecConfig: **"LLMSecConfig: An LLM-Based Approach for Fixing Software Container Misconfigurations"**.
    *Ziyang Ye et al.* 2025. [[Paper](https://www.computer.org/csdl/proceedings-article/msr/2025/018300a629/27vTruUNcXe)]

4.  BARTPredict: **"BARTPredict: Empowering IoT Security with LLM-Driven Cyber Threat Prediction"**.
    *Alaeddine Diaf et al.* 2025. [[Paper](https://ieeexplore.ieee.org/document/10901770)]

5.  IoT-Edge-Attack-Surface: **"Systems-Level Attack Surface of Edge Agent Deployments on IoT"**.
    *Zhonghao Zhan et al.* EuroMLSys 2026. [[Paper](https://doi.org/10.1145/3805621.3807636)]

##### Web & Application Security

1.  MAPTA: **"Multi-Agent Penetration Testing AI for the Web"**.
    *Isaac David and Arthur Gervais.* 2025. [[Paper](https://arxiv.org/abs/2508.20816)][[Github](https://github.com/arthurgervais/mapta)]

2.  PTFusion: **"PTFusion: LLM-driven Context-Aware Knowledge Fusion for Web Penetration Testing"**.
    *Wenhao Wang et al.* Information Fusion 2026. [[Paper](https://www.sciencedirect.com/science/article/pii/S1566253525007936)]

3.  LLM-Agents-Automated-Web: **"LLM Agents for Automated Web Vulnerability Reproduction: Are We There Yet?"**.
    *Bin Liu et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2510.14700)]

4.  Browsing-Dangers: **"The Hidden Dangers of Browsing AI Agents"**.
    *Mykyta Mudryi et al.* 2025. [[Paper](https://arxiv.org/abs/2505.13076)][[GIthub](https://github.com/arimlabs/agent-hijacking-poc)]

5.  Prompt-to-SQL: **"Prompt-to-SQL Injections in LLM-Integrated Web Applications: Risks and Defenses"**.
    *Rodrigo Pedro et al.* ICSE 2025. [[Paper](https://doi.org/10.1109/ICSE55347.2025.00007)]

6.  AIOS: **"AIOS: LLM Agent Operating System"**.
    *Kai Mei et al.* Conference on Language Modeling 2025. [[Paper](https://openreview.net/pdf?id=L4HHkCDz2x)][[Github](https://github.com/agiresearch/AIOS)]

7.  Securing-AI-Agents-Like-OS: **"Toward Securing AI Agents Like Operating Systems"**.
    *Lukas Pirch et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2605.14932)]

8.  OpenClaw-Security: **"A Security Analysis of the OpenClaw AI Agent Framework"**.
    *Surada Suwansathit et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2603.27517)][[GitHub](https://github.com/openclaw/openclaw)]

9.  AgentAudit: **"Agent Audit: A Security Analysis System for LLM Agent Applications"**.
    *Haiyue Zhang et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2603.22853)][[Github](https://github.com/HeadyZhang/agent-audit)]

10. Prompt-Flow-Integrity: **"Prompt Flow Integrity to Prevent Privilege Escalation in LLM Agents"**.
    *Juhee Kim et al.* 2025. [[Paper](https://arxiv.org/abs/2503.15547)][[Github](https://github.com/compsec-snu/pfi)]

11. Progent: **"Progent: Programmable Privilege Control for LLM Agents"**.
    *Tianneng Shi et al.* 2025. [[Paper](https://arxiv.org/abs/2504.11703)][[Github](https://github.com/sunblaze-ucb/progent)]

##### Specialized Applications

1.  LLM-SmartAudit: **"Advanced Smart Contract Vulnerability Detection via LLM-Powered Multi-Agent Systems"**.
    *Zhiyuan Wei et al.* IEEE TSE 2025. [[Paper](https://ieeexplore.ieee.org/document/11019687)]

2.  SmartLLM: **"SmartLLM: Smart Contract Auditing Using Custom Generative AI"**.
    *Jun Kevin and Pujianto Yugopuspito.* 2025. [[Paper](https://ieeexplore.ieee.org/document/11019687)]

3.  FineTuning-Auditing: **"Combining Fine-Tuning and LLM-Based Agents for Intuitive Smart Contract Auditing with Justifications"**.
    *Wei Ma et al.* 2024. [[Paper](https://dl.acm.org/doi/10.1109/ICSE55347.2025.00027)]

4.  AuditGPT: **"AuditGPT: Auditing Smart Contracts with ChatGPT"**.
    *Shihao Xia et al.* 2024. [[Paper](http://arxiv.org/abs/2404.04306)][[Github](https://github.com/pratraut/auditgpt)]

5.  ReCopilot: **"ReCopilot: Reverse Engineering Copilot in Binary Analysis"**.
    *Guoqiang Chen et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2505.16366)]

6.  MalParse: **"Exploring Large Language Models for Semantic Analysis and Categorization of Android Malware"**.
    *Brandon J Walton et al.* ACSAC Workshops 2024. [[Paper](https://doi.ieeecomputersociety.org/10.1109/ACSACW65225.2024.00035)]

7.  OT-Deception: **"Network and Device Level Cyber Deception for Contested Environments Using RL and LLMs"**.
    *Abhijeet Sahu et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2603.17272)]

8.  HIPAA-Agent: **"Towards a HIPAA Compliant Agentic AI System in Healthcare"**.
    *Subash Neupane et al.* 2025. [[Paper](https://arxiv.org/abs/2504.17669)]

9.  LLM-Privacy-GuardRails: **"Deploying Privacy Guardrails for LLMs: A Comparative Analysis of Real-World Applications"**.
    *Shubhi Asthana et al.* 2025. [[Paper](https://arxiv.org/abs/2501.12456)]

### Threats

#### Attack Surface

##### Injection Attacks

1.  Polymorphic Prompt: **"To Protect the LLM Agent Against the Prompt Injection Attack with Polymorphic Prompt"**.
    *Zhilong Wang et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2506.05739)][[Github](https://github.com/zhilongwang/LLMAgentProtector)]

2.  AgentDojo: **"AgentDojo: A Dynamic Environment to Evaluate Prompt Injection Attacks and Defenses for LLM Agents"**.
    *Edoardo Debenedetti et al.* NeurIPS 2024. [[Paper](https://arxiv.org/abs/2406.13352)][[Github](https://github.com/ethz-spylab/agentdojo)]

3.  App-Injection: **"Prompt Injection Attack Against LLM-Integrated Applications"**.
    *Yi Liu et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2306.05499)][[Github](https://github.com/LLMSecurity/HouYi)]

4.  ToolHijacker: **"Prompt Injection Attack to Tool Selection in LLM Agents"**.
    *Jiawen Shi et al.* NDSS 2026. [[Paper](https://dx.doi.org/10.14722/ndss.2026.230675)]

5.  Imprompter: **"Imprompter: Tricking LLM Agents into Improper Tool Use"**.
    *Xiaohan Fu et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2410.14923)][[GitHub](https://github.com/Reapor-Yurnero/imprompter)]

6.  WebInject: **"WebInject: Prompt Injection Attack to Web Agents"**.
    *Xilong Wang et al.* EMNLP 2025. [[Paper](https://aclanthology.org/2025.emnlp-main.802/)]

7.  HTML-Accessibility-Injection: **"Manipulating LLM Web Agents with Indirect Prompt Injection Attack via HTML Accessibility Tree"**.
    *Sam Johnson et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2507.14799)][[GitHub](https://github.com/sej2020/manipulating-web-agents)]

8.  InjecAgent: **"InjecAgent: Benchmarking Indirect Prompt Injections in Tool-Integrated Large Language Model Agents"**.
    *Qiusi Zhan et al.* ACL 2024. [[Paper](https://arxiv.org/abs/2403.02691)][[Github](https://github.com/uiuc-kang-lab/InjecAgent)]

9.  Commercial-Agent-Vulnerability: **"Commercial LLM Agents Are Already Vulnerable to Simple Yet Dangerous Attacks"**.
    *Ang Li et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2502.08586)]

10. BIPIA: **"Benchmarking and Defending Against Indirect Prompt Injection Attacks on Large Language Models"**.
    *Jingwei Yi et al.* KDD 2025. [[Paper](https://dl.acm.org/doi/10.1145/3690624.3709179)][[Github](https://github.com/microsoft/BIPIA)]

11. Prompt Infection: **"Prompt Infection: LLM-to-LLM Prompt Injection Within Multi-Agent Systems"**.
    *Donghyun Lee and Mo Tiwari.* arXiv 2024. [[Paper](https://arxiv.org/abs/2410.07283)]

12. Data Leakage: **"Simple Prompt Injection Attacks Can Leak Personal Data Observed by LLM Agents During Task Execution"**.
    *Meysam Alizadeh et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2506.01055)]

13. AgentVigil: **"AgentVigil: Generic Black-Box Red-Teaming for Indirect Prompt Injection Against LLM Agents"**.
    *Zhun Wang et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2505.05849)]

14. ASB: **"Agent Security Bench (ASB): Formalizing and Benchmarking Attacks and Defenses in LLM-Based Agents"**.
    *Hanrong Zhang et al.* ICLR 2025. [[Paper](https://openreview.net/forum?id=V4y0CpX4hK)][[Github](https://github.com/agiresearch/ASB)]

15. Adaptive Attacks: **"Adaptive Attacks Break Defenses Against Indirect Prompt Injection Attacks on LLM Agents"**.
    *Qiusi Zhan et al.* NAACL 2025. [[Paper](https://aclanthology.org/2025.findings-naacl.395/)][[Github](https://github.com/uiuc-kang-lab/AdaptiveAttackAgent)]

16. Formalizing-PI: **"Formalizing and Benchmarking Prompt Injection Attacks and Defenses"**.
    *Yupei Liu et al.* USENIX Security 2024. [[Paper](https://arxiv.org/abs/2310.12815)][[Github](https://github.com/liu00222/Open-Prompt-Injection)]

17. Poisoning-Alignment-PI: **"Enhancing Prompt Injection Attacks to LLMs via Poisoning Alignment"**.
    *Zedian Shao et al.* ACM AISec 2025. [[Paper](https://arxiv.org/abs/2410.14827)][[Github](https://github.com/Sadcardation/PoisonedAlign)]

18. AutoDAN: **"AutoDAN: Generating Stealthy Jailbreak Prompts on Aligned Large Language Models"**.
    *Xiaogeng Liu et al.* ICLR 2024. [[Paper](https://openreview.net/forum?id=7Jwpw4qKkb)]

19. GCG: **"Universal and Transferable Adversarial Attacks on Aligned Language Models"**.
    *Andy Zou et al.* arXiv 2023. [[Paper](https://arxiv.org/abs/2307.15043)]

##### Poisoning Attacks

1.  Poisoning Attacks Review: **"A Systematic Review of Poisoning Attacks Against Large Language Models"**.
    *Neil Fendley et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2506.06518)]

2.  AgentPoison: **"AgentPoison: Red-Teaming LLM Agents via Poisoning Memory or Knowledge Bases"**.
    *Zhaorun Chen et al.* NeurIPS 2024. [[Paper](https://arxiv.org/abs/2407.12784)][[Github](https://github.com/AI-secure/AgentPoison)]

3.  PoisonBench: **"PoisonBench: Assessing Large Language Model Vulnerability to Poisoned Preference Data"**.
    *Tingchen Fu et al.* ICML 2025. [[Paper](https://openreview.net/pdf?id=21kAulloDG)][[Github](https://github.com/TingchenFu/PoisonBench)]

4.  Poisoning Trends: **"Scaling Trends for Data Poisoning in LLMs"**.
    *Dillon Bowen et al.* AAAI 2025. [[Paper](http://ojs.aaai.org/index.php/AAAI/article/view/34929)][[Github](https://github.com/AlignmentResearch/scaling-poisoning)]

5.  Poison-with-Style: **"Poison with Style: A Practical Poisoning Attack on Code Large Language Models"**.
    *Khang Tran et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2605.27631)]

6.  VisualTrap: **"VisualTrap: A Stealthy Backdoor Attack on GUI Agents via Visual Grounding Manipulation"**.
    *Ziang Ye et al.* CoLM 2025. [[Paper](https://openreview.net/forum?id=7HPuAkgdVm)]

7.  MALICE: **"Malice in Agentland: Down the Rabbit Hole of Backdoors in the AI Supply Chain"**.
    *Léo Boisvert et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2510.05159)]

8.  RAG-Thief: **"RAG-Thief: Scalable Extraction of Private Data from Retrieval-Augmented Generation Applications with Agent-based Attacks"**.
    *Changyue Jiang et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2411.14110)]

9.  ASB: **"Agent Security Bench (ASB): Formalizing and Benchmarking Attacks and Defenses in LLM-Based Agents"**.
    *Hanrong Zhang et al.* ICLR 2025. [[Paper](https://openreview.net/forum?id=V4y0CpX4hK)][[Github](https://github.com/agiresearch/ASB)]

10. Memory-Injection-NeurIPS: **"Memory Injection Attacks on LLM Agents via Query-Only Interaction"**.
    *Shen Dong et al.* NeurIPS 2025. [[Paper](https://openreview.net/forum?id=QINnsnppv8)][[Github](https://github.com/dsh3n77/MINJA)]

##### Jailbreak Attacks

1.  LLMs are not Aligned Browser Agents: **"Aligned LLMs Are Not Aligned Browser Agents"**.
    *Priyanshu Kumar et al.* ICLR 2025. [[Paper](https://arxiv.org/abs/2405.18561)]

2.  Web Vulnerability: **"Why Are Web AI Agents More Vulnerable Than Standalone LLMs? A Security Analysis"**.
    *Jeffrey Yang Fan Chiang et al.* ICLR Workshop 2025. [[Paper](https://openreview.net/forum?id=4KoMbO2RJ9)]

3.  JAWS-BENCH: **"Breaking the Code: Security Assessment of AI Code Agents Through Systematic Jailbreaking Attacks"**.
    *Shoumik Saha et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2510.01359)]

4.  LLM-Fuzzer: **"LLM-Fuzzer: Scaling Assessment of Large Language Model Jailbreaks"**.
    *Jiahao Yu et al.* USENIX Security 2024. [[Paper](https://www.usenix.org/system/files/usenixsecurity24-yu-jiahao.pdf)][[Github](https://github.com/sherdencooper/GPTFuzz)]

5.  Many-Shot Jailbreak: **"Many-Shot Jailbreaking"**.
    *Cem Anil et al.* NeurIPS 2024. [[Paper](https://arxiv.org/abs/2404.08138)]

6.  Paper-Summary-Attack: **"Paper Summary Attack: Jailbreaking LLMs through LLM Safety Papers"**.
    *Liang Lin et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2507.13474)][[GitHub](https://github.com/233liang/Paper-Summary-Attack)]

7.  Robot Jailbreak: **"Jailbreaking LLM-Controlled Robots"**.
    *Alexander Robey et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2410.13691)][[Github](https://github.com/arobey1/robopair)]

8.  Jailbroken: **"Jailbroken: How Does LLM Safety Training Fail?"**.
    *Alexander Wei et al.* NeurIPS 2023. [[Paper](https://proceedings.neurips.cc/paper_files/paper/2023/hash/fd6613131889a4b656206c50a8bd7790-Abstract-Conference.html)]

9.  GCG: **"Universal and Transferable Adversarial Attacks on Aligned Language Models"**.
    *Andy Zou et al.* arXiv 2023. [[Paper](https://arxiv.org/abs/2307.15043)]

10. Jailbreak-Survey: **"A Comprehensive Study of Jailbreak Attack versus Defense for Large Language Models"**.
    *Zihao Xu et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2402.13457)]

11. AgentHarm: **"AgentHarm: A Benchmark for Measuring Harmfulness of LLM Agents"**.
    *Maksym Andriushchenko et al.* ICLR 2025. [[Paper](https://arxiv.org/abs/2410.09024)][[Hugging Face](https://huggingface.co/datasets/ai-safety-institute/AgentHarm)]

##### Agent Manipulation Attacks

1.  PromptInject: **"Ignore Previous Prompt: Attack Techniques for Language Models"**.
    *Fábio Perez and Ian Ribeiro.* arXiv 2022. [[Paper](https://arxiv.org/abs/2211.09527)][[Github](https://github.com/agencyenterprise/PromptInject)]

2.  CAIN: **"CAIN: Hijacking LLM-Humans Conversations via a Two-Stage Malicious System Prompt Generation and Refining Framework"**.
    *Viet Pham and Thai Le.* arXiv 2025. [[Paper](https://arxiv.org/abs/2505.16888)][[Github](https://github.com/vietph34/CAIN)]

3.  PseudoConversation Injection: **"Pseudo-Conversation Injection for LLM Goal Hijacking"**.
    *Zheng Chen and Buhui Yao.* arXiv 2024. [[Paper](https://arxiv.org/abs/2410.23678)]

4.  AI²: **"Towards Action Hijacking of Large Language Model-Based Agent"**.
    *Yuyang Zhang et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2412.10807)]

5.  InfoRM: **"InfoRM: Mitigating Reward Hacking in RLHF via Information-Theoretic Reward Modeling"**.
    *Yuchun Miao et al.* 2024. [[Paper](https://proceedings.neurips.cc/paper_files/paper/2024/file/f25d75fc760aec0a6174f9f5d9da59b8-Paper-Conference.pdf)][[Github](https://github.com/miaoyuchun/InfoRM)]

6.  Preference as Reward (PAR): **"Reward Shaping to Mitigate Reward Hacking in RLHF"**.
    *Jiayi Fu et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2502.18770)][[Github](https://github.com/PorUna-byte/PAR)]

7.  Spec Gaming: **"Demonstrating Specification Gaming in Reasoning Models"**.
    *Alexander Bondarenko et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2502.13295)][[Github](https://github.com/palisaderesearch/ctfish)]

8.  BARDec-POMDP: **"Byzantine Robust Cooperative Multi-Agent Reinforcement Learning as a Bayesian Game"**.
    *Simin Li et al.* ICLR 2024. [[Paper](https://openreview.net/forum?id=z6KS9D1dxt&noteId=bmQTLbJlRL)][[Github](https://github.com/DIG-Beihang/EIR-MAPPO)]

9.  Byzantine Coord: **"Byzantine-Robust Decentralized Coordination of LLM Agents"**.
    *Yongrae Jo and Chanik Park.* arXiv 2025. [[Paper](https://arxiv.org/abs/2507.14928)]

10. AIOps-Manipulation: **"When AIOps Become 'AI Oops': Subverting LLM-driven IT Operations via Telemetry Manipulation"**.
    *Dario Pasquini et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.06394)]

11. AgentDoS: **"Autonomy Comes with Costs: Detecting Denial-of-Service Vulnerabilities Caused by Resource Abusing in LLM-based Agents"**.
    *Jiaqi Luo et al.* USENIX Security 2026. [[Paper](https://www.usenix.org/conference/usenixsecurity26)]

12. Reward-Hacking: **"Defining and Characterizing Reward Hacking"**.
    *Joar Skalse et al.* NeurIPS 2022. [[Paper](https://arxiv.org/abs/2209.13085)]

13. Advertisement Embedding Attacks: **"Attacking LLMs and AI Agents: Advertisement Embedding Attacks Against Large Language Models"**.
    *Qiming Guo et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.17674)]

14. Reward-Misspecification: **"The Effects of Reward Misspecification: Mapping and Mitigating Misaligned Models"**.
    *Alexander Pan et al.* NeurIPS Deep RL Workshop 2021. [[Paper](https://openreview.net/forum?id=mp1AstNFvQ5)]

##### Pre-execution Cognitive Attacks

1.  Indirect-Prompt-Injection-Apps: **"Not What You've Signed Up For: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection"**.
    *Kai Greshake et al.* AISec 2023. [[Paper](https://doi.org/10.1145/3605764.3623985)]

2.  Watch-Out-Agents: **"Watch Out for Your Agents! Investigating Backdoor Threats to LLM-Based Agents"**.
    *Wenkai Yang et al.* NeurIPS 2024. [[Paper](https://openreview.net/forum?id=Nf4MHF1pi5)]

3.  ScamAgents: **"ScamAgents: How AI Agents Can Simulate Human-Level Scam Calls"**.
    *Sanket Badhe.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.06457)]

4.  Reasoning-Style-Poisoning: **"Reasoning-Style Poisoning of LLM Agents via Stealthy Style Transfer: Process-Level Attacks and Runtime Monitoring in RSV Space"**.
    *Xingfu Zhou and Pengfei Wang.* arXiv 2025. [[Paper](https://arxiv.org/abs/2512.14448)]

5.  Skill-Inject: **"Skill-Inject: Measuring Agent Vulnerability to Skill File Attacks"**.
    *David Schmotz et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2602.20156)]

##### Red-Teaming Attacks

1.  Red Teaming LMs: **"Red Teaming Language Models with Language Models"**.
    *Ethan Perez et al.* arXiv 2022. [[Paper](https://arxiv.org/abs/2202.03286)]

2.  MART: **"MART: Improving LLM Safety with Multi-Round Automatic Red-Teaming"**.
    *Suyu Ge et al.* arXiv 2023. [[Paper](https://arxiv.org/abs/2311.07689)]

3.  AiTM: **"Red-Teaming LLM Multi-Agent Systems via Communication Attacks"**.
    *Pengfei He et al.* ACL 2025. [[Paper](https://aclanthology.org/2025.findings-acl.349/)][[Github](https://github.com/PengfeiHePower/AiTM)]

4.  AgentFuzz: **"Make Agent Defeat Agent: Automatic Detection of Taint-Style Vulnerabilities in LLM-Based Agents"**.
    *Fengyu Liu et al.* USENIX Security 2025. [[Paper](https://www.usenix.org/conference/usenixsecurity25/presentation/liu-fengyu)][[Code](https://zenodo.org/records/15590097)]

5.  Privacy Risks: **"Searching for Privacy Risks in LLM Agents via Simulation"**.
    *Yanzhe Zhang and Diyi Yang.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.10880)][[Github](https://github.com/SALT-NLP/search_privacy_risk)]

6.  xTeaming: **"X-Teaming: Multi-Turn Jailbreaks and Defenses with Adaptive Multi-Agents"**.
    *Salman Rahman et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2504.13203)]

7.  AgentDoS: **"Autonomy Comes with Costs: Detecting Denial-of-Service Vulnerabilities Caused by Resource Abusing in LLM-based Agents"**.
    *Jiaqi Luo et al.* USENIX Security 2026. [[Paper](https://www.usenix.org/conference/usenixsecurity26)]

8.  AIOps-Manipulation: **"When AIOps Become 'AI Oops': Subverting LLM-driven IT Operations via Telemetry Manipulation"**.
    *Dario Pasquini et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.06394)]

##### Interface-Level Attacks

1.  Commercial-Agent-Vulnerability: **"Commercial LLM Agents Are Already Vulnerable to Simple Yet Dangerous Attacks"**.
    *Ang Li et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2502.08586)]

2.  MIP: **"MIP against Agent: Malicious Image Patches Hijacking Multimodal OS Agents"**.
    *Lukas Aichberger et al.* NeurIPS 2025. [[Paper](https://openreview.net/forum?id=ToNRHqX6xq)]

3.  HTML-Accessibility-Injection: **"Manipulating LLM Web Agents with Indirect Prompt Injection Attack via HTML Accessibility Tree"**.
    *Sam Johnson et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2507.14799)][[GitHub](https://github.com/sej2020/manipulating-web-agents)]

4.  CUA-Systematization: **"A Systematization of Security Vulnerabilities in Computer Use Agents"**.
    *Daniel Jones et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2507.05445)]

5.  WebInject: **"WebInject: Prompt Injection Attack to Web Agents"**.
    *Xilong Wang et al.* EMNLP 2025. [[Paper](https://aclanthology.org/2025.emnlp-main.802/)]

6.  VisualTrap: **"VisualTrap: A Stealthy Backdoor Attack on GUI Agents via Visual Grounding Manipulation"**.
    *Ziang Ye et al.* CoLM 2025. [[Paper](https://openreview.net/forum?id=7HPuAkgdVm)]

7.  Pop-up Attack: **"Attacking Vision-Language Computer Agents via Pop-ups"**.
    *Yanzhe Zhang et al.* ACL 2025. [[Paper](https://arxiv.org/abs/2411.02391)][[GitHub](https://github.com/SALT-NLP/PopupAttack)]

#### Evaluation

##### Adversarial Benchmarking

1.  ASB: **"Agent Security Bench (ASB): Formalizing and Benchmarking Attacks and Defenses in LLM-Based Agents"**.
    *Hanrong Zhang et al.* ICLR 2025. [[Paper](https://openreview.net/forum?id=V4y0CpX4hK)][[Github](https://github.com/agiresearch/ASB)]

2.  RAS-Eval: **"RAS-Eval: A Comprehensive Benchmark for Security Evaluation of LLM Agents in Real-World Environments"**.
    *Yuchuan Fu et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2506.15253)][[Github](https://github.com/lanzer-tree/RAS-Eval)]

3.  AgentDojo: **"AgentDojo: A Dynamic Environment to Evaluate Prompt Injection Attacks and Defenses for LLM Agents"**.
    *Edoardo Debenedetti et al.* NeurIPS 2024. [[Paper](https://arxiv.org/abs/2406.13352)][[Github](https://github.com/ethz-spylab/agentdojo)]

4.  AgentHarm: **"AgentHarm: A Benchmark for Measuring Harmfulness of LLM Agents"**.
    *Maksym Andriushchenko et al.* ICLR 2025. [[Paper](https://arxiv.org/abs/2410.09024)][[Hugging Face](https://huggingface.co/datasets/ai-safety-institute/AgentHarm)]

5.  SafeArena: **"SafeArena: Evaluating the Safety of Autonomous Web Agents"**.
    *Ada Defne Tur et al.* ICML 2025. [[Paper](https://openreview.net/forum?id=7TrOBcxSvy)][[Github](https://github.com/McGill-NLP/safearena)]

6.  ST-WebAgentBench: **"ST-WebAgentBench: A Benchmark for Evaluating Safety & Trustworthiness in Web Agents"**.
    *Ido Levy et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2410.06703)][[Github](https://github.com/segev-shlomov/ST-WebAgentBench)]

7.  JAWS-BENCH: **"Breaking the Code: Security Assessment of AI Code Agents Through Systematic Jailbreaking Attacks"**.
    *Shoumik Saha et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2510.01359)]

8.  SandboxEval: **"SandboxEval: Towards Securing Test Environment for Untrusted Code"**.
    *Rafiqul Rabin et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2504.00018)]

9.  InjecAgent: **"InjecAgent: Benchmarking Indirect Prompt Injections in Tool-Integrated Large Language Model Agents"**.
    *Qiusi Zhan et al.* ACL 2024. [[Paper](https://arxiv.org/abs/2403.02691)][[Github](https://github.com/uiuc-kang-lab/InjecAgent)]

10. LLMs are not Aligned Browser Agents: **"Aligned LLMs Are Not Aligned Browser Agents"**.
    *Priyanshu Kumar et al.* ICLR 2025. [[Paper](https://arxiv.org/abs/2405.18561)]

11. MCPTox: **"MCPTox: A Benchmark for Tool Poisoning on Real-World MCP Servers"**.
    *Zhiqiang Wang et al.* AAAI 2026. [[Paper](https://arxiv.org/abs/2510.15994)][[GitHub](https://github.com/dongsenzhang/MSB)]

12. MCP-SafetyBench: **"MCP-SafetyBench: A Benchmark for Safety Evaluation of Large Language Models with Real-World MCP Servers"**.
    *Xuanjun Zong et al.* ICLR 2026. [[Paper](https://openreview.net/forum?id=7XYjeL46co)][[GitHub](https://github.com/xjzzzzzzzz/MCPSafety)]

13. MSB: **"MCP Security Bench (MSB): Benchmarking Attacks Against Model Context Protocol in LLM Agents"**.
    *D. Zhang et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2510.15994)][[GitHub](https://github.com/dongsenzhang/MSB)]

14. WASP: **"WASP: Benchmarking Web Agent Security Against Prompt Injection Attacks"**.
    *Ivan Evtimov et al.* NeurIPS 2026. [[Paper](https://arxiv.org/abs/2506.08136)]

15. PoisonBench: **"PoisonBench: Assessing Large Language Model Vulnerability to Poisoned Preference Data"**.
    *Tingchen Fu et al.* ICML 2025. [[Paper](https://openreview.net/pdf?id=21kAulloDG)][[Github](https://github.com/TingchenFu/PoisonBench)]

16. OS-Harm: **"OS-Harm: A Benchmark for Measuring Safety of Computer Use Agents"**.
    *Thomas Kuntz et al.* NeurIPS 2025. [[Paper](https://arxiv.org/abs/2506.14866)][[GitHub](https://github.com/tml-epfl/os-harm)]

17. MobileSafetyBench: **"MobileSafetyBench: Evaluating Safety of Autonomous Agents in Mobile Device Control"**.
    *Juyong Lee et al.* AAAI 2026. [[Paper](https://arxiv.org/abs/2410.17520)][[GitHub](https://github.com/jylee425/mobilesafetybench)]

18. RedTeamCUA: **"RedTeamCUA: Realistic Adversarial Testing of Computer-Use Agents in Hybrid Web-OS Environments"**.
    *Zeyi Liao et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2505.21936)][[GitHub](https://github.com/OSU-NLP-Group/RedTeamCUA)]

19. HackWorld: **"HackWorld: Evaluating Computer-Use Agents on Exploiting Web Application Vulnerabilities"**.
    *Xiaoxue Ren et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2510.12200)][[GitHub](https://github.com/GUI-Agent/HackWorld)]

20. AgentLeak†: **"AgentLeak: A Benchmark for Internal-Channel Privacy Leakage in Multi-Agent LLM Systems"**.
    *Faouzi El Yagoubi et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2602.11510)][[GitHub](https://github.com/Privatris/AgentLeak)]

##### Execution Environments

1.  CVE-Bench (Web): **"CVE-Bench: A Benchmark for AI Agents' Ability to Exploit Real-World Web Application Vulnerabilities"**.
    *Yuxuan Zhu et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2503.17332)][[Github](https://github.com/uiuc-kang-lab/cve-bench)]

2.  DoomArena: **"DoomArena: A Framework for Testing AI Agents Against Evolving Security Threats"**.
    *Léo Boisvert et al.* CoLM 2025. [[Paper](https://openreview.net/forum?id=GanmYQ0RpE)][[Github](https://github.com/ServiceNow/DoomArena)]

3.  WebArena: **"WebArena: A Realistic Web Environment for Building Autonomous Agents"**.
    *Shuyan Zhou et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2307.13854)][[Github](http://github.com/web-arena-x/webarena)]

4.  HackWorld: **"HackWorld: Evaluating Computer-Use Agents on Exploiting Web Application Vulnerabilities"**.
    *Xiaoxue Ren et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2510.12200)][[GitHub](https://github.com/GUI-Agent/HackWorld)]

5.  AgentDojo: **"AgentDojo: A Dynamic Environment to Evaluate Prompt Injection Attacks and Defenses for LLM Agents"**.
    *Edoardo Debenedetti et al.* NeurIPS 2024. [[Paper](https://arxiv.org/abs/2406.13352)][[Github](https://github.com/ethz-spylab/agentdojo)]

#### Why Alignment Fails in Agentic Settings

1.  ScamAgents: **"ScamAgents: How AI Agents Can Simulate Human-Level Scam Calls"**.
    *Sanket Badhe.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.06457)]

2.  Instruction-Hierarchy: **"The Instruction Hierarchy: Training LLMs to Prioritize Privileged Instructions"**.
    *Eric Wallace et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2404.13208)]

3.  Jailbroken: **"Jailbroken: How Does LLM Safety Training Fail?"**.
    *Alexander Wei et al.* NeurIPS 2023. [[Paper](https://proceedings.neurips.cc/paper_files/paper/2023/hash/fd6613131889a4b656206c50a8bd7790-Abstract-Conference.html)]

4.  Refusal-Direction: **"Refusal in Language Models Is Mediated by a Single Direction"**.
    *Andy Arditi et al.* NeurIPS 2024. [[Paper](https://arxiv.org/abs/2406.11717)][[GitHub](https://github.com/andyrdt/refusal_direction)]

5.  Web Vulnerability: **"Why Are Web AI Agents More Vulnerable Than Standalone LLMs? A Security Analysis"**.
    *Jeffrey Yang Fan Chiang et al.* ICLR Workshop 2025. [[Paper](https://openreview.net/forum?id=4KoMbO2RJ9)]

6.  When-Refusals-Fail: **"When Refusals Fail: Unstable Safety Mechanisms in Long-Context LLM Agents"**.
    *Tsimur Hadeliya et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2512.02445)]

7.  Lost-in-the-Middle: **"Lost in the Middle: How Language Models Use Long Contexts"**.
    *Nelson F. Liu et al.* TACL 2024. [[Paper](https://arxiv.org/abs/2307.03172)][[GitHub](https://github.com/nelson-liu/lost-in-the-middle)]

8.  Shallow-Alignment: **"Safety Alignment Should Be Made More Than Just a Few Tokens Deep"**.
    *Xiangyu Qi et al.* ICLR 2025. [[Paper](https://openreview.net/forum?id=6Mxhg9PtDE)][[GitHub](https://github.com/Unispac/shallow-vs-deep-alignment)]

9.  JAWS-BENCH: **"Breaking the Code: Security Assessment of AI Code Agents Through Systematic Jailbreaking Attacks"**.
    *Shoumik Saha et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2510.01359)]

10. CoT-Hijacking: **"Chain-of-Thought Hijacking"**.
    *Jianli Zhao et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2510.26418)]

### Defenses

#### Defense & Operations

##### Secure-by-Design

1.  ACE: **"ACE: A Security Architecture for LLM-Integrated App Systems"**.
    *Evan Li et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2504.20984)][[Github](https://github.com/escottrose01/ace-llm)]

2.  Resilient-Agents: **"Architecting Resilient LLM Agents: A Guide to Secure Plan-Then-Execute Implementations"**.
    *Ron F. Del Rosario et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2509.08646)]

3.  Task Shield: **"The Task Shield: Enforcing Task Alignment to Defend Against Indirect Prompt Injection in LLM Agents"**.
    *Feiran Jia et al.* ACL 2025. [[Paper](https://aclanthology.org/2025.acl-long.1435/)]

4.  CaMeL†: **"Defeating Prompt Injections by Design"**.
    *Edoardo Debenedetti et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2503.18813)][[Github](https://github.com/google-research/camel-prompt-injection)]

5.  SkillFortify†: **"Formal Analysis and Supply Chain Security for Agentic AI Skills"**.
    *Varun Pratap Bhardwaj.* Zenodo 2026. [[Paper](https://doi.org/10.5281/zenodo.18787663)][[Github](https://github.com/varun369/skillfortify)]

6.  Polymorphic Prompt: **"To Protect the LLM Agent Against the Prompt Injection Attack with Polymorphic Prompt"**.
    *Zhilong Wang et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2506.05739)][[Github](https://github.com/zhilongwang/LLMAgentProtector)]

7.  MetaSecAlign: **"Meta SecAlign: A Secure Foundation LLM Against Prompt Injection Attacks"**.
    *Sizhe Chen et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2507.02735)][[GitHub](https://github.com/facebookresearch/Meta_SecAlign)]

8.  Information-Flow-Control: **"Securing AI Agents with Information-Flow Control"**.
    *Manuel Costa et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2505.23643)][[GitHub](https://github.com/microsoft/fides)]

9.  Instruction-Hierarchy: **"The Instruction Hierarchy: Training LLMs to Prioritize Privileged Instructions"**.
    *Eric Wallace et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2404.13208)]

10. MCPInspect: **"A First Look at the Security Issues in the Model Context Protocol Ecosystem"**.
    *Xiaofan Li and Xing Gao.* DSN 2026. [[Paper](https://arxiv.org/abs/2510.16558)]

11. ShieldAgent: **"ShieldAgent: Shielding Agents via Verifiable Safety Policy Reasoning"**.
    *Zhaorun Chen et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2503.22738)][[Project](https://shieldagent-aiguard.github.io/)]

12. CloakHoneyTrap: **"Cloak, Honey, Trap: Proactive Defenses Against LLM Agents"**.
    *Michael Ayzenshteyn et al.* USENIX Security 2025. [[Paper](https://www.usenix.org/system/files/usenixsecurity25-ayzenshteyn.pdf)][[Github](https://github.com/Daniel-Ayz/CHeaT)]

13. IPIGuard: **"IPIGuard: A Novel Tool Dependency Graph-Based Defense Against Indirect Prompt Injection in LLM Agents"**.
    *Hengyu An et al.* EMNLP 2025. [[Paper](https://aclanthology.org/2025.emnlp-main.53.pdf)][[Github](https://github.com/Greysahy/ipiguard)]

14. CAGE4: **"Large Language Models are Autonomous Cyber Defenders"**.
    *Sebastián R. Castro et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2505.04843)]

15. TRISM†: **"TRISM for Agentic AI: A Review of Trust, Risk, and Security Management in LLM-Based Agentic Multi-Agent Systems"**.
    *Shaina Raza et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2506.04133)]

16. Trustworthy-Agentic†: **"Trustworthy Agentic AI Systems: A Cross-Layer Review of Architectures, Threat Models, and Governance Strategies"**.
    *Ibrahim Adabara et al.* F1000Research 2025. [[Paper](https://f1000research.com/articles/14-905)]

17. ModelGuard: **"ModelGuard: Information-Theoretic Defense Against Model Extraction Attacks"**.
    *Minxue Tang et al.* USENIX Security 2024. [[Paper](https://www.usenix.org/conference/usenixsecurity24/presentation/tang)][[Github](https://github.com/Yoruko-Tang/ModelGuard)]

18. Security-Of-AI-Agents: **"Security of AI Agents"**.
    *Yifeng He et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2406.08689)][[Github](https://github.com/SecurityLab-UCD/ai-agent-security)]

19. Threat-Model: **"Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents"**.
    *Vineeth Sai Narajala and Om Narayan.* arXiv 2025. [[Paper](https://arxiv.org/abs/2504.19956)]

20. CaMeL-Foundations: **"Systems Security Foundations for Agentic Computing"**.
    *Mihai Christodorescu et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2512.01295)]

21. Spotlighting: **"Defending Against Indirect Prompt Injection Attacks With Spotlighting"**.
    *Keegan Hines et al.* CAMLIS 2024. [[Paper](https://arxiv.org/abs/2403.14720)]

22. StruQ: **"StruQ: Defending Against Prompt Injection with Structured Queries"**.
    *Sizhe Chen et al.* USENIX Security 2025. [[Paper](https://arxiv.org/abs/2402.06363)][[Github](https://github.com/Sizhe-Chen/StruQ)]

23. Bounded Agents†: **"Bounded Agents: Delegation Security for Multi-Agent AI Systems"**.
    *Xabier Muruaga.* arXiv 2026. [[Paper](https://arxiv.org/abs/2608.15888)][[Github](https://github.com/xmuruaga/bounded-agents)]

24. AgentDojo: **"AgentDojo: A Dynamic Environment to Evaluate Prompt Injection Attacks and Defenses for LLM Agents"**.
    *Edoardo Debenedetti et al.* NeurIPS 2024. [[Paper](https://arxiv.org/abs/2406.13352)][[Github](https://github.com/ethz-spylab/agentdojo)]

25. Portable-Agent-Memory: **"Portable Agent Memory: A Protocol for Cryptographically-Verified Memory Transfer Across Heterogeneous AI Agents"**.
    *Santhosh Kumar Ravindran.* arXiv 2026. [[Paper](https://arxiv.org/abs/2605.11032)]

26. Threshold-ECDSA: **"An Efficient Multiparty Threshold ECDSA Protocol against Malicious Adversaries for Blockchain-Based LLMs"**.
    *Jingyi Wang et al.* IET Information Security 2024. [[Paper](https://doi.org/10.1049/2024/2252865)]

##### Multi-Agent Security

1.  D-CIPHER: **"D-CIPHER: Dynamic Collaborative Intelligent Multi-Agent System with Planner and Heterogeneous Executors for Offensive Security"**.
    *Meet Udeshi et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2502.10931)][[Github](https://github.com/NYU-LLM-CTF/nyuctf_agents)]

2.  Secure-Multi-LLM: **"Secure Multi-LLM Agentic AI and Agentification for Edge General Intelligence by Zero-Trust: A Survey"**.
    *Yinqiu Liu et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.19870)]

3.  PhishDebate: **"PhishDebate: An LLM-Based Multi-Agent Framework for Phishing Website Detection"**.
    *Wenhao Li et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2506.15656)]

4.  Robustness-Smoothing: **"Enhancing Robustness of LLM-Driven Multi-Agent Systems Through Randomized Smoothing"**.
    *Jinwei Hu et al.* Chinese Journal of Aeronautics 2025. [[Paper](https://www.sciencedirect.com/science/article/pii/S1000936125003851)]

5.  Challenges-Multi-Agent: **"LLM Multi-Agent Systems: Challenges and Open Problems"**.
    *Shanshan Han et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2402.03578)]

6.  Cross-Domain-Challenges†: **"Seven Security Challenges That Must Be Solved in Cross-Domain Multi-Agent LLM Systems"**.
    *Ronny Ko et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2505.23847)]

7.  Secret-Collusion: **"Secret Collusion among AI Agents: Multi-Agent Deception via Steganography"**.
    *Sumeet Ramesh Motwani et al.* NeurIPS 2024. [[Paper](https://arxiv.org/abs/2402.07510)]

8.  Certifiably-Robust-RAG: **"Certifiably Robust RAG against Retrieval Corruption"**.
    *Chong Xiang et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2405.15556)][[Github](https://github.com/inspire-group/RobustRAG)]

9.  Byzantine Coord: **"Byzantine-Robust Decentralized Coordination of LLM Agents"**.
    *Yongrae Jo and Chanik Park.* arXiv 2025. [[Paper](https://arxiv.org/abs/2507.14928)]

10. Prompt Infection: **"Prompt Infection: LLM-to-LLM Prompt Injection Within Multi-Agent Systems"**.
    *Donghyun Lee and Mo Tiwari.* arXiv 2024. [[Paper](https://arxiv.org/abs/2410.07283)]

##### Runtime Protection

1.  R^2-Guard: **"R^2-Guard: Robust Reasoning Enabled LLM Guardrail via Knowledge-Enhanced Logical Reasoning"**.
    *Mintong Kang and Bo Li.* ICLR 2025. [[Paper](https://openreview.net/forum?id=CkgKSqZbuC)][[Github](https://github.com/kangmintong/R-2-Guard)]

2.  Refining-Guardrails: **"Refining Input Guardrails: Enhancing LLM-as-a-Judge Efficiency Through Chain-of-Thought Fine-Tuning and Alignment"**.
    *Melissa Kazemi Rad et al.* AAAI Workshop 2025. [[Paper](https://openreview.net/forum?id=UNPzbCKovl)]

3.  AgentSpec: **"AgentSpec: Customizable Runtime Enforcement for Safe and Reliable LLM Agents"**.
    *Haoyu Wang et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2503.18666)][[Github](https://github.com/haoyuwang99/AgentSpec)]

4.  SentinelAgent: **"SentinelAgent: Graph-Based Anomaly Detection in Multi-Agent Systems"**.
    *Xu He et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2505.24201)]

5.  Confront-Insider†: **"Confront Insider Threat: Precise Anomaly Detection in Behavior Logs Based on LLM Fine-Tuning"**.
    *Shuang Song et al.* COLING 2025. [[Paper](https://aclanthology.org/2025.coling-main.574/)]

6.  GuardAgent: **"GuardAgent: Safeguard LLM Agents by a Guard Agent via Knowledge-Enabled Reasoning"**.
    *Zhen Xiang et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2406.09187)][[Github](https://github.com/guardagent/code)]

7.  AgentGuard: **"AgentGuard: Repurposing Agentic Orchestrator for Safety Evaluation of Tool Orchestration"**.
    *Jizhou Chen and Samuel Lee Cong.* arXiv 2025. [[Paper](https://arxiv.org/abs/2502.09809)]

8.  AGrail: **"AGrail: A Lifelong Agent Guardrail with Effective and Adaptive Safety Detection"**.
    *Weidi Luo et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2502.11448)][[Github](https://github.com/SaFo-Lab/AGrail4Agent)]

9.  PSG-Agent: **"PSG-Agent: Personality-Aware Safety Guardrail for LLM-Based Agents"**.
    *Yaozu Wu et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2509.23614)]

10. WebGuard: **"WebGuard: Building a Generalizable Guardrail for Web Agents"**.
    *Boyuan Zheng et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2507.14293)][[GitHub](https://github.com/OSU-NLP-Group/WebGuard)]

11. ShieldNet: **"ShieldNet: Network-Level Guardrails against Emerging Supply-Chain Injections in Agentic Systems"**.
    *Zhuowen Yuan et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2604.04426)]

12. MCPGuard: **"MCP-Guard: A Multi-Stage Defense-in-Depth Framework for Securing Model Context Protocol in Agentic AI"**.
    *Wenpeng Xing et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.10991)][[Github](https://github.com/GenTelLab/MCP-Guard)]

13. AgentStepper: **"AgentStepper: Interactive Debugging of Software Development Agents"**.
    *Robert Hutter and Michael Pradel.* arXiv 2026. [[Paper](https://arxiv.org/abs/2602.06593)][[GitHub](https://github.com/sola-st/AgentStepper)]

14. AgentSentry: **"AgentSentry: Mitigating Indirect Prompt Injection via Temporal Causal Diagnostics"**.
    *Tian Zhang et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2602.22724)]

15. Bedrock-Security†: **"Securing Amazon Bedrock Agents: Safeguarding Against Indirect Prompt Injections"**.
    *Amazon Web Services.* AWS White Paper 2024. [[Link](https://aws.amazon.com/blogs/machine-learning/securing-amazon-bedrock-agents-a-guide-to-safeguarding-against-indirect-prompt-injections/)]

16. AgentGuard-RV: **"AgentGuard: Runtime Verification of AI Agents"**.
    *Roham Koohestani.* ASE 2025 Workshop (AgenticSE). [[Paper](https://arxiv.org/abs/2509.23864)]

17. Jailbreaker-in-Jail: **"Jailbreaker in Jail: Moving Target Defense for Large Language Models"**.
    *Bocheng Chen et al.* ACM MTD 2023. [[Paper](https://arxiv.org/abs/2310.02417)]

18. DynamicAttention: **"Improving the Robustness of Transformer-based Large Language Models with Dynamic Attention"**.
    *Lujia Shen et al.* NDSS 2024. [[Paper](https://www.ndss-symposium.org/ndss-paper/improving-the-robustness-of-transformer-based-large-language-models-with-dynamic-attention/)]

##### Security Operations

1.  IRIS: **"IRIS: LLM-Assisted Static Analysis for Detecting Security Vulnerabilities"**.
    *Ziyang Li et al.* ICLR 2025. [[Paper](https://openreview.net/forum?id=9LdJDU7E91)][[Github](https://github.com/iris-sast/iris)]

2.  Chain-of-Agents: **"Chain-of-Agents: End-to-End Agent Foundation Models via Multi-Agent Distillation and Agentic RL"**.
    *Weizhen Li et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.13167)][[Github](https://github.com/OPPO-PersonalAI/Agent_Foundation_Models)]

3.  RepoAudit: **"RepoAudit: An Autonomous LLM-Agent for Repository-Level Code Auditing"**.
    *Jinyao Guo et al.* ICML 2025. [[Paper](https://openreview.net/pdf?id=TXcifVbFpG)][[Github](https://github.com/PurCL/RepoAudit)]

4.  Knighter: **"Knighter: Transforming Static Analysis with LLM-Synthesized Checkers"**.
    *Chenyuan Yang et al.* SOSP 2025. [[Paper](https://dl.acm.org/doi/10.1145/3731569.3764827)][[Github](https://github.com/ise-uiuc/KNighter)]

5.  VeriPlan: **"VeriPlan: Integrating Formal Verification and LLMs into End-User Planning"**.
    *Christine P. Lee et al.* CHI 2025. [[Paper](https://dl.acm.org/doi/10.1145/3706598.3714113)]

6.  MCMAS-OP: **"Formal Verification of Open Multi-Agent Systems"**.
    *Panagiotis Kouvaros et al.* AAMAS 2019. [[Paper](https://dl.acm.org/doi/10.5555/3306127.3331691)]

7.  Specifying-Behavior: **"Formally Specifying the High-Level Behavior of LLM-Based Agents"**.
    *Maxwell Crouse et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2310.08535)]

8.  VerifiablySafe: **"Towards Verifiably Safe Tool Use for LLM Agents"**.
    *Aarya Doshi et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2601.08012)]

9.  AIR: **"AIR: Improving Agent Safety through Incident Response"**.
    *Zibo Xiao et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2602.11749)]

10. Policy-Guided-Threat: **"Policy-Guided Threat Hunting: An LLM-enabled Framework with Splunk SOC Triage"**.
    *Rishikesh Sahay et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2603.23966)]

11. Blue-Team-Benchmark: **"Benchmarking LLM-Assisted Blue Teaming via Standardized Threat Hunting"**.
    *Yuqiao Meng et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2509.23571)]

12. CIAF: **"Cloud Investigation Automation Framework (CIAF): An AI-Driven Approach to Cloud Forensics"**.
    *Dalal Alharthi and Ivan Roberto Kawaminami Garcia.* arXiv 2025. [[Paper](https://arxiv.org/abs/2510.00452)]

13. LLM-Cloud-Forensics: **"LLM-Powered Automated Cloud Forensics: From Log Analysis to Investigation"**.
    *Dalal Alharthi and Rozhin Yasaei.* IEEE CLOUD 2025. [[Paper](https://ieeexplore.ieee.org/document/11120597)]

14. CyberSOCEval: **"CyberSOCEval: Benchmarking LLMs Capabilities for Malware Analysis and Threat Intelligence Reasoning"**.
    *Lauren Deason et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2509.20166)][[Data](https://github.com/CrowdStrike/CyberSOCEval_data)][[Github](https://github.com/meta-llama/PurpleLlama)]

15. CyberSleuth: **"CyberSleuth: Autonomous Blue-Team LLM Agent for Web Attack Forensics"**.
    *Stefano Fumero et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.20643)][[Github](https://github.com/SmartData-Polito/LLM_Agent_Cybersecurity_Forensic)]

16. IRCopilot: **"IRCopilot: Automated Incident Response with Large Language Models"**.
    *Xihuan Lin et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2505.20945)][[Code](https://anonymous.4open.science/r/IRCopilot-78A0)]

17. CTI-Vulnerabilities: **"Uncovering Vulnerabilities of LLM-Assisted Cyber Threat Intelligence"**.
    *Yuqiao Meng et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2509.23573)][[Github](https://github.com/mengyuqiao/LLM-CTI)]

18. ProvSEEK: **"LLM-Driven Provenance Forensics for Threat Investigation and Detection"**.
    *Kunal Mukherjee and Murat Kantarcioglu.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.21323)][[Github](https://anonymous.4open.science/r/provseek-anonymous-DDDD)]

19. LLMCloudHunter: **"LLMCloudHunter: Harnessing LLMs for Automated Extraction of Detection Rules from Cloud-Based CTI"**.
    *Yuval Schwartz et al.* WWW 2025. [[Paper](https://dl.acm.org/doi/10.1145/3696410.3714798)][[Github](https://github.com/YuvalSchwartz/llm-cloud-hunter)]

20. LLM-in-the-SOC-Empirical-Study: **"LLMs in the SOC: An Empirical Study of Human-AI Collaboration in Security Operations Centres"**.
    *Ronal Singh et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.18947)][[Github](https://github.com/eSentire-Labs/LLM-Gateway)]

21. RAG-Incident-Response: **"Advancing Autonomous Incident Response: Leveraging LLMs and Cyber Threat Intelligence"**.
    *Amine Tellache et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.10677)]

22. GALA: **"GALA: Can Graph-Augmented Large Language Model Agentic Workflows Elevate Root Cause Analysis?"**.
    *Yifang Tian et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.12472)]

23. CORTEX: **"Cortex: Collaborative LLM Agents for High-Stakes Alert Triage"**.
    *Bowen Wei et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2510.00311)]

24. ExCyTInBench: **"Excytin-bench: Evaluating LLM Agents on Cyber Threat Investigation"**.
    *Yiran Wu et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2507.14201)][[Github](https://github.com/kaebvcidn/Excytin-Bench)]

#### Evaluation

##### Benchmarking Platforms

1.  AgentDojo: **"AgentDojo: A Dynamic Environment to Evaluate Prompt Injection Attacks and Defenses for LLM Agents"**.
    *Edoardo Debenedetti et al.* NeurIPS 2024. [[Paper](https://arxiv.org/abs/2406.13352)][[Github](https://github.com/ethz-spylab/agentdojo)]

2.  SafeArena: **"SafeArena: Evaluating the Safety of Autonomous Web Agents"**.
    *Ada Defne Tur et al.* ICML 2025. [[Paper](https://openreview.net/forum?id=7TrOBcxSvy)][[Github](https://github.com/McGill-NLP/safearena)]

3.  RAS-Eval: **"RAS-Eval: A Comprehensive Benchmark for Security Evaluation of LLM Agents in Real-World Environments"**.
    *Yuchuan Fu et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2506.15253)][[Github](https://github.com/lanzer-tree/RAS-Eval)]

4.  ASB: **"Agent Security Bench (ASB): Formalizing and Benchmarking Attacks and Defenses in LLM-Based Agents"**.
    *Hanrong Zhang et al.* ICLR 2025. [[Paper](https://openreview.net/forum?id=V4y0CpX4hK)][[Github](https://github.com/agiresearch/ASB)]

5.  AgentHarm: **"AgentHarm: A Benchmark for Measuring Harmfulness of LLM Agents"**.
    *Maksym Andriushchenko et al.* ICLR 2025. [[Paper](https://arxiv.org/abs/2410.09024)][[Hugging Face](https://huggingface.co/datasets/ai-safety-institute/AgentHarm)]

6.  Cybench: **"Cybench: A Framework for Evaluating Cybersecurity Capabilities and Risks of Language Models"**.
    *Andy K Zhang et al.* ICLR 2025. [[Paper](https://openreview.net/forum?id=tc90LV0yRL)][[Github](https://github.com/andyzorigin/cybench)]

7.  ZeroDayBench: **"ZeroDayBench: Evaluating LLM Agents on Unseen Zero-Day Vulnerabilities for Cyberdefense"**.
    *Nancy Lau et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2603.02297)]

8.  R-Judge: **"R-Judge: Benchmarking Safety Risk Awareness for LLM Agents"**.
    *Tongxin Yuan et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2401.10019)][[GitHub](https://github.com/Lordog/R-Judge)]

9.  ToolFuzz: **"ToolFuzz - Automated Agent Tool Testing"**.
    *Ivan Milev et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2503.04479)]

10. CyberSecEval2: **"CyberSecEval 2: A Wide-Ranging Cybersecurity Risk Assessment for LLMs"**.
    *Manish Bhatt et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2404.13161)]

11. aiXamine†: **"aiXamine: Simplified LLM Safety and Security"**.
    *Fatih Deniz et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2504.14985)]

12. TurkingBench: **"TurkingBench: A Challenge Benchmark for Web Agents"**.
    *Kevin Xu et al.* NAACL 2025. [[Paper](https://aclanthology.org/2025.naacl-long.188/)][[Github](https://github.com/JHU-CLSP/turking-bench)]

13. τ-Bench: **"τ-Bench: A Benchmark for Tool-Agent-User Interaction in Real-World Domains"**.
    *Shunyu Yao et al.* 2024. [[Paper](https://arxiv.org/abs/2406.12045)][[Github](https://github.com/sierra-research/tau-bench)]

14. WebArena: **"WebArena: A Realistic Web Environment for Building Autonomous Agents"**.
    *Shuyan Zhou et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2307.13854)][[Github](http://github.com/web-arena-x/webarena)]

15. MasterKey: **"MASTERKEY: Automated Jailbreaking of Large Language Model Chatbots"**.
    *Gelei Deng et al.* NDSS 2024. [[Paper](https://www.ndss-symposium.org/wp-content/uploads/2024-188-paper.pdf)]

16. EchoLeak: **"EchoLeak: The First Real-World Zero-Click Prompt Injection Exploit in a Production LLM System"**.
    *Pavan Reddy and Aditya Sanjay Gujral.* arXiv 2025. [[Paper](https://arxiv.org/abs/2509.10540)]

17. Sleeper-Agents: **"Sleeper Agents: Training Deceptive LLMs that Persist Through Safety Training"**.
    *Evan Hubinger et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2401.05566)]

18. Ziran†: **"Ziran: Open-Source Security Testing Framework for AI Agents"**.
    *Leone Perdigão.* 2025. [[Blog](https://leoneperdigao.medium.com/your-ai-agent-has-a-backdoor-heres-how-i-found-it-1ad50124cacf)][[Github](https://github.com/taoq-ai/ziran)]

19. CVE-Bench (Web): **"CVE-Bench: A Benchmark for AI Agents' Ability to Exploit Real-World Web Application Vulnerabilities"**.
    *Yuxuan Zhu et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2503.17332)][[Github](https://github.com/uiuc-kang-lab/cve-bench)]

20. AgentFuzz: **"Make Agent Defeat Agent: Automatic Detection of Taint-Style Vulnerabilities in LLM-Based Agents"**.
    *Fengyu Liu et al.* USENIX Security 2025. [[Paper](https://www.usenix.org/conference/usenixsecurity25/presentation/liu-fengyu)][[Code](https://zenodo.org/records/15590097)]

21. Commercial-Agent-Vulnerability: **"Commercial LLM Agents Are Already Vulnerable to Simple Yet Dangerous Attacks"**.
    *Ang Li et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2502.08586)]

22. Taming-OpenClaw: **"Taming OpenClaw: Security Analysis and Mitigation of Autonomous LLM Agent Threats"**.
    *Xinhao Deng et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2603.11619)]

23. AgentVigil: **"AgentVigil: Generic Black-Box Red-Teaming for Indirect Prompt Injection Against LLM Agents"**.
    *Zhun Wang et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2505.05849)]

24. InjecAgent: **"InjecAgent: Benchmarking Indirect Prompt Injections in Tool-Integrated Large Language Model Agents"**.
    *Qiusi Zhan et al.* ACL 2024. [[Paper](https://arxiv.org/abs/2403.02691)][[Github](https://github.com/uiuc-kang-lab/InjecAgent)]

25. Privacy Risks: **"Searching for Privacy Risks in LLM Agents via Simulation"**.
    *Yanzhe Zhang and Diyi Yang.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.10880)][[Github](https://github.com/SALT-NLP/search_privacy_risk)]

##### Defense Testing

1.  Adaptive Attacks: **"Adaptive Attacks Break Defenses Against Indirect Prompt Injection Attacks on LLM Agents"**.
    *Qiusi Zhan et al.* NAACL 2025. [[Paper](https://aclanthology.org/2025.findings-naacl.395/)][[Github](https://github.com/uiuc-kang-lab/AdaptiveAttackAgent)]

2.  Open-Challenges: **"Open Challenges in Multi-Agent Security: Towards Secure Systems of Interacting AI Agents"**.
    *Christian Schroeder de Witt.* arXiv 2025. [[Paper](https://arxiv.org/abs/2505.02077)]

3.  Trustworthy-Survey: **"A Survey on Trustworthy LLM Agents: Threats and Countermeasures"**.
    *Miao Yu et al.* KDD 2025. [[Paper](https://dl.acm.org/doi/10.1145/3711896.3736561)]

4.  Risk-Navigating: **"Navigating the Risks: A Survey of Security, Privacy, and Ethics Threats in LLM-Based Agents"**.
    *Yuyou Gan et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2411.09523)]

5.  Safety-At-Scale: **"Safety at Scale: A Comprehensive Survey of Large Model and Agent Safety"**.
    *Xingjun Ma et al.* Foundations and Trends in Privacy and Security 2025. [[Paper](https://www.nowpublishers.com/article/Details/SEC-051)]

6.  Full-Stack-Safety: **"A Comprehensive Survey in LLM(-Agent) Full Stack Safety: Data, Training and Deployment"**.
    *Kun Wang et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2504.15585)]

7.  Agents-Under-Threat: **"AI Agents Under Threat: A Survey of Key Security Challenges and Future Pathways"**.
    *Zehang Deng et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2406.02630)]

8.  AI-Agent-Index: **"The 2025 AI Agent Index: Documenting Technical and Safety Features of Deployed Agentic AI Systems"**.
    *Leon Staufer et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2602.17753)]

9.  xTeaming: **"X-Teaming: Multi-Turn Jailbreaks and Defenses with Adaptive Multi-Agents"**.
    *Salman Rahman et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2504.13203)]

10. Trustworthy-Distributed: **"Trustworthy Distributed AI Systems: Robustness, Privacy, and Governance"**.
    *Wenqi Wei and Ling Liu.* arXiv 2024. [[Paper](https://arxiv.org/abs/2402.01096)]

11. Defend-via-Hacking: **"To Defend Against Cyber Attacks, We Must Teach AI Agents to Hack"**.
    *Terry Yue Zhuo et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2602.02595)]

12. MCPGuard: **"MCP-Guard: A Multi-Stage Defense-in-Depth Framework for Securing Model Context Protocol in Agentic AI"**.
    *Wenpeng Xing et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2508.10991)][[Github](https://github.com/GenTelLab/MCP-Guard)]

13. ShieldNet: **"ShieldNet: Network-Level Guardrails against Emerging Supply-Chain Injections in Agentic Systems"**.
    *Zhuowen Yuan et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2604.04426)]

##### Domain-Specific Frameworks

1.  Agentic-AI-Healthcare: **"Agentic-AI Healthcare: Multilingual, Privacy-First Framework with MCP Agents"**.
    *Mohammad A. Shehab.* arXiv 2025. [[Paper](https://arxiv.org/abs/2510.02325)]

2.  PrivacyChecker: **"Privacy in Action: Towards Realistic Privacy Mitigation and Evaluation for LLM-Powered Agents"**.
    *Shouju Wang et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2509.17488)][[Github](https://github.com/microsoft/ACV/tree/main/misc/PrivacyInAction)]

3.  Privacy-Aware-RAG: **"Privacy-Aware RAG: Secure and Isolated Knowledge Retrieval"**.
    *Pengcheng Zhou et al.* arXiv 2025. [[Paper](https://arxiv.org/abs/2503.15548)]

4.  LLM-Privacy-GuardRails: **"Deploying Privacy Guardrails for LLMs: A Comparative Analysis of Real-World Applications"**.
    *Shubhi Asthana et al.* 2025. [[Paper](https://arxiv.org/abs/2501.12456)]

5.  AuditGPT: **"AuditGPT: Auditing Smart Contracts with ChatGPT"**.
    *Shihao Xia et al.* 2024. [[Paper](http://arxiv.org/abs/2404.04306)][[Github](https://github.com/pratraut/auditgpt)]

6.  BARTPredict: **"BARTPredict: Empowering IoT Security with LLM-Driven Cyber Threat Prediction"**.
    *Alaeddine Diaf et al.* 2025. [[Paper](https://ieeexplore.ieee.org/document/10901770)]

7.  FineTuning-Auditing: **"Combining Fine-Tuning and LLM-Based Agents for Intuitive Smart Contract Auditing with Justifications"**.
    *Wei Ma et al.* 2024. [[Paper](https://dl.acm.org/doi/10.1109/ICSE55347.2025.00027)]

8.  Browsing-Dangers: **"The Hidden Dangers of Browsing AI Agents"**.
    *Mykyta Mudryi et al.* 2025. [[Paper](https://arxiv.org/abs/2505.13076)][[GIthub](https://github.com/arimlabs/agent-hijacking-poc)]

9.  Cloud-Infrastructure-AI-Agent: **"Cloud Infrastructure Management in the Age of AI Agents"**.
    *Zhenning Yang et al.* ACM SIGOPS Operating Systems Review 2025. [[Paper](https://dl.acm.org/doi/10.1145/3759441.3759443)]

10. OS-Agents-Survey: **"OS Agents: A Survey on MLLM-based Agents for Computer, Phone and Browser Use"**.
    *Xueyu Hu et al.* 2025. [[Paper](https://aclanthology.org/2025.acl-long.369/)][[Github](https://github.com/OS-Agent-Survey/OS-Agent-Survey)]

11. Autonomous-Driving-Perception: **"Enhancing LLM-based Autonomous Driving Agents to Mitigate Perception Attacks"**.
    *Ruoyu Muller et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2409.14488)]

12. Privacy-Preserving-Medical-Imaging: **"Privacy-Preserving AI for Encrypted Medical Imaging: A Framework for Secure Diagnosis and Learning"**.
    *Abdullah Al Siam and Sadequzzaman Shohan.* arXiv 2025. [[Paper](https://arxiv.org/abs/2507.21060)]

13. LISA: **"LISA Technical Report: An Agentic Framework for Smart Contract Auditing"**.
    *Izaiah Sun et al.* 2025. [[Paper](https://arxiv.org/abs/2509.24698)][[Github](https://github.com/agentlisa)]

14. Skill-Ecosystem-Poisoning: **"Supply-Chain Poisoning Attacks Against LLM Coding Agent Skill Ecosystems"**.
    *Yubin Qu et al.* arXiv 2026. [[Paper](https://arxiv.org/abs/2604.03081)]

15. LLM-SmartAudit (arXiv): **"LLM-SmartAudit: Advanced Smart Contract Vulnerability Detection"**.
    *Zhiyuan Wei et al.* arXiv 2024. [[Paper](https://arxiv.org/abs/2410.09381)]

16. Embodied-AI-Security: **"Towards Robust and Secure Embodied AI: A Survey on Vulnerabilities and Attacks"**.
    *Wenpeng Xing et al.* 2025. [[Paper](https://arxiv.org/abs/2502.13175)]

---

## Analysis

> This section summarizes the analysis published in the TMLR version of the survey. It is a fixed snapshot of the 274 papers coded for that version. The paper list above keeps growing, but entries marked **†** are not included in these numbers and figures.

### Corpus Overview

<div align="center">
    <img src="./assets/corpus_composition_venn.png" width="45%"/>
</div>

A paper can be coded under more than one pillar (e.g., one that introduces both an attack and a defense for it). Applications account for 113 papers, Threats for 86, and Defenses for 123, giving a deduplicated total of 274 papers. Pillar-level percentages below use that pillar's count as the denominator, and cross-cutting percentages use all 274 papers, unless a smaller analysis set is stated.

---

### Applications Analysis

**Red-Teaming and Blue-Teaming Agent Pipelines**

<div align="center">
    <img src="./assets/red-teaming-pipeline.png" width="90%"/>
</div>

A red-teaming pipeline pairs a reconnaissance agent that enumerates the attack surface with a planner that builds an attack graph and decomposes objectives. Specialist agents handle vulnerability discovery, fuzzing, and exploit generation, an executor carries out actions, and a feedback collector validates outcomes. Shared memory/RAG (exploit DBs, task trees) sustains long-horizon state across attack stages.

<div align="center">
    <img src="./assets/blue-teaming-pipeline.png" width="90%"/>
</div>

A blue-teaming pipeline moves telemetry, alerts, and threat intelligence through data collection, detection, and threat-hunting agents. A triage agent prioritizes incidents and filters false positives, and forensics/RCA and remediation agents investigate causes and recommend mitigations. Human analysts approve high-impact response actions.

**Security-Lifecycle Coverage Map**

<div align="center">
    <img src="./assets/fig_lifecycle_lifelines.png" width="80%"/>
</div>

Research clusters in stages that give immediate, verifiable feedback. On offense, vulnerability discovery is the most covered stage (52 papers), followed closely by exploitation (50), reconnaissance (35), and scanning (22). Coverage drops sharply after exploitation: post-exploitation has 13 papers, exfiltration 3, and persistence only 2. On defense, detection leads (27), followed by remediation (19) and forensics (17), while threat hunting (11), root-cause analysis (10), alert triage (9), and response (6) remain thin. Stages that require sustained reasoning, stealth, or long-term operational awareness receive little attention.

**Offense-Defense Autonomy Asymmetry**

<div align="center">
    <img src="./assets/fig_autonomy_offensive.png" width="32%"/>
    <img src="./assets/fig_autonomy_defensive.png" width="32%"/>
    <img src="./assets/fig_human_oversight_execution.png" width="32%"/>
</div>

Of 47 offensive systems, 39 (83.0%) operate at Level 3 (fully autonomous) and none at Level 0. Of 35 defensive systems, only 5 (14.3%) reach Level 3, while 42.9% operate at Level 1 (copilot), 28.6% at Level 2, and 14.3% at Level 0. As a result, 85.7% of defensive systems keep a human approval gate, against 17.0% of offensive systems. Offense optimizes for end-to-end task completion; defense prioritizes explainability, safety, and accountability, so developers deliberately restrict autonomy.

**Dual-Use Red-Teaming**

<div align="center">
    <img src="./assets/fig_A_cost_comparison.png" width="32%"/>
    <img src="./assets/fig_B_agent_effectiveness.png" width="32%"/>
    <img src="./assets/fig_C_cost_reduction.png" width="32%"/>
</div>

60 of the 113 application systems (53.1%) expose capabilities that are directly offensive or broadly dual-use. Agents reduce exploitation cost by 2.8×–8.9× relative to human baselines. A single agent exploits 87% of one-day CVEs at ~$8.80 per exploit, CVE-Genie reproduces 51% of 841 CVEs at $2.77 each, HPTSA exploits zero-days at ~$24.4 versus ~$75 for human experts, and ARTEMIS runs at ~$18/hr versus $60/hr for human penetration testers. Three shifts emerge: reduced cost, higher scalability through parallel multi-agent execution, and a lower skill floor. This capability comes from the agentic scaffold rather than the base model: HPTSA loses 13× in pass@1 without its hierarchical coordination, and base models often refuse offensive tasks that they complete once embedded in an agent.

---

### Threats Analysis

**Entry Points of the Attack Surface**

<div align="center">
    <img src="./assets/fig1_threat_entrypoint_heatmap.png" width="80%"/>
</div>

Of the 86 threat papers, 74 describe a channel-specific attack mechanism. The conversational input (user query + system prompt) is the most attacked entry point, accounting for 56.8% of evaluated attacks, largely because it is the easiest channel to study and also exists in stateless chatbots. Among agent-specific surfaces, the tool/API response leads (24 papers) and is growing alongside the Model Context Protocol, followed by environment observations (20) and retrieved documents/RAG (17). Inter-agent communication (5 papers) and persistent memory remain thin, and no paper in the corpus attacks the reflection output.

**Agent Loop Failure Stages and Threat Specificity**

<div align="center">
    <img src="./assets/fig4_agent_loop_stage_diagram.png" width="49%"/>
    <img src="./assets/fig5_threat_specificity_stacked.png" width="45%"/>
</div>

Of 78 papers whose failure stage can be located, reasoning is the most targeted stage (54 papers), followed by action selection (41). Execution (9), planning (7), perception (6), observation (5), and retrieval (5) receive far less attention, and reflection none. Half of the attacks (50.5%) are agent-native, 41.4% are inherited from the base LLM or amplified by the agentic scaffold, and 8.1% are unclassifiable. Jailbreaks are overwhelmingly inherited or amplified (20 of 25 labels), while injections are mostly agent-native (23 of 36). Safety alignment does not transfer to agents: non-denial rates jump from 0% for a standalone model to 46.6% as a web agent, and GPT-4o's harmful-behavior rate rises from 12% in chat to 74% as a browser agent. Agent-native threats operate through five mechanisms: persistent-state poisoning, inter-agent compromise, tool/protocol-layer poisoning, plan and action hijacking, and specification/reward gaming.

**Threat Models and Attack Objectives**

Of the 77 threat papers that state attacker access, 51.9% assume black-box access and 27.3% need no model access at all; only 20.8% study white-box or gray-box settings. Few require capabilities beyond model access (20.9% training/gradient access, 5.8% tool execution, 3.5% an inter-agent channel, 2.3% memory writes). The most common objectives are inducing unauthorized actions (65.8%), data exfiltration (46.8%), and content-policy violation (38.0%). The dominant threat model is an unprivileged external attacker operating black-box through channels the agent already reads.

**Benchmarks, Metrics and Evaluation Gaps**

25 of the 86 threat papers (29.1%) are benchmarks. 124 distinct benchmarks or datasets appear across the literature, and 75% of them are used by exactly one paper. Of the 31 reused ones, only four are built for agentic security: AgentDojo, InjecAgent, AgentHarm, and BrowserART. Tool responses (14 benchmark papers) and user queries (9) are heavily instrumented, while persistent memory (1), inter-agent messaging (0), and reflection output (0) are largely unevaluated. 76.7% of papers report attack success rate as their headline metric, yet only 19 report utility under attack and 14 report attack cost. ASR definitions also vary: AgentPoison reports 81.2% retrieval ASR but 62.6% end-to-end ASR for the same attack. The main evaluation gaps are single-turn-only evaluation, lack of multi-agent coverage, and simulated rather than real tool execution.

---

### Defenses Analysis

**Defense Strategies**

<div align="center">
    <img src="./assets/Defense_Taxonomy_Analysis.png" width="90%"/>
</div>

Of the 123 defense papers, 92 propose or evaluate at least one defense technique. Ten strategies emerge under a non-exclusive taxonomy. LLM-based monitoring is the largest (53.3%), followed by capability-scoped execution (32.6%), input sanitization and filtering (31.5%), sandboxing and formal verification (27.2%), red-team simulation (21.7%), structured queries (19.6%), cryptographic verification (18.5%), and consensus/vaccine seeding (14.1%). Dataset sanitation and differential privacy (6.5%) and moving target defense (5.4%) are the least explored. No single strategy achieves uniformly low severity across scalability, adversarial robustness, latency/overhead, and coverage, which motivates hybrid, multi-layer defense architectures.

**Structural Compositions**

<div align="center">
    <img src="./assets/Defense_Architecture_Analysis.png" width="90%"/>
</div>

Defenses fall into six structural compositions based on their primary trust boundary: Base LLM Alignment, External Monitor, Formal Verification, Sandbox/Isolation, Cryptographic/Structural Integrity, and Human-in-the-Loop. External Monitors lead in most attack classes, peaking at agent manipulation (19), injection (14), and poisoning and extraction (14). Base LLM Alignment concentrates on poisoning and extraction (8), injection (7), and jailbreak (7), but it trusts the very component under attack.

**Cost-Security Trade-offs and Defense Placement**

<div align="center">
    <img src="./assets/Cost_vs_Security_Trade_offs.png" width="64%"/>
    <img src="./assets/Proactive_vs_Reactive_Intervention.png" width="27%"/>
</div>

Only 18 papers (19.6%) report cost comprehensively, covering security, utility, tokens, and latency. Another 25.0% focus on security and utility, 16.3% on security and compute, and the largest group (39.1%) treats cost only qualitatively or theoretically. Stronger protection consistently costs latency and tokens: IPIGuard brings ASR below 1% at ~14.6K tokens and 13.9 s per task, GuardAgent uses ~6.1K tokens per task, while lightweight filters such as PPA run at ~0.06 ms, so cheap filters should screen requests before expensive LLM-based reasoning. Placement is heavily skewed: 78.3% of defenses intervene before computation and only 21.7% after it, leaving post-computation monitoring underexplored as a primary defense.

---

### Cross-Cutting Trends

**Defense Coverage Across Attack Categories**

<div align="center">
    <img src="./assets/attack_defense_heatmap.png" width="80%"/>
</div>

Each of the 81 defense papers with a primary attack category is mapped to that category and its primary defense mechanism; cell values measure defensive attention, not effectiveness. Injection attacks receive the most attention (30 papers, most often countered with structured queries), followed by agent manipulation (18, most often LLM-based monitoring) and poisoning and extraction (15). Jailbreak (9), red-teaming (5), pre-execution (3), and prompt infection (1) attacks are the least covered.

**Agent Cardinality & Autonomy**

<div align="center">
    <img src="./assets/Agent_Cardinality_Analysis.png" width="36%"/>
    <img src="./assets/Autonomy_Level_Distribution.png" width="56%"/>
</div>

Single-agent systems dominate the corpus (196 papers, 71.5%), followed by multi-agent (58, 21.2%) and hybrid frameworks (20, 7.3%). Of the 221 papers that present a system of their own, Level 3 autonomy dominates (148, 67.0%), followed by Level 2 (15.4%), Level 1 (11.8%), and Level 0 (5.9%).

**Architectural Paradigms & Roles**

<div align="center">
    <img src="./assets/architecture_distribution.png" width="36%"/>
    <img src="./assets/Role_Distribution.png" width="56%"/>
</div>

Of the 257 papers with an identifiable paradigm, monolithic designs lead (40.1%), followed by planner-executor (32.3%), hybrid (21.0%), LLM-as-a-Judge (3.9%), debate-centric (1.9%), and teacher-student (0.8%). Papers average 3.06 cognitive roles, so modern pipelines are inherently multi-functional: executors appear in 88.7% of papers, tool-callers in 73.5%, planners in 66.5%, critics in 51.3%, and governors in 25.7%.

**LLM Usage & Knowledge Sources**

<div align="center">
    <img src="./assets/LLM_Usage_Distributions.png" width="80%"/>
    <img src="./assets/LLM_Knowledge_Sources.png" width="80%"/>
</div>

GPT variants appear in 86.5% of papers, a near-universal baseline that raises reproducibility and generalization concerns. LLaMA (50.0%), Claude (43.8%), Gemini (33.2%), Qwen (28.5%), DeepSeek (23.4%), and Mistral/Mixtral (17.5%) follow. Pre-trained knowledge underlies 96.7% of papers and in-context learning 76.3%, while fine-tuning (25.2%), RAG (24.5%), and preference learning (12.0%) are far less common.

**Data Modalities**

<div align="center">
    <img src="./assets/Data_Modalities.png" width="80%"/>
</div>

Across 272 papers, text dominates (98.2%), followed by code (58.1%), logs (26.8%), images (15.8%), network traces (9.6%), and binaries (5.5%). Every code paper also uses text, and every binaries paper also uses code. The prominence of Text + Code reflects a focus on static source auditing, leaving active network and binary runtime security a significant coverage gap.

---

## Contributors

<a href="https://github.com/kagnlp/Awesome-Agentic-Security/graphs/contributors">
    <img src="https://contrib.rocks/image?repo=kagnlp/Awesome-Agentic-Security" />
</a>

If you find this survey or repository useful, please cite our work:

```bibtex
@article{shahriar2026agentic,
  title={A Survey on Agentic Security: Applications, Threats and Defenses},
  author={Shahriar, Asif and Rahman, Md Nafiu and Ahmed, Sadif and Sadeque, Farig and Parvez, Md Rizwan},
  journal={Transactions on Machine Learning Research},
  issn={2835-8856},
  year={2026},
  url={https://openreview.net/forum?id=Od4ZnAUv9T}
}
```
