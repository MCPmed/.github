# Contributing to MCPmed

Thanks for your interest in improving MCPmed. This file is the **organization-wide default** — every repo under [github.com/MCPmed](https://github.com/MCPmed) inherits it unless it ships its own `CONTRIBUTING.md`.

## What MCPmed is

MCPmed is a collection of [Model Context Protocol](https://modelcontextprotocol.io) servers that expose biomedical and bioinformatics databases to LLMs. See [`profile/README.md`](../profile/README.md) for the full catalog and the accompanying paper ([arXiv:2507.08055](https://arxiv.org/abs/2507.08055)).

## Where to contribute

Priority areas, in rough order:

1. **New database connectors** — wrap an additional biomedical API as an MCP server.
2. **Tests** — several existing servers declare test tooling but ship no test files. Filling in real tests is high-leverage work.
3. **Bug fixes and upstream API drift** — the underlying databases evolve; our wrappers need to keep up.
4. **Documentation and worked examples** — every server should have at least one end-to-end example runnable in under a minute.

## How to start a new MCP server

Use the [`Cookiecutter-MCPmed`](https://github.com/MCPmed/Cookiecutter-MCPmed) template. It scaffolds a Python package with `pyproject.toml`, `pytest`, `ruff`, `black`, `mypy`, and an MCP server skeleton wired up for you.

```bash
cookiecutter gh:MCPmed/Cookiecutter-MCPmed
```

**Python is the default language** for MCPmed servers. The scientific Python ecosystem (biopython, scanpy, pandas, pyarrow, RDKit) is irreplaceable for this domain, and our users read and write Python. TypeScript is supported as a secondary path for thin pass-through wrappers that perform no scientific computation.

## Development workflow

1. **Fork** the repository you want to change.
2. **Create a feature branch** off `main`: `git checkout -b feat/short-description`.
3. **Install in editable mode with dev extras**:
   ```bash
   pip install -e ".[dev]"
   pre-commit install   # if the repo ships .pre-commit-config.yaml
   ```
4. **Make your change.** Keep pull requests focused — one logical change per PR.
5. **Run the quality gates locally** before pushing:
   ```bash
   ruff check .
   black --check .
   mypy <package_name>   # where configured
   pytest
   ```
6. **Open a pull request** against the upstream `main` branch. Fill in the PR template.

## Code style

- **Python**: PEP 8, enforced by `ruff` and `black`. Type annotations are expected on all public functions; `mypy` runs in CI where configured.
- **TypeScript**: `eslint` + `prettier`. Type-check with `tsc --noEmit`.
- **Imports**: let `ruff`/`isort` handle ordering — don't hand-sort.
- **Docstrings**: public MCP tools must have a one-line description that shows up in `list_tools`. That description *is* the LLM's documentation, so write it for a model, not a human reader.

## Commit messages

- Use [Conventional Commits](https://www.conventionalcommits.org/) where practical: `feat:`, `fix:`, `docs:`, `test:`, `refactor:`, `ci:`, `chore:`.
- Write in the imperative mood ("add GEO series endpoint", not "added").
- **Do not include AI-generated self-references or meta-commentary** in commit messages. Keep them factual and conventional.

## Testing expectations

Every MCP tool (`@mcp.tool`) should have at least:

1. **One happy-path test** that calls the tool with realistic inputs and asserts the response shape.
2. **One schema test** that exercises the `list_tools` output and confirms the tool's JSON schema is valid and stable.

For tools that hit external APIs, record fixtures with `vcrpy` (Python) or `msw` (TypeScript) so the suite runs offline and in CI.

## Licensing

- New contributions must be compatible with **BSD-3-Clause or MIT**. Do not introduce copyleft dependencies (GPL, AGPL) without prior discussion.
- By submitting a pull request, you agree your contribution is licensed under the terms of the repository's `LICENSE` file.

## Reporting issues

- **Bugs**: file an issue with a minimal reproduction — we cannot debug what we can't run.
- **Feature requests**: describe the database, the research use case, and a sketch of the MCP tools you imagine.
- **Security issues**: see [`SECURITY.md`](SECURITY.md) — do **not** open a public issue.

## Code of Conduct

All MCPmed spaces follow the [Contributor Covenant](CODE_OF_CONDUCT.md). Be kind; assume good intent; disagree on ideas, not people.
