# AI Quant Skills

Open, reviewable skills for AI-assisted quantitative-strategy development.

This repository is a collection. Each installable skill lives under `skills/<skill-name>/`; repository governance and release records stay at the repository root so the skill itself remains small.

## Available skills

| Skill | Purpose | Current version | Status |
| --- | --- | --- | --- |
| [`ai-quant-strategy-workflow`](skills/ai-quant-strategy-workflow/) | Turn a vague strategy idea into an approved task brief, then advance one evidence-gated stage at a time and stop before live trading. | `1.0.0` | Stable |

## Install in Codex

Ask Codex to use `$skill-installer` with this immutable source:

```text
https://github.com/BotMe-NotImplemented/ai-quant-skills/tree/v1.0.0/skills/ai-quant-strategy-workflow
```

After installation, start a new turn and invoke `$ai-quant-strategy-workflow`. If it is not discovered, restart Codex.

For a manual project-scoped install, download the canonical release ZIP, verify its SHA-256 file, and extract the `ai-quant-strategy-workflow` folder under `<repo>/.agents/skills/`.

- [Stable release page](https://github.com/BotMe-NotImplemented/ai-quant-skills/releases/tag/v1.0.0)
- [Canonical ZIP](https://github.com/BotMe-NotImplemented/ai-quant-skills/releases/download/v1.0.0/ai-quant-strategy-workflow-1.0.0.zip)
- [SHA-256 file](https://github.com/BotMe-NotImplemented/ai-quant-skills/releases/download/v1.0.0/ai-quant-strategy-workflow-1.0.0.zip.sha256)

Do not use GitHub's automatically generated source archives as a substitute for the canonical skill ZIP.

## Safety boundary

This project provides an educational workflow, not investment advice, a return promise, a security recommendation, or permission to trade. Backtest profit does not prove correct behavior. Version 1 stops at a live-trading gate and never authorizes or switches to a real account.

This is not a TqSdk official skill and does not copy or impersonate TqSdk documentation. Any TqSdk API, function, account, or product fact must be verified against an independent official documentation skill, source code, or current official documentation.

The current skill is instruction-first. It requires no MCP server, hosted service, script, trading credential, or background data collection.

## Verify and update

Pin production or teaching references to a versioned tag and asset URL. Before upgrading:

1. Read [CHANGELOG.md](CHANGELOG.md) and [RELEASES.md](RELEASES.md).
2. Download the new ZIP and adjacent checksum file.
3. Recompute SHA-256 locally and compare it with the published value.
4. Install into a clean location and repeat the safety scenarios relevant to your use.
5. Keep the previous verified version available for rollback.

## License and support

The repository is licensed under [Apache License 2.0](LICENSE). Use GitHub Issues for non-sensitive defects or documentation gaps. Follow [SECURITY.md](SECURITY.md) for sensitive reports.
