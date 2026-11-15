# Papers

Key papers, grouped by topic. ⭐ marks papers to read first. Titles and years were checked against arXiv.

## Prompt injection

- ⭐ **Not what you've signed up for: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection** (Greshake et al., 2023) — [arXiv:2302.12173](https://arxiv.org/abs/2302.12173). Defines indirect prompt injection. This is the most important paper in this list.
- **Ignore Previous Prompt: Attack Techniques For Language Models** (Perez & Ribeiro, 2022) — [arXiv:2211.09527](https://arxiv.org/abs/2211.09527). An early systematic study of goal hijacking and prompt leaking.
- **Prompt Injection attack against LLM-integrated Applications** (Liu et al., 2023) — [arXiv:2306.05499](https://arxiv.org/abs/2306.05499). HouYi attack against real applications.
- **Formalizing and Benchmarking Prompt Injection Attacks and Defenses** (Liu et al., 2023) — [arXiv:2310.12815](https://arxiv.org/abs/2310.12815).

## Jailbreaking and adversarial attacks on LLMs

- ⭐ **Universal and Transferable Adversarial Attacks on Aligned Language Models** (Zou et al., 2023) — [arXiv:2307.15043](https://arxiv.org/abs/2307.15043). The GCG adversarial suffix attack.
- **Jailbreaking Black Box Large Language Models in Twenty Queries** (Chao et al., 2023) — [arXiv:2310.08419](https://arxiv.org/abs/2310.08419). PAIR: using an attacker LLM to jailbreak.
- **Tree of Attacks: Jailbreaking Black-Box LLMs Automatically** (Mehrotra et al., 2023) — [arXiv:2312.02119](https://arxiv.org/abs/2312.02119). TAP.
- **Many-shot jailbreaking** (Anthropic, 2024) — [research post](https://www.anthropic.com/research/many-shot-jailbreaking).
- **Red Teaming Language Models to Reduce Harms** (Ganguli et al., 2022) — [arXiv:2209.07858](https://arxiv.org/abs/2209.07858). Methods and lessons from large-scale human red teaming.
- **A Survey of Attacks on Large Vision-Language Models** (2024) — [arXiv:2407.07403](https://arxiv.org/abs/2407.07403). Multimodal attacks.

## Agent and MCP security

- ⭐ **AgentDojo: A Dynamic Environment to Evaluate Prompt Injection Attacks and Defenses for LLM Agents** (Debenedetti et al., 2024) — [arXiv:2406.13352](https://arxiv.org/abs/2406.13352).
- **InjecAgent: Benchmarking Indirect Prompt Injections in Tool-Integrated LLM Agents** (Zhan et al., 2024) — [arXiv:2403.02691](https://arxiv.org/abs/2403.02691).
- **Agent Security Bench (ASB)** (Zhang et al., 2024) — [arXiv:2410.02644](https://arxiv.org/abs/2410.02644).
- **MCP Safety Audit: LLMs with the Model Context Protocol Allow Major Security Exploits** (Radosevich & Halloran, 2025) — [arXiv:2504.03767](https://arxiv.org/abs/2504.03767).
- **LLM Agents can Autonomously Hack Websites** (Fang et al., 2024) — [arXiv:2402.06664](https://arxiv.org/abs/2402.06664).

## Defenses

- ⭐ **Design Patterns for Securing LLM Agents against Prompt Injections** (Beurer-Kellner et al., 2025) — [arXiv:2506.08837](https://arxiv.org/abs/2506.08837).
- ⭐ **Defeating Prompt Injections by Design** (CaMeL, Debenedetti et al., 2025) — [arXiv:2503.18813](https://arxiv.org/abs/2503.18813).
- **The Instruction Hierarchy: Training LLMs to Prioritize Privileged Instructions** (Wallace et al., 2024) — [arXiv:2404.13208](https://arxiv.org/abs/2404.13208).
- **MELON: Provable Defense Against Indirect Prompt Injection Attacks in AI Agents** (2025) — [arXiv:2502.05174](https://arxiv.org/abs/2502.05174).

## Privacy, extraction and model stealing

- ⭐ **Extracting Training Data from Large Language Models** (Carlini et al., 2020) — [arXiv:2012.07805](https://arxiv.org/abs/2012.07805).
- **Scalable Extraction of Training Data from (Production) Language Models** (Nasr et al., 2023) — [arXiv:2311.17035](https://arxiv.org/abs/2311.17035).
- **Stealing Part of a Production Language Model** (Carlini et al., 2024) — [arXiv:2403.06634](https://arxiv.org/abs/2403.06634).
- **Membership Inference Attacks against Machine Learning Models** (Shokri et al., 2016) — [arXiv:1610.05820](https://arxiv.org/abs/1610.05820).
- **Stealing Machine Learning Models via Prediction APIs** (Tramèr et al., 2016) — [arXiv:1609.02943](https://arxiv.org/abs/1609.02943).

## Poisoning and backdoors

- **Poisoning Web-Scale Training Datasets is Practical** (Carlini et al., 2023) — [arXiv:2302.10149](https://arxiv.org/abs/2302.10149).
- **Sleeper Agents: Training Deceptive LLMs that Persist Through Safety Training** (Hubinger et al., 2024) — [arXiv:2401.05566](https://arxiv.org/abs/2401.05566).
- **BadNets: Identifying Vulnerabilities in the Machine Learning Model Supply Chain** (Gu et al., 2017) — [arXiv:1708.06733](https://arxiv.org/abs/1708.06733).

## Classic adversarial examples

- ⭐ **Intriguing properties of neural networks** (Szegedy et al., 2013) — [arXiv:1312.6199](https://arxiv.org/abs/1312.6199). Where adversarial examples were first described.
- ⭐ **Explaining and Harnessing Adversarial Examples** (Goodfellow et al., 2014) — [arXiv:1412.6572](https://arxiv.org/abs/1412.6572). FGSM.
- **Towards Deep Learning Models Resistant to Adversarial Attacks** (Madry et al., 2017) — [arXiv:1706.06083](https://arxiv.org/abs/1706.06083). PGD and adversarial training.

## Benchmarks

- **JailbreakBench** (2024) — [arXiv:2404.01318](https://arxiv.org/abs/2404.01318).
- **HarmBench** (2024) — [arXiv:2402.04249](https://arxiv.org/abs/2402.04249).

## Reports and taxonomies

- **NIST AI 100-2 E2025: Adversarial Machine Learning — A Taxonomy and Terminology of Attacks and Mitigations** — [NIST](https://csrc.nist.gov/pubs/ai/100/2/e2025/final).
- **Disrupting the first reported AI-orchestrated cyber espionage campaign** (Anthropic) — [report](https://www.anthropic.com/news/disrupting-AI-espionage).

## Keep up with new papers

- [llmsecurity.net](https://llmsecurity.net)
- arXiv listings for cs.CR and cs.LG. Search for "prompt injection", "LLM agent security" and "jailbreak".
- Proceedings of [IEEE SaTML](https://satml.org), USENIX Security, IEEE S&P, ACM CCS and NDSS.
