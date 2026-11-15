# AI Security Resources

A curated, practice-first collection of resources for learning **AI security**: attacking and defending LLM applications, AI agents, MCP servers and classic machine-learning systems.

**Last reviewed: November 2026.** Every link was checked before it was added. Repository stars and activity dates come from the GitHub API at review time.

> **New here?** Start with the [Learning Path](docs/learning-path.md). It is an ordered roadmap from web security basics to AI agent red teaming, with hands-on labs at every stage.

## Contents

- [Why this list](#why-this-list)
- [Start Here](#start-here)
- [Frameworks and Standards](#frameworks-and-standards)
- [Hands-on Labs, CTFs and Playgrounds](#hands-on-labs-ctfs-and-playgrounds)
  - [PortSwigger Web Security Academy](#portswigger-web-security-academy)
  - [Online challenges](#online-challenges)
  - [Self-hosted vulnerable apps](#self-hosted-vulnerable-apps)
- [Courses and Training Paths](#courses-and-training-paths)
- [Attack Techniques](#attack-techniques)
- [Agent and MCP Security](#agent-and-mcp-security)
- [Defenses and Secure Design](#defenses-and-secure-design)
- [Red Teaming and Scanning Tools](#red-teaming-and-scanning-tools)
- [Model Supply Chain Security](#model-supply-chain-security)
- [Benchmarks and Datasets](#benchmarks-and-datasets)
- [AI for Offensive Security](#ai-for-offensive-security)
- [Blogs, Newsletters and Research Feeds](#blogs-newsletters-and-research-feeds)
- [Conferences and Communities](#conferences-and-communities)
- [Other Curated Lists](#other-curated-lists)
- [Papers](docs/papers.md) · [Books](docs/books.md) · [Glossary](docs/glossary.md)

## Why this list

There are already many AI security "awesome lists". This one tries to do three things differently:

1. **It puts learning order first.** Resources are grouped into a path that builds skills, not only into a catalogue.
2. **It treats web security as the foundation.** Most real-world AI application bugs are ordinary vulnerabilities (XSS, SSRF, broken access control, injection) that an LLM can reach. That is why PortSwigger's Web Security Academy has a central place here.
3. **It tracks what is current.** In 2026 the focus has moved from chatbot jailbreaks to **agents**: tool use, MCP, coding agents and autonomous scanners. Archived or abandoned projects are labelled as such.

## Start Here

If you only do five things:

1. Read the [OWASP Top 10 for LLM Applications](https://genai.owasp.org/llm-top-10/) and the [OWASP Top 10 for Agentic Applications 2026](https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/).
2. Solve every lab in [PortSwigger: Web LLM attacks](https://portswigger.net/web-security/llm-attacks) and [AI-powered scanner vulnerabilities](https://portswigger.net/web-security/llm-attacks/ai-powered-scanner-vulnerabilities).
3. Beat all levels of [Gandalf](https://gandalf.lakera.ai) to build intuition for prompt injection.
4. Read Simon Willison's [The lethal trifecta for AI agents](https://simonwillison.net/2025/Jun/16/the-lethal-trifecta/) and the [Design Patterns for Securing LLM Agents against Prompt Injections](https://arxiv.org/abs/2506.08837) paper.
5. Run [garak](https://github.com/NVIDIA/garak) or [promptfoo](https://github.com/promptfoo/promptfoo) against a local model and read the report.

## Frameworks and Standards

| Resource | What it is |
|---|---|
| [OWASP Top 10 for LLM Applications](https://genai.owasp.org/llm-top-10/) | The standard taxonomy of LLM application risks: prompt injection, sensitive information disclosure, excessive agency and more. |
| [OWASP Top 10 for Agentic Applications 2026](https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/) | Released December 2025. Ten risks for autonomous agents (ASI01–ASI10): goal hijack, tool misuse, identity abuse, memory poisoning, rogue agents and more. |
| [OWASP GenAI Security Project initiatives](https://genai.owasp.org/initiatives/) | Hub for the OWASP GenAI work, including the [GenAI Red Teaming Guide](https://genai.owasp.org/resource/genai-red-teaming-guide/) and the [Agent Control Standard](https://genai.owasp.org/resource/agent-control-standard-acs/). |
| [OWASP AI Testing Guide](https://github.com/OWASP/www-project-ai-testing-guide) | A methodology for testing AI systems, in the style of the OWASP Web Security Testing Guide. |
| [OWASP AISVS](https://github.com/OWASP/AISVS) | AI Security Verification Standard: requirements you can test against, in the style of ASVS. |
| [OWASP AI Exchange](https://owaspai.org) | A large, open knowledge base of AI threats and controls. It feeds into ISO and EU AI Act standards work. |
| [OWASP Machine Learning Security Top 10](https://github.com/OWASP/www-project-machine-learning-security-top-10) | Risks for classic ML systems: input manipulation, data poisoning, model theft and more. |
| [MITRE ATLAS](https://atlas.mitre.org) | An ATT&CK-style matrix of adversary tactics and techniques against AI systems, with real case studies. The data is available in [mitre-atlas/atlas-data](https://github.com/mitre-atlas/atlas-data). |
| [NIST AI 100-2 E2025: Adversarial Machine Learning](https://csrc.nist.gov/pubs/ai/100/2/e2025/final) | NIST's taxonomy and terminology for attacks and mitigations, covering both predictive and generative AI. |
| [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) | A governance framework for managing AI risk, plus a Generative AI profile. |
| [Google Secure AI Framework (SAIF)](https://saif.google) | Google's conceptual framework and risk map for securing AI systems. |
| [MCP Security Best Practices](https://modelcontextprotocol.io/specification/draft/basic/security_best_practices) | The official guidance from the Model Context Protocol spec: confused deputy, token passthrough, session hijacking and more. |

## Hands-on Labs, CTFs and Playgrounds

### PortSwigger Web Security Academy

Free, high quality and browser-based. The LLM labs use a **live LLM**, so you may need to rephrase prompts or retry.

**Topic pages:**
- [Web LLM attacks](https://portswigger.net/web-security/llm-attacks): how LLM APIs work, mapping the attack surface, chaining vulnerabilities, insecure output handling, indirect prompt injection, training data leakage and defenses.
- [AI-powered scanner vulnerabilities](https://portswigger.net/web-security/llm-attacks/ai-powered-scanner-vulnerabilities): this newer topic attacks the *AI agent itself*. It covers indirect prompt injection into AI-powered scanners, data exfiltration through them, and abusing routing-based SSRF to bypass restrictions.

**Labs, in suggested order:**

| # | Lab | Skill |
|---|---|---|
| 1 | [Exploiting LLM APIs with excessive agency](https://portswigger.net/web-security/llm-attacks/lab-exploiting-llm-apis-with-excessive-agency) | Mapping which APIs the LLM can call, and abusing them |
| 2 | [Exploiting vulnerabilities in LLM APIs](https://portswigger.net/web-security/llm-attacks/lab-exploiting-vulnerabilities-in-llm-apis) | Using the LLM as a proxy to reach a classic vulnerability (command injection) |
| 3 | [Indirect prompt injection](https://portswigger.net/web-security/llm-attacks/lab-indirect-prompt-injection) | Planting instructions in third-party content the LLM reads |
| 4 | [Exploiting insecure output handling in LLMs](https://portswigger.net/web-security/llm-attacks/lab-exploiting-insecure-output-handling-in-llms) | Indirect prompt injection that ends in XSS |
| 5 | [Exploiting AI agents to perform destructive actions](https://portswigger.net/web-security/llm-attacks/ai-powered-scanner-vulnerabilities/lab-indirect-prompt-injection-via-ai-powered-scan) | Hijacking an AI-powered scanner through content it scans |
| 6 | [Bypassing AI scanner defenses to exfiltrate sensitive information](https://portswigger.net/web-security/llm-attacks/ai-powered-scanner-vulnerabilities/lab-bypassing-ai-scanner-defenses-to-exfiltrate-sensitive-information) | Getting past guardrails and stealing the agent's credentials |
| 7 | [Exploiting AI agents to trigger secondary vulnerabilities](https://portswigger.net/web-security/llm-attacks/ai-powered-scanner-vulnerabilities/lab-exploiting-target-website-vulnerabilities-to-bypass-restrictions) | Steering an agent into exploiting SSRF on an internal network |

**Also from PortSwigger:**
- [All labs](https://portswigger.net/web-security/all-labs): you need the core web topics first. See [Learning Path, Phase 0](docs/learning-path.md#phase-0--web-security-foundations).
- [Creating AI extensions for Burp](https://portswigger.net/burp/documentation/desktop/extend-burp/extensions/creating/creating-ai-extensions): use the Montoya API's AI features in your own Burp extensions.
- [PortSwigger Research](https://portswigger.net/research) and [PortSwigger YouTube](https://www.youtube.com/@PortSwiggerTV).

### Online challenges

| Platform | Notes |
|---|---|
| [Gandalf (Lakera)](https://gandalf.lakera.ai) | The classic prompt injection game. Make the model reveal a password across increasingly hardened levels. Best first step. |
| [Crucible (Dreadnode)](https://crucible.dreadnode.io) | Dozens of AI/ML CTF challenges: prompt injection, model evasion, data analysis, extraction. Solved through a Python API, like real engagements. |
| [HackAPrompt](https://www.hackaprompt.com) | Prompt hacking competitions and tracks. Earlier rounds produced well-known research datasets. |
| [Prompt Airlines (Wiz)](https://promptairlines.com) | A short CTF: manipulate an airline customer-service bot into giving you a free ticket. |
| [Hack The Box CTF](https://ctf.hackthebox.com) | Regularly hosts events with AI/ML categories. |

### Self-hosted vulnerable apps

| Project | Notes |
|---|---|
| [Damn Vulnerable MCP Server](https://github.com/harishsg993010/damn-vulnerable-MCP-server) | Ten challenges covering MCP-specific bugs: tool poisoning, rug pulls, tool shadowing, token theft and more. Actively maintained. |
| [Damn Vulnerable LLM Agent](https://github.com/ReversecLabs/damn-vulnerable-llm-agent) | A ReAct banking agent you hijack through thought/action injection. From ReversecLabs (formerly WithSecure Labs). |
| [Microsoft AI Red Teaming Playground Labs](https://github.com/microsoft/AI-Red-Teaming-Playground-Labs) | The challenges Microsoft uses in its own AI red teaming training, with infrastructure to self-host. |
| [AIGoat](https://github.com/orcasecurity-research/AIGoat) | Deliberately vulnerable AI infrastructure on AWS (Terraform), covering the OWASP ML Top 10. |
| [learn-agent-security-from-scratch](https://github.com/xinbetween/learn-agent-security-from-scratch) | A free 27-chapter course with runnable Python labs: prompt injection, exfiltration channels, tool poisoning, memory attacks, MCP supply chain and sandboxing. New and small, but well structured. |

## Courses and Training Paths

**Free**
- [PortSwigger Web Security Academy](https://portswigger.net/web-security): the LLM labs above, plus all the web fundamentals.
- [Hugging Face Agents Course](https://huggingface.co/learn/agents-course): learn how agents, tool calling and agent loops are built. You cannot break what you do not understand.
- [Hugging Face LLM Course](https://huggingface.co/learn/llm-course): transformers, tokenizers and fine-tuning, hands-on.
- [DeepLearning.AI: Red Teaming LLM Applications](https://www.deeplearning.ai/short-courses/red-teaming-llm-applications/): a short course built with Giskard.
- [Learn Prompting: Prompt Hacking](https://learnprompting.org/docs/prompt_hacking/introduction): a readable introduction to injection, leaking and jailbreaking.
- [Microsoft AI Red Team docs](https://learn.microsoft.com/en-us/security/ai-red-team/): planning and running AI red team operations.

**Paid or subscription**
- [Hack The Box Academy: AI Red Teamer path](https://academy.hackthebox.com/path/preview/ai-red-teamer): built with Google and aligned to SAIF. It covers ML fundamentals, prompt injection, application and system attacks, evasion and privacy attacks. One of the most complete structured paths.
- [TryHackMe: AI Security path](https://tryhackme.com/resources/blog/introducing-the-ai-security-learning-path): launched in 2026. Beginner-friendly rooms built around the OWASP LLM Top 10, plus a matching AI1 certification.

## Attack Techniques

Key ideas to understand, each with one or two of the best explanations. More in [Papers](docs/papers.md).

- **Direct prompt injection and jailbreaking.** [Ignore Previous Prompt](https://arxiv.org/abs/2211.09527) (2022) is the first systematic study. [PAIR](https://arxiv.org/abs/2310.08419) and [TAP](https://arxiv.org/abs/2312.02119) cover automated black-box jailbreaking. Anthropic's [Many-shot jailbreaking](https://www.anthropic.com/research/many-shot-jailbreaking) shows long-context attacks.
- **Indirect prompt injection.** [Not what you've signed up for](https://arxiv.org/abs/2302.12173) by Greshake et al. is the foundational paper. Also see Kai Greshake's [Inject My PDF](https://kai-greshake.de/posts/inject-my-pdf/).
- **Adversarial suffixes (GCG).** [Universal and Transferable Adversarial Attacks on Aligned Language Models](https://arxiv.org/abs/2307.15043), with code at [llm-attacks/llm-attacks](https://github.com/llm-attacks/llm-attacks). [BrokenHill](https://github.com/BishopFox/BrokenHill) is a productionised version.
- **Data exfiltration from LLM apps.** Rendering markdown images, link unfurling and tool calls can all leak data. [Embrace The Red](https://embracethered.com/blog/) documents dozens of real cases in ChatGPT, Copilot, Claude, Gemini and coding agents.
- **Training data extraction.** [Extracting Training Data from LLMs](https://arxiv.org/abs/2012.07805) and [Scalable Extraction from Production Models](https://arxiv.org/abs/2311.17035).
- **Model stealing.** [Stealing Part of a Production Language Model](https://arxiv.org/abs/2403.06634).
- **Data poisoning and backdoors.** [Poisoning Web-Scale Training Datasets is Practical](https://arxiv.org/abs/2302.10149) and [Sleeper Agents](https://arxiv.org/abs/2401.05566).
- **Classic adversarial ML.** Evasion ([FGSM](https://arxiv.org/abs/1412.6572), [PGD](https://arxiv.org/abs/1706.06083)), [membership inference](https://arxiv.org/abs/1610.05820) and [backdoors (BadNets)](https://arxiv.org/abs/1708.06733).
- **Prompt collections for red teamers.** [L1B3RT4S](https://github.com/elder-plinius/L1B3RT4S) is a huge, frequently updated collection of jailbreak prompts. Use it to test guardrails.

## Agent and MCP Security

This is the most active area in 2026. Agents combine untrusted input, private data and the ability to act. Prompt injection then becomes RCE, data theft or destructive actions.

**Must-reads**
- [The lethal trifecta for AI agents](https://simonwillison.net/2025/Jun/16/the-lethal-trifecta/) by Simon Willison. Private data plus untrusted content plus an exfiltration channel adds up to a vulnerability. This is the mental model to use.
- [Simon Willison's prompt injection tag](https://simonwillison.net/tags/prompt-injection/): the best running commentary on the topic since 2022.
- [MCP Security Notification: Tool Poisoning Attacks](https://invariantlabs.ai/blog/mcp-security-notification-tool-poisoning-attacks) by Invariant Labs. The original write-up of hidden instructions in MCP tool descriptions.
- [When prompts become shells: RCE vulnerabilities in AI agent frameworks](https://www.microsoft.com/en-us/security/blog/2026/05/07/prompts-become-shells-rce-vulnerabilities-ai-agent-frameworks/) (Microsoft, 2026): prompt injection that reaches host-level code execution in agent frameworks.
- [Disrupting the first reported AI-orchestrated cyber espionage campaign](https://www.anthropic.com/news/disrupting-AI-espionage) (Anthropic): a real-world case of attackers using an AI coding agent for intrusion operations.
- [MCP Safety Audit](https://arxiv.org/abs/2504.03767): shows how LLMs with MCP can be coerced into credential theft and remote access.

**Benchmarks and research environments**
- [AgentDojo](https://github.com/ethz-spylab/agentdojo) ([paper](https://arxiv.org/abs/2406.13352)): the standard environment for prompt-injection attacks and defenses on tool-using agents.
- [InjecAgent](https://arxiv.org/abs/2403.02691) and [Agent Security Bench](https://arxiv.org/abs/2410.02644).

**Scanners**: see [Red Teaming and Scanning Tools](#red-teaming-and-scanning-tools). The relevant ones are agent-scan, mcp-scanner and agentic-radar.

**Curated lists**
- [awesome-mcp-security](https://github.com/Puliczek/awesome-mcp-security) and SlowMist's [MCP Security Checklist](https://github.com/slowmist/MCP-Security-Checklist).

## Defenses and Secure Design

Prompt injection is **not solved**. Filters and classifiers reduce risk but can be bypassed. Lasting defenses come from architecture: limit what a compromised model can do.

- [Design Patterns for Securing LLM Agents against Prompt Injections](https://arxiv.org/abs/2506.08837) (2025): action-selector, plan-then-execute, dual LLM, context minimisation and other patterns. Start here.
- [Defeating Prompt Injections by Design (CaMeL)](https://arxiv.org/abs/2503.18813) (Google DeepMind, 2025): separates control flow from data flow, and uses capabilities to enforce policy.
- [The Instruction Hierarchy](https://arxiv.org/abs/2404.13208) (OpenAI, 2024): training models to give privileged instructions priority.
- [prompt-injection-defenses](https://github.com/tldrsec/prompt-injection-defenses) (tl;dr sec): every practical and proposed defense in one place.
- [PortSwigger: Defending against LLM attacks](https://portswigger.net/web-security/llm-attacks#defending-against-llm-attacks): treat LLM-reachable APIs as public, and do not rely on prompting.
- [OpenAI: Understanding prompt injections](https://openai.com/index/prompt-injections/): how a frontier lab thinks about the problem for agents.

**Guardrail toolkits** (useful layers, not a complete solution):

| Tool | Status | Notes |
|---|---|---|
| [NeMo Guardrails](https://github.com/NVIDIA-NeMo/Guardrails) | Active | Programmable input, output and dialog rails (NVIDIA). |
| [Guardrails AI](https://github.com/guardrails-ai/guardrails) | Active | Validators for LLM inputs and outputs. |
| [PurpleLlama](https://github.com/meta-llama/PurpleLlama) | Active | Meta's Llama Guard, Prompt Guard, CodeShield and the CyberSecEval benchmarks. |
| [LLM Guard](https://github.com/protectai/llm-guard) | Archived (2026) | Still useful to study how input and output scanners are designed. |

## Red Teaming and Scanning Tools

| Tool | Status | Use it for |
|---|---|---|
| [garak](https://github.com/NVIDIA/garak) | Active, ~10k★ | The "nmap for LLMs". It probes for prompt injection, jailbreaks, data leakage, toxicity and more. |
| [PyRIT](https://github.com/microsoft/PyRIT) | Active, ~5k★ | Microsoft's AI red teaming framework: multi-turn orchestrators, converters and scoring. (The old `Azure/PyRIT` repo is archived. Use `microsoft/PyRIT`.) |
| [promptfoo](https://github.com/promptfoo/promptfoo) | Active, ~27k★ | Eval and red team CLI for prompts, agents and RAG, with OWASP and ATLAS mapped plugins. See its [red team docs](https://www.promptfoo.dev/docs/red-team/). |
| [DeepTeam](https://github.com/confident-ai/deepteam) | Active | Framework for red teaming LLMs and agents. |
| [Giskard](https://github.com/Giskard-AI/giskard-oss) | Active | Testing and vulnerability scanning for LLM agents. |
| [Agentic Security](https://github.com/msoedov/agentic_security) | Active | Agentic LLM vulnerability scanner and fuzzing kit. |
| [FuzzyAI](https://github.com/cyberark/FuzzyAI) | Active | Automated LLM jailbreak fuzzing (CyberArk). |
| [EasyJailbreak](https://github.com/EasyJailbreak/EasyJailbreak) | Active | Framework that implements many published jailbreak attacks. |
| [Inspect](https://github.com/UKGovernmentBEIS/inspect_ai) + [inspect_evals](https://github.com/UKGovernmentBEIS/inspect_evals) | Active | The UK AI Security Institute's eval framework. Many security and cyber evals are built on it. |
| [Rigging](https://github.com/dreadnode/rigging) | Active | Lightweight LLM interaction framework, handy for scripting attacks (Dreadnode). |
| [agent-scan](https://github.com/snyk/agent-scan) | Active | Scans MCP servers, agents and agent skills for tool poisoning and similar issues. Formerly Invariant's `mcp-scan`. |
| [mcp-scanner](https://github.com/cisco-ai-defense/mcp-scanner) | Active | Cisco's MCP server threat scanner. |
| [Agentic Radar](https://github.com/splx-ai/agentic-radar) | Active | Maps and scans agentic workflows (LangGraph, CrewAI and others). |
| [Adversarial Robustness Toolbox (ART)](https://github.com/Trusted-AI/adversarial-robustness-toolbox) | Active | The reference library for classic adversarial ML: evasion, poisoning, extraction and inference. |
| [Dioptra](https://github.com/usnistgov/dioptra) | Active | NIST's testbed for measuring how robust ML models are. |
| [Counterfit](https://github.com/Azure/counterfit) | Archived | Microsoft's older ML attack CLI. Historical interest only. |

## Model Supply Chain Security

Model files can be code. Pickle-based formats run arbitrary code when loaded.

- [ModelScan](https://github.com/protectai/modelscan): scans model files for serialization attacks.
- [Fickling](https://github.com/trailofbits/fickling) (Trail of Bits): pickle decompiler, static analyzer and injection tool.
- [model-transparency](https://github.com/sigstore/model-transparency) (Sigstore): sign and verify ML models.
- [ai-exploits](https://github.com/protectai/ai-exploits): real-world exploits for disclosed vulnerabilities in ML tooling (MLflow, Ray and others). Not updated since 2024, but educational.
- [BadNets](https://arxiv.org/abs/1708.06733): the original ML supply chain backdoor paper.

## Benchmarks and Datasets

- [JailbreakBench](https://github.com/JailbreakBench/jailbreakbench) and [HarmBench](https://github.com/centerforaisafety/HarmBench): standardised jailbreak and refusal evaluations.
- [AgentDojo](https://github.com/ethz-spylab/agentdojo): prompt injection against agents.
- [jailbreak_llms](https://github.com/verazuo/jailbreak_llms): 15k in-the-wild jailbreak prompts (CCS'24).
- [CyberSecEval in PurpleLlama](https://github.com/meta-llama/PurpleLlama): measures cyber risk and capability of LLMs.
- [AIRTBench](https://github.com/dreadnode/AIRTBench-Code): measures how well models can do autonomous AI red teaming, using Crucible challenges.
- [LLMail-Inject](https://github.com/microsoft/llmail-inject-challenge): code and data from Microsoft's adaptive prompt injection challenge.

## AI for Offensive Security

Using LLMs as tools in security work.

- [PentestGPT](https://github.com/GreyDGL/PentestGPT): agentic penetration testing framework.
- [hackingBuddyGPT](https://github.com/ipa-lab/hackingBuddyGPT): minimal LLM hacking agents for research and learning.
- [CAI (Cybersecurity AI)](https://github.com/aliasrobotics/cai): open framework for security agents (repo archived in 2026).
- [LLM Agents can Autonomously Hack Websites](https://arxiv.org/abs/2402.06664): the key paper on offensive agent capability.
- [offensive-ai-compilation](https://github.com/jiep/offensive-ai-compilation): a large list of offensive AI resources.

## Blogs, Newsletters and Research Feeds

- [Embrace The Red](https://embracethered.com/blog/) (Johann Rehberger): real-world prompt injection and data exfiltration findings in production AI products.
- [Simon Willison: prompt injection](https://simonwillison.net/tags/prompt-injection/).
- [Nicholas Carlini's writing](https://nicholas.carlini.com/writing/): adversarial ML research, explained clearly.
- [NVIDIA AI Red Team blog](https://developer.nvidia.com/blog/tag/ai-red-team/).
- [PortSwigger Research](https://portswigger.net/research).
- [HiddenLayer research](https://hiddenlayer.com/research/) and [Lakera AI security guides](https://www.lakera.ai/ai-security-guides).
- [LLM Security (llmsecurity.net)](https://llmsecurity.net): a collection of LLM security papers and links.
- [promptfoo LLM Security DB](https://www.promptfoo.dev/lm-security-db/): a searchable database of LLM vulnerabilities.
- [Google: AI risk and resilience 2026](https://cloud.google.com/security/resources/ai-risk-and-resilience-2026): incident case studies with mapped controls.

## Conferences and Communities

- [DEF CON AI Village](https://aivillage.org): talks, CTFs and the generative AI red teaming events.
- [IEEE SaTML](https://satml.org): the main academic venue for secure and trustworthy ML.
- [CAMLIS](https://www.camlis.org): Conference on Applied Machine Learning in Information Security.
- [USENIX Security](https://www.usenix.org/conference/usenixsecurity26), IEEE S&P, ACM CCS and NDSS: most important attack papers appear here.
- [UK AI Security Institute](https://www.aisi.gov.uk): government research on AI security and evaluations.

## Other Curated Lists

Great work by other people. Go deeper here.

| Repository | Focus |
|---|---|
| [ottosulin/awesome-ai-security](https://github.com/ottosulin/awesome-ai-security) | Broad AI security resources. Very actively maintained. |
| [TalEliyahu/Awesome-AI-Security](https://github.com/TalEliyahu/Awesome-AI-Security) | Research, tools and governance for securing AI. |
| [corca-ai/awesome-llm-security](https://github.com/corca-ai/awesome-llm-security) | LLM security tools, papers and projects. |
| [anmolksachan/AI-ML-Free-Resources-for-Security-and-Prompt-Injection](https://github.com/anmolksachan/AI-ML-Free-Resources-for-Security-and-Prompt-Injection) | Free AI/ML pentesting roadmap for beginners. |
| [Joe-B-Security/awesome-prompt-injection](https://github.com/Joe-B-Security/awesome-prompt-injection) | Prompt injection articles, tutorials and tools. |
| [PromptLabs/Prompt-Hacking-Resources](https://github.com/PromptLabs/Prompt-Hacking-Resources) | AI red teaming, jailbreaking and prompt injection resources. |
| [jiep/offensive-ai-compilation](https://github.com/jiep/offensive-ai-compilation) | Offensive uses of AI and attacks on AI. |
| [greshake/llm-security](https://github.com/greshake/llm-security) | Original indirect prompt injection demos. |
| [Puliczek/awesome-mcp-security](https://github.com/Puliczek/awesome-mcp-security) | MCP security. |
| [ElNiak/awesome-ai-cybersecurity](https://github.com/ElNiak/awesome-ai-cybersecurity) | AI applied to cybersecurity. |
| [The-Art-of-Hacking/h4cker](https://github.com/The-Art-of-Hacking/h4cker) | Omar Santos's huge security repo, with a large AI security section. |

## Contributing

Pull requests are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[CC0 1.0](LICENSE). Linked resources belong to their respective authors.
