# Glossary

Short definitions of terms used in AI security.

**Adversarial example.** An input with small, deliberate changes that cause a model to make a wrong prediction. One example is an image that looks normal to humans but is classified as something else.

**Agent.** An LLM that runs in a loop. It decides on actions, calls tools, observes the results and continues until a goal is reached.

**Agent goal hijack (ASI01).** Manipulating an agent's objective, usually through content it processes. This is the top risk in the OWASP Agentic Top 10.

**Backdoor / trojan.** A hidden behaviour planted during training or fine-tuning. A specific trigger in the input activates it.

**Confused deputy.** A privileged component that is tricked into misusing its authority on behalf of an attacker. LLM agents are the textbook modern example.

**Context window.** All the text (system prompt, user messages, tool outputs, retrieved documents) the model sees at once. The model can't reliably tell instructions apart from data within it.

**Data exfiltration (LLM).** Leaking data from an LLM app through channels the model controls. Examples are markdown image URLs, links, tool calls and web requests.

**Data poisoning.** Corrupting training, fine-tuning or retrieval data to change how a model behaves.

**Direct prompt injection.** The user types instructions that override the developer's intended behaviour.

**Evasion attack.** Crafting inputs at inference time so that a model misclassifies them.

**Excessive agency.** An LLM has more tools, permissions or autonomy than it needs. A single injection then becomes a damaging action.

**GCG (Greedy Coordinate Gradient).** An optimisation attack that finds adversarial suffixes which jailbreak aligned LLMs.

**Guardrails.** Input and output filters, classifiers or policies around an LLM. They help, but on their own they can't stop a determined attacker.

**Indirect prompt injection.** Instructions hidden in content the model processes (web pages, emails, documents, tool output, code comments), not typed by the user.

**Insecure output handling.** Trusting LLM output and passing it to a browser, shell, SQL engine or other interpreter without validation. This leads to XSS, RCE and SQLi.

**Instruction hierarchy.** Training a model to prioritise system and developer instructions over user and tool content.

**Jailbreak.** Getting a model to bypass its safety training and produce content it was trained to refuse.

**Lethal trifecta.** Simon Willison's term for an agent with access to private data, exposure to untrusted content, and the ability to communicate externally. If all three are present, data can be stolen.

**MCP (Model Context Protocol).** An open protocol for connecting LLM applications to tools and data sources (MCP servers).

**Membership inference.** Determining whether a specific record was in a model's training data.

**Model extraction / stealing.** Recreating a model, or parts of it, by querying its API.

**Model inversion.** Reconstructing sensitive features of training data from model outputs.

**Pickle / serialization attack.** Malicious code embedded in model files that use unsafe formats (Python pickle). It runs when the model is loaded.

**Prompt leaking.** Extracting a system prompt or hidden instructions.

**RAG (Retrieval-Augmented Generation).** Feeding retrieved documents into the model's context. Every retrieved document is a possible injection vector.

**Red teaming (AI).** Adversarial testing of AI systems for security and safety failures, using a structured methodology.

**Rug pull (MCP).** An MCP server that changes its tool definitions to malicious ones after the user has approved it.

**System prompt.** Developer instructions placed at the start of the context. It is not a security boundary.

**Tool poisoning.** Hidden instructions inside MCP or tool descriptions that the model reads and follows. Users usually never see them.

**Tool shadowing.** A malicious tool whose description changes how the agent uses *other*, trusted tools.
