# AGENTS.md — cpa-freetier2api-plugin (karlorz fork)

GitHub fork of Likhixang/cpa-freetier2api-plugin with the kr01 WorkBuddy global `/v2/report` 10001 overlay on `v0.1.49`.

Read `docs/FORK.md` before any git or release action.

## Remotes

- `origin` = https://github.com/karlorz/cpa-freetier2api-plugin (push allowed)
- `upstream` = https://github.com/Likhixang/cpa-freetier2api-plugin (fetch only)

## Hard rule

Push to **karlorz origin** only. Do not push to Likhixang. Do not open a public PR to Likhixang unless the operator asks. Do not GitHub-release. Do not publish to plugin-store.

## Overlay deploy (kr01)

1. Build linux/arm64 c-shared on kr01.
2. Backup `/root/cliproxyapi/plugins/linux/arm64/freetier2api-v0.1.49.so`.
3. Copy the new `.so` onto that same filename.
4. `systemctl --user restart cliproxyapi` only. Never the leftover system unit.

Live overlay sha256 prefix: `12fff03b76a12789`.
