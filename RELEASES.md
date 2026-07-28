# Release Ledger

This ledger maps public versions to immutable source and package identities. GitHub release assets, not automatic source archives, are the canonical downloadable packages.

| Version | Release type | Tag | Source commit | Asset | SHA-256 | Codex verification | Other agents |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `1.0.0` | Stable | `v1.0.0` | Pending tag commit | `ai-quant-strategy-workflow-1.0.0.zip` | `db4ca0438f6c64268f4f6f82585cb846a818f37f9153670ce918ffac0807ecd5` | Pending public-URL run | Static compatibility only |
| `0.1.0-rc.2` | Prerelease | `v0.1.0-rc.2` | `017eda7e6b80176aab7dd358cdecd66d605b2ab9` | `ai-quant-strategy-workflow-0.1.0-rc.2.zip` | `9b35b08de88936312b0153b7bfcee091f94483609156238ba3b8867edde5f50c` | Public tag install + discovery + 6/6 behavior PASS | Static compatibility only |
| `0.1.0-rc.1` | Internal candidate | None | `0032024` | Internal only | `b93a42decddd0172f485c2ad142246b094803ca90d8d6c455e35b305caa8ac8d` | 6/6 local harness at the time | Static compatibility only |

## Rollback rule

Do not overwrite or silently replace a published asset. If a package changes, issue a new version, tag, asset name, and checksum. To roll back, reinstall a previously verified version-pinned source or canonical ZIP and record the selected version in the consuming project.
