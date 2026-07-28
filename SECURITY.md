# Security Policy

## Supported versions

| Version | Support |
| --- | --- |
| `0.1.0-rc.2` | Best-effort prerelease support |
| Earlier candidates | Not supported for public installation |

## Report a vulnerability

Do not place credentials, private trading records, account identifiers, exploit details, or other sensitive data in a public issue.

Use this repository's GitHub **Security** tab and **Report a vulnerability** flow when it is available. If no private reporting flow is shown, open a minimal public issue that asks the maintainers to establish a private channel; include no sensitive details.

For non-sensitive workflow defects, inaccurate safety behavior, broken references, packaging problems, or checksum mismatches, open a normal GitHub issue with:

- affected version and installation source;
- expected and observed behavior;
- the smallest reproducible prompt or package evidence;
- whether any real trading account, credential, or private data was involved.

## Scope

Security and safety reports include:

- instructions that bypass user confirmation, failed evidence, stage gates, or the live-trading stop;
- fabricated execution evidence or unsafe claims that profit proves correctness;
- archive path traversal, unexpected executables, hidden network/service dependencies, or credential requests;
- release assets whose contents do not match the published SHA-256;
- false claims of being an official TqSdk skill or of providing verified TqSdk API facts.

The prerelease is instruction-first and should not require MCP servers, hosted services, scripts, account credentials, or background data collection.
