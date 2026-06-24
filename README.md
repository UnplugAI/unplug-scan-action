# Unplug Agent Scan — GitHub Action

Scan **agent-related files changed in a pull request** for prompt injection and related threats using [unplug-ai](https://pypi.org/project/unplug-ai/) (regex-only Guard — no ML download required).

Designed for repos that ship:

- `AGENTS.md` / `AGENT.md`
- `.cursor/rules`, `.cursor/hooks.json`, MCP configs
- `mcp.json`, Claude Desktop MCP settings

## Quick start

```yaml
name: Unplug agent scan

on:
  pull_request:

permissions:
  contents: read

jobs:
  scan:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v6
        with:
          fetch-depth: 0

      - uses: UnplugAI/unplug-scan-action@v1
        with:
          base-ref: main
```

## Inputs

| Input | Default | Description |
|-------|---------|-------------|
| `base-ref` | `main` | Base branch for `git diff origin/<base-ref>...HEAD` |
| `python-version` | `3.12` | Python version |
| `unplug-version` | `>=0.4.0,<0.5` | PyPI constraint for `unplug-ai` |

## Monorepo / SDK development

If you develop the SDK in the same repo, use the composite action in [UnplugAI/Unplug](https://github.com/UnplugAI/Unplug):

```yaml
- uses: UnplugAI/Unplug/.github/actions/unplug-scan@dev
  with:
    base-ref: dev
    install-mode: local
```

## Local CLI

```bash
pip install "unplug-ai>=0.4.0"
unplug-scan-pr --base-ref main
```

## Marketplace

This repository is published to the [GitHub Marketplace](https://github.com/marketplace?type=actions) as **Unplug Agent Scan**.

## License

Apache-2.0 — see [LICENSE](LICENSE).
