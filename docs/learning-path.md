# AI Security Learning Path

An ordered, hands-on roadmap. Each phase lists what to learn, where to practise, and how you know you're done. Time estimates assume a few hours a week.

**Who this is for:** security people who want to add AI, and developers who want to break and secure AI systems. You don't need a PhD in ML. You do need to be comfortable with HTTP, Python and a terminal.

**Guiding principles**
- **Practise every week.** Reading without labs doesn't stick.
- **Web security comes first.** Most AI application bugs end up as ordinary bugs (XSS, SSRF, IDOR, command injection) that an LLM can trigger for you.
- **Focus on agents.** In 2026 the impact is in tool-using agents, MCP and coding assistants, not chatbots that say rude things.
- **Assume prompt injection can't be fully prevented.** Judge systems by what a compromised model can do.

```
Phase 0  Web security foundations        (PortSwigger core topics)
Phase 1  How LLMs and agents work         (enough to reason about attacks)
Phase 2  Attacking LLM applications       (PortSwigger Web LLM labs, Gandalf)
Phase 3  Attacking agents and MCP         (PortSwigger AI scanner labs, DVMCP)
Phase 4  Red teaming at scale             (garak, PyRIT, promptfoo, Crucible)
Phase 5  Classic adversarial ML           (evasion, poisoning, extraction)
Phase 6  Defense and secure architecture  (design patterns, threat modelling)
Phase 7  Specialise and stay current
```

---

## Phase 0 — Web security foundations

**Why:** an LLM wired to APIs is a confused deputy that attacker-controlled text can steer. To exploit or fix it, you need to know the bugs it can reach.

**Do these** [PortSwigger Web Security Academy](https://portswigger.net/web-security) topics, at least the Apprentice labs:
- [Cross-site scripting](https://portswigger.net/web-security/cross-site-scripting): needed for insecure output handling.
- [SSRF](https://portswigger.net/web-security/ssrf): agents that fetch URLs are SSRF engines.
- [OS command injection](https://portswigger.net/web-security/os-command-injection) and [SQL injection](https://portswigger.net/web-security/sql-injection).
- [Access control](https://portswigger.net/web-security/access-control): needed for excessive agency.
- [API testing](https://portswigger.net/web-security/api-testing): LLM tool calls are API calls.
- [CSRF](https://portswigger.net/web-security/csrf) and [information disclosure](https://portswigger.net/web-security/information-disclosure).

**Tools:** Burp Suite Community or Professional.

**Done when** you can solve Apprentice labs in these topics without hints.

---

## Phase 1 — How LLMs and agents work

**Why:** you need a working mental model of tokens, context windows, system prompts, tool calling, RAG and agent loops. You don't need the maths.

**Learn**
- [3Blue1Brown: Neural networks](https://www.3blue1brown.com/topics/neural-networks): visual intuition, including transformers and attention.
- [Andrej Karpathy: Intro to Large Language Models](https://www.youtube.com/watch?v=zjkBMFhNj_g): a one-hour talk that ends with a section on LLM security.
- [Hugging Face Agents Course](https://huggingface.co/learn/agents-course): build an agent with tools. This is the most important item in this phase.
- Optional deeper dive: [Karpathy's Zero to Hero](https://karpathy.ai/zero-to-hero.html), [Hugging Face LLM Course](https://huggingface.co/learn/llm-course), [Build an LLM from Scratch](https://github.com/rasbt/LLMs-from-scratch).

**Do**
- Run a local model (for example with Ollama or llama.cpp) and call it from Python.
- Build a tiny agent with two tools, such as "read URL" and "send email". You'll attack it in Phase 3.
- Read the [MCP specification](https://github.com/modelcontextprotocol/modelcontextprotocol) overview and run one MCP server locally.

**Done when** you can explain where untrusted text enters an agent's context, and what the model can do with it.

---

## Phase 2 — Attacking LLM applications

**Read**
- [OWASP Top 10 for LLM Applications](https://genai.owasp.org/llm-top-10/).
- [PortSwigger: Web LLM attacks](https://portswigger.net/web-security/llm-attacks): read the whole topic page.
- [Greshake et al., Indirect Prompt Injection](https://arxiv.org/abs/2302.12173): the foundational paper.
- A few posts from [Embrace The Red](https://embracethered.com/blog/) on markdown-image data exfiltration.

**Practise**
1. [Gandalf](https://gandalf.lakera.ai): all levels.
2. PortSwigger Web LLM labs, in order:
   - [Exploiting LLM APIs with excessive agency](https://portswigger.net/web-security/llm-attacks/lab-exploiting-llm-apis-with-excessive-agency)
   - [Exploiting vulnerabilities in LLM APIs](https://portswigger.net/web-security/llm-attacks/lab-exploiting-vulnerabilities-in-llm-apis)
   - [Indirect prompt injection](https://portswigger.net/web-security/llm-attacks/lab-indirect-prompt-injection)
   - [Exploiting insecure output handling in LLMs](https://portswigger.net/web-security/llm-attacks/lab-exploiting-insecure-output-handling-in-llms)
3. [Prompt Airlines](https://promptairlines.com).
4. Optional structured course: the [TryHackMe AI Security path](https://tryhackme.com/resources/blog/introducing-the-ai-security-learning-path), or the first modules of the [HTB AI Red Teamer path](https://academy.hackthebox.com/path/preview/ai-red-teamer).

**Done when** you can, without hints: map an LLM's tools, use it to reach a backend vulnerability, and plant an indirect injection that leads to XSS or data theft.

---

## Phase 3 — Attacking agents and MCP

**Read**
- [OWASP Top 10 for Agentic Applications 2026](https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/).
- [The lethal trifecta](https://simonwillison.net/2025/Jun/16/the-lethal-trifecta/).
- [Tool Poisoning Attacks](https://invariantlabs.ai/blog/mcp-security-notification-tool-poisoning-attacks) (Invariant Labs).
- [MCP Security Best Practices](https://modelcontextprotocol.io/specification/draft/basic/security_best_practices).
- [When prompts become shells](https://www.microsoft.com/en-us/security/blog/2026/05/07/prompts-become-shells-rce-vulnerabilities-ai-agent-frameworks/) (Microsoft, 2026).

**Practise**
1. PortSwigger [AI-powered scanner vulnerabilities](https://portswigger.net/web-security/llm-attacks/ai-powered-scanner-vulnerabilities) labs:
   - [Exploiting AI agents to perform destructive actions](https://portswigger.net/web-security/llm-attacks/ai-powered-scanner-vulnerabilities/lab-indirect-prompt-injection-via-ai-powered-scan)
   - [Bypassing AI scanner defenses to exfiltrate sensitive information](https://portswigger.net/web-security/llm-attacks/ai-powered-scanner-vulnerabilities/lab-bypassing-ai-scanner-defenses-to-exfiltrate-sensitive-information)
   - [Exploiting AI agents to trigger secondary vulnerabilities](https://portswigger.net/web-security/llm-attacks/ai-powered-scanner-vulnerabilities/lab-exploiting-target-website-vulnerabilities-to-bypass-restrictions)
2. [Damn Vulnerable MCP Server](https://github.com/harishsg993010/damn-vulnerable-MCP-server): all challenges.
3. [Damn Vulnerable LLM Agent](https://github.com/ReversecLabs/damn-vulnerable-llm-agent).
4. Attack the agent you built in Phase 1. Make it email you its secrets using only content it reads.
5. Optional: [learn-agent-security-from-scratch](https://github.com/xinbetween/learn-agent-security-from-scratch) labs.
6. Scan some real MCP servers with [agent-scan](https://github.com/snyk/agent-scan) or [mcp-scanner](https://github.com/cisco-ai-defense/mcp-scanner) and review the findings by hand.

**Done when** you can explain and demonstrate tool poisoning, a rug pull, cross-tool exfiltration, and prompt-injection-to-RCE in an agent.

---

## Phase 4 — Red teaming at scale

**Why:** manual prompting doesn't scale to real engagements. Learn the tools and the methodology.

**Read**
- [OWASP GenAI Red Teaming Guide](https://genai.owasp.org/resource/genai-red-teaming-guide/).
- [Microsoft AI Red Team docs](https://learn.microsoft.com/en-us/security/ai-red-team/).
- [MITRE ATLAS](https://atlas.mitre.org): learn to map findings to techniques.
- [PAIR](https://arxiv.org/abs/2310.08419), [TAP](https://arxiv.org/abs/2312.02119) and [GCG](https://arxiv.org/abs/2307.15043): how automated attacks work.

**Practise**
- Run [garak](https://github.com/NVIDIA/garak) against a local model. Read the probes and understand each one.
- Write a multi-turn attack with [PyRIT](https://github.com/microsoft/PyRIT).
- Set up a [promptfoo red team](https://www.promptfoo.dev/docs/red-team/) config against your Phase 1 agent.
- Solve challenges on [Crucible](https://crucible.dreadnode.io) through its Python API.
- Write a short red team report for your agent: scope, findings mapped to OWASP and ATLAS, impact and fixes.

**Done when** you can deliver a reproducible, automated assessment of an LLM application, with a written report.

---

## Phase 5 — Classic adversarial ML

**Why:** vision, fraud, malware and spam classifiers are still deployed everywhere, and LLM attacks build on these ideas.

**Read**
- [NIST AI 100-2 E2025](https://csrc.nist.gov/pubs/ai/100/2/e2025/final): the taxonomy.
- Classics: [Intriguing properties](https://arxiv.org/abs/1312.6199), [FGSM](https://arxiv.org/abs/1412.6572), [PGD](https://arxiv.org/abs/1706.06083), [membership inference](https://arxiv.org/abs/1610.05820), [model stealing](https://arxiv.org/abs/1609.02943), [BadNets](https://arxiv.org/abs/1708.06733).
- [OWASP ML Security Top 10](https://github.com/OWASP/www-project-machine-learning-security-top-10).

**Practise**
- Generate FGSM and PGD adversarial examples with [ART](https://github.com/Trusted-AI/adversarial-robustness-toolbox).
- Inspect a malicious pickle with [Fickling](https://github.com/trailofbits/fickling) and scan models with [ModelScan](https://github.com/protectai/modelscan).
- Do the evasion and privacy modules of the [HTB AI Red Teamer path](https://academy.hackthebox.com/path/preview/ai-red-teamer), and the ML challenges on Crucible.
- Optional: deploy [AIGoat](https://github.com/orcasecurity-research/AIGoat).

**Done when** you can explain the difference between evasion, poisoning, extraction and inference attacks, and run each one.

---

## Phase 6 — Defense and secure architecture

**Read**
- [Design Patterns for Securing LLM Agents against Prompt Injections](https://arxiv.org/abs/2506.08837).
- [CaMeL: Defeating Prompt Injections by Design](https://arxiv.org/abs/2503.18813).
- [prompt-injection-defenses](https://github.com/tldrsec/prompt-injection-defenses).
- [Google SAIF](https://saif.google), [OWASP AISVS](https://github.com/OWASP/AISVS) and [OWASP AI Exchange](https://owaspai.org).

**Practise**
- Threat model your Phase 1 agent. List trust boundaries, untrusted inputs, sensitive data, actions and exfiltration channels.
- Redesign it with one pattern (for example plan-then-execute or dual LLM). Then re-run your Phase 4 attacks.
- Add [NeMo Guardrails](https://github.com/NVIDIA-NeMo/Guardrails) or [Llama Prompt Guard](https://github.com/meta-llama/PurpleLlama) and measure how much of your attack suite it stops. Then bypass it.
- Measure defenses on [AgentDojo](https://github.com/ethz-spylab/agentdojo).

**Done when** you can review an AI feature design and give concrete architectural fixes, not only "add a filter".

---

## Phase 7 — Specialise and stay current

Choose a direction:
- **AI application pentesting and bug bounty:** many bug bounty programmes now include AI features. Keep up with Embrace The Red and PortSwigger Research.
- **Agent and MCP security engineering:** secure agent harnesses, authorisation, sandboxing.
- **ML research:** read [SaTML](https://satml.org), USENIX Security and IEEE S&P papers, and reproduce one.
- **AI for offensive security:** [PentestGPT](https://github.com/GreyDGL/PentestGPT), [hackingBuddyGPT](https://github.com/ipa-lab/hackingBuddyGPT), [AIRTBench](https://github.com/dreadnode/AIRTBench-Code).

**Weekly habits**
- Read [Simon Willison's prompt-injection tag](https://simonwillison.net/tags/prompt-injection/) and [Embrace The Red](https://embracethered.com/blog/).
- Follow [MITRE ATLAS data releases](https://github.com/mitre-atlas/atlas-data/releases) and the [OWASP GenAI project](https://genai.owasp.org/initiatives/).
- Watch DEF CON [AI Village](https://aivillage.org) talks.
- Turn one new vulnerability write-up a week into a lab you can reproduce.
