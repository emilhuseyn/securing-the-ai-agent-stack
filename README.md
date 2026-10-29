# Securing the AI Agent Stack

A free, open, hands-on course for software and security engineers who want to move into AI
security. Every module is built around a bug class that has been found in real open-source AI
tooling, with a lab that reproduces it safely in a local container and then fixes it.

Status: proposal and curriculum. Modules are written and published one at a time.

## Who it is for

Backend, platform and application-security engineers who already know web security and want to
work on the security of AI systems: agent platforms, tool servers, model supply chains. No machine
learning background is assumed.

## Format

- Written modules (Markdown) with diagrams, published in this repository under CC BY 4.0
- One lab per module: a deliberately vulnerable component in Docker Compose, an exploit walkthrough,
  then the fix and a regression test (code under MIT)
- Self-paced; every lab runs on a laptop with no cloud account or paid API key
- Two free online cohorts at the end, with weekly office hours, to test the material on real learners

## Modules

1. **Threat model of an agent platform.** What an agent platform holds (model keys, documents, tool
   credentials), who can talk to it, and where its controls are enforced.
2. **Server-side request forgery through agent tools.** Web-fetch tools, document connectors,
   webhooks and OpenAPI tool imports reaching internal services and cloud metadata. Lab: a vulnerable
   fetch tool, then an egress filter that also survives redirects and DNS rebinding.
3. **Authorization in agent platforms.** The "sibling route" pattern: one endpoint checks ownership,
   its neighbour on the same resource does not. Lab: find it with a diff of route guards, fix it,
   add a test.
4. **MCP authorization.** OAuth for MCP servers: audience validation, token passthrough, discovery
   SSRF. Lab: a mock authorization server and a server that accepts a token issued for another
   resource.
5. **When prompt injection meets server-side bugs.** Indirect prompt injection as the trigger for
   the bugs in modules 2-4, and why model-level defences do not fix them.
6. **Model and tool supply chain.** Signatures (e.g. the OpenSSF model-signing format), revision
   pinning, provenance for MCP server packages. Lab: verify a signed model, detect an unpinned load.
7. **Secrets and CI for AI projects.** Credentials in container layers, notebooks and CI logs;
   GitHub Actions hardening. Lab: find a leaked key in an image layer and rotate it properly.
8. **Finding, reporting and fixing.** Coordinated disclosure in open source: writing a report
   maintainers act on, GitHub security advisories, sending the fix upstream.

## Author

Emil Huseynov, security researcher and backend developer (Baku State University; M.Sc. Information
Security, Azerbaijan Technical University). Paid findings in smart-contract audit competitions,
vulnerability reports to open-source AI tools, an MCP OAuth flaw confirmed by Ory, security pull
requests to Apache Struts, and about 40 software-supply-chain measurement papers in 2026.
GitHub: https://github.com/emilhuseyn

See [BUDGET.md](BUDGET.md) for the funding plan.
