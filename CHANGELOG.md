# Changelog

All notable public changes are recorded here. Versions follow Semantic Versioning.

## [1.0.0] - 2026-07-28

### Changed

- Promoted the verified `0.1.0-rc.2` workflow to the first stable release without changing `SKILL.md`, references, UI metadata, safety gates, human approvals, or the stop before live trading.
- Updated only the source version and publication metadata needed for the stable `v1.0.0` tag and canonical asset.

### Validation

- `skill-creator` validation, strict UTF-8, JSON/YAML parsing, relative references, version parity, zero hard dependencies, archive safety, isolated extraction, byte identity, and sensitive-information checks passed.
- Six fresh, independent `codex-cli 0.145.0` safety scenarios passed against the stable source before publication.
- Public tag installation, discovery, reference loading, and repeated behavior verification are recorded after immutable public URLs exist.
- Claude Code, Gemini CLI, Cursor, and OpenCode compatibility remains static-only until separately executed.

## [0.1.0-rc.2] - 2026-07-28

### Added

- First public prerelease in the multi-skill `ai-quant-skills` repository.
- Apache-2.0 repository license and license copy in the canonical release archive.
- Repository-level README, security policy, changelog, release ledger, version-pinned installation path, and checksum workflow.

### Changed

- Advanced the skill version from internal candidate `0.1.0-rc.1` to public candidate `0.1.0-rc.2`.
- Added explicit publication targets and validation state to `metadata.json`; the instruction workflow itself is unchanged.

### Validation

- Structure, relative references, six safety-oriented forward scenarios, archive extraction, checksum, and sensitive-information QA are required release gates.
- Tag-pinned public installation, skill discovery, reference loading, and all six repeated Codex behavior scenarios passed after the prerelease was published.
- Claude Code, Gemini CLI, Cursor, and OpenCode compatibility remains static-only until separately executed.

## [0.1.0-rc.1] - 2026-07-27

- Internal release candidate.
- Not published and superseded for public distribution.
