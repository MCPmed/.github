# Security Policy

## Reporting a Vulnerability

If you discover a security vulnerability in any MCPmed repository, **please do not open a public GitHub issue**. Public disclosure before a fix is available puts users at risk.

Instead, report it privately using **GitHub's private vulnerability reporting**:

1. Go to the affected repository on GitHub.
2. Click the **Security** tab.
3. Click **Report a vulnerability**.
4. Fill in the form with as much detail as possible.

If private vulnerability reporting is not enabled on a particular repo, email the maintainers directly — the contact is listed in the paper ([arXiv:2507.08055](https://arxiv.org/abs/2507.08055)) and in each repo's `pyproject.toml` under `[project.authors]`.

## What to include

A good report contains:

- The repository and version (or commit SHA) affected.
- A description of the vulnerability and its potential impact.
- Step-by-step instructions to reproduce it, ideally with a minimal proof of concept.
- Any suggested mitigation or patch, if you have one.

## Our commitment

- We will acknowledge your report within **5 business days**.
- We will keep you informed of our progress as we investigate and develop a fix.
- We will credit you in the release notes unless you prefer to remain anonymous.
- We will coordinate public disclosure with you once a fix is released.

## Scope

This policy covers all repositories under the [MCPmed GitHub organization](https://github.com/MCPmed). It does **not** cover vulnerabilities in the upstream databases and APIs these servers wrap (NCBI, EMBL-EBI, STRING-db, UCSC, etc.) — please report those to the respective upstream maintainers.

## Security considerations for MCP servers

MCP servers expose tools to LLMs, which then execute them on behalf of users. When contributing, be mindful of:

- **Prompt injection** via tool outputs. Treat any string returned from an upstream API as potentially adversarial when it flows back into an LLM context.
- **SSRF and URL handling**. Validate and restrict any user-supplied URLs before fetching.
- **Credential leakage**. Never echo API keys, tokens, or session cookies in tool responses or logs.
- **Rate limiting and abuse**. Upstream databases have terms of service — do not build servers that let an LLM DoS them.
