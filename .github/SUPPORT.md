# Getting Support

MCPmed is an academic open-source project maintained by volunteers. We want to help you succeed, but please use the right channel for your question.

## Before you ask

1. **Read the repo's `README.md`** — installation, configuration, and basic usage are almost always documented there.
2. **Read the paper** — [arXiv:2507.08055](https://arxiv.org/abs/2507.08055) covers the motivation, architecture, and intended use cases of MCPmed as a whole.
3. **Search existing issues** — your question may already have been answered.

## Where to ask

| Question type | Channel |
|---|---|
| "How do I use this server / wire it into Claude Desktop / run a specific tool?" | Open a **Discussion** (if enabled) or a **question-labelled issue** on the specific repo. |
| "I think I found a bug." | Open an **issue** using the bug report template. |
| "I'd like a new feature / database connector." | Open an **issue** using the feature request template. |
| "I want to contribute code." | See [`CONTRIBUTING.md`](CONTRIBUTING.md). |
| "I think I found a security issue." | See [`SECURITY.md`](SECURITY.md) — **do not open a public issue**. |
| General discussion about MCPmed, the paper, or biomedical MCP tooling | The project website: <https://mcpmed.org> |

## What we can't help with

- **Upstream API issues.** If NCBI, EMBL-EBI, or STRING-db returns the wrong data, that is an upstream problem. We will try to document the behavior, but we cannot fix it.
- **LLM application code.** How you integrate an MCP server into your own agent or application is out of scope. We maintain the servers; we don't debug everyone's orchestration.
- **Biological interpretation.** We can help you fetch the data; interpreting it is your research.

## Response times

This project is maintained on a best-effort basis. Expect issue responses within days, not hours. If something is urgent, consider filing a pull request with a proposed fix — it is the single fastest way to get attention.
