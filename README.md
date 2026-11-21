<div align="center">
  <h2>Yoshi Kinga</h2>
  <p><strong>Deterministic Security, Cost Circuit-Breakers & Privacy Guardrails for Production AI Agents</strong></p>

  <p>
    <a href="https://github.com/yoshikinga?tab=repositories">
      <img src="https://img.shields.io/github/stars/yoshikinga?affiliations=OWNER&style=flat-square&logo=github&label=Ecosystem%20Stars&color=18181B" alt="GitHub Stars" />
    </a>
    <a href="https://github.com/sponsors/yoshikinga">
      <img src="https://img.shields.io/github/sponsors/yoshikinga?style=flat-square&logo=githubsponsors&logoColor=EA4AAA&label=Sponsors&color=18181B" alt="GitHub Sponsors" />
    </a>
    <img src="https://img.shields.io/badge/Dependencies-Zero-10B981?style=flat-square" alt="Zero Dependencies" />
    <img src="https://img.shields.io/badge/TypeScript-Strict%20ESM%2FCJS-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript Strict" />
    <img src="https://img.shields.io/badge/License-MIT-64748B?style=flat-square" alt="MIT License" />
  </p>
</div>

---

### Engineering Philosophy

Autonomous AI agents and **Model Context Protocol (MCP)** servers introduce non-deterministic operational risks: runaway API spend, sensitive data exfiltration across streaming chunks, and unauthorized tool execution. 

I design **zero-dependency, sub-millisecond TypeScript primitives** that sit between LLMs and critical infrastructure—giving engineering teams deterministic safety guarantees without supply-chain bloat or vendor lock-in.

---

### Production Safety Architecture

```mermaid
flowchart LR
    A[User / Prompt] --> B[redact-stream]
    B -->|Sanitized Stream| C[LLM / AI Agent]
    C -->|Tool Call Request| D[token-fuse]
    D -->|Within USD Budget| E[mcp-warden]
    E -->|Policy Verified + Audited| F[(MCP Tools & Infra)]

    style B fill:#0f172a,stroke:#38bdf8,stroke-width:1.5px,color:#f8fafc
    style D fill:#0f172a,stroke:#f59e0b,stroke-width:1.5px,color:#f8fafc
    style E fill:#0f172a,stroke:#10b981,stroke-width:1.5px,color:#f8fafc
```

### Core Open-Source Suite

| Package | Focus | Key Guarantee |
| :--- | :--- | :--- |
| **[`mcp-warden`](https://github.com/yoshikinga/mcp-warden)** | **MCP Firewall & Audit** | JSON-RPC tool-call policy enforcement, path-traversal blocking & SHA-256 audit logs. |
| **[`token-fuse`](https://github.com/yoshikinga/token-fuse)** | **FinOps Circuit-Breaker** | Real-time USD spend caps & semantic infinite-loop termination in `< 1ms`. |
| **[`redact-stream`](https://github.com/yoshikinga/redact-stream)** | **Streaming PII Scrubber** | Chunk-boundary aware API key, JWT & PII redaction with reversible local tokens. |

---

### Technical Standards & Runtime Stack

<p>
  <img src="https://img.shields.io/badge/Language-TypeScript%205.x-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Node.js-20%2B-339933?style=flat-square&logo=nodedotjs&logoColor=white" alt="Node.js" />
  <img src="https://img.shields.io/badge/Bun-Compatible-FBF0DF?style=flat-square&logo=bun&logoColor=black" alt="Bun" />
  <img src="https://img.shields.io/badge/Deno-Compatible-000000?style=flat-square&logo=deno&logoColor=white" alt="Deno" />
  <img src="https://img.shields.io/badge/Cloudflare%20Workers-Edge%20Ready-F38020?style=flat-square&logo=cloudflare&logoColor=white" alt="Cloudflare Workers" />
  <img src="https://img.shields.io/badge/Crypto-Web%20Crypto%20API-475569?style=flat-square" alt="Web Crypto API" />
</p>

* **Zero External Runtime Dependencies:** `0` third-party `npm` packages in production builds—eliminating transitive CVE risks.
* **Universal Edge Compatibility:** Pure Web Standard APIs (`ReadableStream`, `TransformStream`, `crypto.subtle`) running identically across Node.js, Bun, Deno, and Serverless Edge runtimes.
* **Deterministic Latency:** Engineered for inline request pipelines with strict memory bounds and zero regex catastrophic backtracking.

---

### Sustaining Independent Security Infrastructure

All libraries in this ecosystem are MIT-licensed, vendor-neutral, and maintained independently. If these guardrails protect your production API budgets, customer privacy, or MCP toolchains, consider backing ongoing development and security maintenance.

<p align="left">
  <a href="https://github.com/sponsors/yoshikinga">
    <img src="https://img.shields.io/badge/Sponsor%20%40yoshikinga-GitHub%20Sponsors-EA4AAA?style=for-the-badge&logo=githubsponsors&logoColor=white" alt="Sponsor @yoshikinga on GitHub Sponsors" />
  </a>
</p>
