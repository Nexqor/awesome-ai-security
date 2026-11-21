<p align="center">
  <img src="https://raw.githubusercontent.com/Nexqor/Nexqor/main/banner.png" alt="Nexqor" width="100%">
</p>

<h1 align="center">Awesome AI Security 🛡️</h1>

<p align="center">
  A curated list of frameworks, tools, papers, labs and real incidents for <b>securing AI systems</b>:<br/>
  LLMs, RAG pipelines and autonomous agents.
</p>

<p align="center">
  <a href="https://awesome.re"><img src="https://awesome.re/badge-flat2.svg" alt="Awesome"/></a>
  <a href="https://nexqor.github.io"><img src="https://img.shields.io/badge/site-nexqor.github.io-c41237?style=for-the-badge" alt="site"/></a>
  <a href="https://x.com/whyNexqor"><img src="https://img.shields.io/badge/X-@whyNexqor-000000?style=for-the-badge&logo=x&logoColor=white" alt="X"/></a>
  <img src="https://img.shields.io/badge/PRs-welcome-c41237?style=for-the-badge" alt="PRs welcome"/>
</p>

> AI is the new attack surface. This list is maintained by [Nexqor](https://github.com/Nexqor) and updated as new attacks, tools and incidents appear.

---

## Contents

- [Frameworks & Standards](#frameworks--standards)
- [Offensive Tools / Red Teaming](#offensive-tools--red-teaming)
- [Defensive Tools / Guardrails](#defensive-tools--guardrails)
- [Model Supply Chain](#model-supply-chain)
- [MCP & Agent Tooling Security](#mcp--agent-tooling-security)
- [Benchmarks & Evaluations](#benchmarks--evaluations)
- [Key Papers](#key-papers)
- [Practice Labs & CTFs](#practice-labs--ctfs)
- [Blogs & Researchers](#blogs--researchers)
- [Incident Timeline 2026](#incident-timeline-2026)
- [Related Nexqor Projects](#related-nexqor-projects)

---

## Frameworks & Standards

- [OWASP Top 10 for LLM & GenAI Applications](https://genai.owasp.org/) - The reference list of LLM risks: prompt injection, sensitive data disclosure, excessive agency and more.
- [MITRE ATLAS](https://atlas.mitre.org/) - ATT&CK-style knowledge base of adversary tactics and techniques against AI systems.
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) - Govern, map, measure and manage AI risk.
- [NIST AI 100-2: Adversarial Machine Learning Taxonomy](https://csrc.nist.gov/pubs/ai/100/2/e2023/final) - Shared vocabulary for evasion, poisoning, privacy and abuse attacks.
- [Google Secure AI Framework (SAIF)](https://saif.google/) - Google's framework for building and deploying AI securely.

## Offensive Tools / Red Teaming

- [garak](https://github.com/NVIDIA/garak) - LLM vulnerability scanner: probes for jailbreaks, injection, leakage and toxicity.
- [PyRIT](https://github.com/Azure/PyRIT) - Microsoft's Python Risk Identification Toolkit for generative AI red teaming.
- [promptfoo](https://github.com/promptfoo/promptfoo) - Test, eval and red team LLM apps from the CLI or CI.
- [Counterfit](https://github.com/Azure/counterfit) - Automation layer for assessing the security of ML models.
- [Adversarial Robustness Toolbox (ART)](https://github.com/Trusted-AI/adversarial-robustness-toolbox) - Attacks and defenses for evasion, poisoning, extraction and inference.

## Defensive Tools / Guardrails

- [LLM Guard](https://github.com/protectai/llm-guard) - Input/output scanners for prompt injection, PII, secrets and toxic content.
- [NeMo Guardrails](https://github.com/NVIDIA/NeMo-Guardrails) - Programmable rails that keep LLM apps on-topic and safe.
- [Purple Llama / Llama Guard](https://github.com/meta-llama/PurpleLlama) - Meta's open tools and classifiers for safer LLM input and output.
- [Rebuff](https://github.com/protectai/rebuff) - Multi-layer prompt injection detector.
- [nexqor-tools](https://github.com/Nexqor/nexqor-tools) - Lightweight prompt-injection scanner for documents, web pages and RAG content.

## Model Supply Chain

- [ModelScan](https://github.com/protectai/modelscan) - Scans model files (pickle, H5, SavedModel) for unsafe code.
- [Safetensors](https://github.com/huggingface/safetensors) - Safe tensor storage format that cannot execute code on load.
- Rule of thumb: never `torch.load()` an untrusted checkpoint. Pickle deserialization = arbitrary code execution.

## MCP & Agent Tooling Security

- [MCPTox](https://arxiv.org/abs/2508.14925) - Benchmark for tool poisoning attacks on real-world MCP servers.
- [CSA: MCP tool description poisoning](https://labs.cloudsecurityalliance.org/research/csa-research-note-mcp-tool-description-poisoning-20260711-cs/) - How poisoned tool descriptions exfiltrate data.
- [CSA: MCP tool poisoning & IDE auto-execution](https://labs.cloudsecurityalliance.org/research/csa-research-note-mcp-tool-poisoning-auto-execution-20260701/) - Auto-loaded workspace configs as an attack path.
- [Playbook 09: MCP Tool Poisoning](https://github.com/Nexqor/ai-attack-playbook/blob/main/09-mcp-tool-poisoning.md) - Attack chain, detection and defenses.
- [AI Agent Security Checklist](https://nexqor.github.io/checklist.html) - 24 checks with a live score.

## Benchmarks & Evaluations

- [HarmBench](https://github.com/centerforaisafety/HarmBench) - Standardized evaluation of automated red teaming and refusal.
- [JailbreakBench](https://github.com/JailbreakBench/jailbreakbench) - Open robustness benchmark for jailbreak attacks.
- [AgentDojo](https://github.com/ethz-spylab/agentdojo) - Dynamic environment for prompt injection attacks and defenses on tool-using agents.

## Key Papers

| Year | Paper | Why it matters |
|------|-------|----------------|
| 2021 | [Extracting Training Data from Large Language Models](https://arxiv.org/abs/2012.07805) (Carlini et al.) | Models memorize and leak training data verbatim. |
| 2022 | [Ignore Previous Prompt: Attack Techniques for Language Models](https://arxiv.org/abs/2211.09527) (Perez & Ribeiro) | Early systematic study of goal hijacking and prompt leaking. |
| 2023 | [Not what you've signed up for: Indirect Prompt Injection](https://arxiv.org/abs/2302.12173) (Greshake et al.) | Instructions hidden in data the model reads can hijack LLM-integrated apps. |
| 2023 | [Poisoning Web-Scale Training Datasets is Practical](https://arxiv.org/abs/2302.10149) (Carlini et al.) | Cheap, real-world poisoning of public training data. |
| 2023 | [Universal and Transferable Adversarial Attacks on Aligned LLMs](https://arxiv.org/abs/2307.15043) (Zou et al.) | Automatically generated suffixes jailbreak many models at once. |
| 2024 | [Sleeper Agents](https://arxiv.org/abs/2401.05566) (Hubinger et al.) | Backdoored behavior can survive safety training. |
| 2025 | ["Your AI, My Shell": Prompt Injection on Agentic Coding Editors](https://arxiv.org/abs/2509.22040) | Injection in coding agents leads to command execution. |

## Practice Labs & CTFs

- [Gandalf by Lakera](https://gandalf.lakera.ai/) - Trick an LLM into revealing a password across escalating levels.
- [AgentDojo](https://github.com/ethz-spylab/agentdojo) - Try attacks and defenses against tool-using agents.
- [ai-attack-playbook](https://github.com/Nexqor/ai-attack-playbook) - Nexqor's step-by-step breakdowns of each attack class.

## Blogs & Researchers

- [Simon Willison: Prompt injection series](https://simonwillison.net/series/prompt-injection/) - The most complete running commentary on prompt injection.
- [Embrace The Red](https://embracethered.com/blog/) - Johann Rehberger's hands-on research on data exfiltration from AI assistants.
- [Microsoft Security Blog](https://www.microsoft.com/en-us/security/blog/) - Agent framework vulnerabilities and AI red team findings.
- [Nexqor on X](https://x.com/whyNexqor) - Daily breakdowns of AI hacks, leaks and patches.

## Incident Timeline 2026

> Every entry is sourced. Scope of ongoing incidents may change, so check the latest vendor update.

| Date | Incident | Class | Source |
|------|----------|-------|--------|
| 2026-05 | Prompt injection in Semantic Kernel could escalate to host-level RCE; patched by removing the exposed tool | Agent framework RCE | [Microsoft](https://www.microsoft.com/en-us/security/blog/2026/05/07/prompts-become-shells-rce-vulnerabilities-ai-agent-frameworks/) |
| 2026-04-21 | "Comment and Control": one injection leaked secrets from three AI coding agents | Prompt injection | [VentureBeat](https://venturebeat.com/security/ai-agent-runtime-security-system-card-audit-comment-and-control-2026) |
| 2026 | LiteLLM `/key/regenerate` flaw (CVE-2026-40217) used to escalate to proxy admin in LLMjacking | LLMjacking | [The Hacker News](https://thehackernews.com/2026/11/amazon-uncovers-ai-agent-campaign.html) |
| 2026-11-08 | RCE in SGLang inference engine exploited on a NEAR AI server | Inference infra RCE | [CSA CISO Briefing](https://labs.cloudsecurityalliance.org/research/ciso-daily-briefing-20261111/) |
| 2026-11-09 | Fireworks AI breach widens: model weights, datasets and Notion AI chats accessed | LLMjacking / data breach | [The Hacker News](https://thehackernews.com/2026/11/fireworks-ai-breach-widens-to-expose.html) |
| 2026-11-16 | Amazon reports AI agents scanning for API keys in LiteLLM, Dify, Ollama and other apps | Credential hunting | [The Hacker News](https://thehackernews.com/2026/11/amazon-uncovers-ai-agent-campaign.html) |
| 2026-07 | Poisoned MCP tool descriptions as a silent exfiltration path; IDEs auto-loading workspace MCP configs | MCP tool poisoning | [CSA](https://labs.cloudsecurityalliance.org/research/csa-research-note-mcp-tool-description-poisoning-20260711-cs/) |
| 2026-10 | Microsoft DDR 2026 describes JADEPUFFER, a fully autonomous ransomware attack (July 2026) | Autonomous ransomware | [Tech Times](https://www.techtimes.com/articles/328467/20261002/microsoft-2026-security-report-autonomous-ransomware-has-hacked-real-organizations.htm) |
| 2026-11 | Copilot in Visual Studio/SSMS: filename trick reaches agent's own MCP config, RCE (patched) | Coding agent RCE | [Adversa AI](https://adversa.ai/blog/top-ai-coding-agent-security-resources-november-2026/) |
| 2026-11-18 | "TheMailer" phishing kit uses LLMs to write a unique lure per victim | AI phishing | [SC Media](https://scworld.com/brief/new-ai-powered-phishing-kit-automates-malicious-email-campaigns) |
| 2026-11-19 | Coinbase blocks $4.7M sent to a deepfake Elon Musk livestream | Deepfake fraud | [SC Media](https://www.scworld.com/brief/coinbase-blocks-4-7-million-in-cryptocurrency-transfers-linked-to-deepfake-scam) |
| 2026-11-20 | GAO assessment: AI scales phishing, deepfakes and multi-stage attacks | Policy | [GAO](https://www.gao.gov/assets/gao-27-108458.pdf) |

## Related Nexqor Projects

- [ai-attack-playbook](https://github.com/Nexqor/ai-attack-playbook) - How each AI attack works, and how to stop it.
- [nexqor-tools](https://github.com/Nexqor/nexqor-tools) - Small defensive scripts from the posts.
- [nexqor.github.io](https://nexqor.github.io) - News, playbook and glossary on the web.

---

## Contributing

Found a tool, paper or incident that belongs here? Open a PR with:
1. One line in the right section: `- [Name](link) - What it does.`
2. For incidents: date, class and a primary source.

Educational content for defenders. ⭐ Star the repo to follow updates.
