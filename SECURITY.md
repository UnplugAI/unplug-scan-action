# Security Policy

## Reporting a Vulnerability

If you discover a security vulnerability in this GitHub Action, please report it responsibly.

**Preferred:** [GitHub Security Advisories](https://github.com/UnplugAI/unplug-scan-action/security/advisories/new) (private disclosure).

**Email:** [security@unplug-ai.org](mailto:security@unplug-ai.org)

Please include:

- A description of the vulnerability and its potential impact
- Steps to reproduce or a proof of concept
- Affected versions (e.g. `v1.0.0`)

Do **not** open a public GitHub issue for security vulnerabilities.

## Response Timeline

- **Acknowledgment** within 3 business days
- **Initial assessment** within 7 business days
- **Fix or mitigation plan** communicated as soon as a path is identified

We will coordinate disclosure timing with you and credit reporters who wish to be named.

## Supported Versions

| Version | Supported |
|---------|-----------|
| Latest `v1` release | Yes |
| Older releases | Best effort |

## Scope

In scope:

- The composite action defined in `action.yml`
- Official CI workflows in this repository

Out of scope:

- The `unplug-ai` SDK itself (report to [UnplugAI/Unplug](https://github.com/UnplugAI/Unplug/security/advisories/new))
- Third-party actions consumed here (e.g. `astral-sh/setup-uv`, `actions/setup-python`) unless this action introduces the vulnerability
