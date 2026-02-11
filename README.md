# mcp-server-pr-analyzer

A small utility to analyze GitHub pull requests for the MCP server project. This repository contains starter tooling to fetch and evaluate PRs, plus a simple example analyzer.

## Contents

- `pr_analyzer.py` — a minimal `PRAnalyzer` class and CLI entrypoint for running an analysis.
- `github.py` — (existing) helpers for interacting with the GitHub API.
- `.env` — environment variables used by the project (not committed with secrets).
- `requirements.txt` / `pyproject.toml` — Python dependencies.

## Quick Start

1. Create a `.env` file in the project root (see example entries below).
2. Install dependencies:

```bash
python -m pip install -r requirements.txt
```

3. Run the analyzer (example):

```bash
GITHUB_TOKEN="your_token_here" EXAMPLE_REPO="owner/repo" EXAMPLE_PR=1 python pr_analyzer.py
```

## Environment (.env)

Store non-committed configuration and secrets in `.env`. Example entries:

```
# GitHub personal access token with repo/read permissions
GITHUB_TOKEN=your_token_here

# Example repo and PR for local testing
EXAMPLE_REPO=owner/repo
EXAMPLE_PR=1
```

## Development notes

- `pr_analyzer.py` is intentionally small — extend `PRAnalyzer.analyze()` to implement checks you want (linting, changelog presence, size limits, label rules, etc.).
- Use `github.py` helpers to fetch PR metadata and files. Consider using PyGitHub or the GitHub REST API directly.

