# karlorz fork — WorkBuddy billing overlay on Likhixang v0.1.49

This checkout is a GitHub fork of https://github.com/Likhixang/cpa-freetier2api-plugin with the 2026-11-10 WorkBuddy global `/v2/report` 10001 patch on top of tag `v0.1.49` (`b26f73d`).

## Remotes

| Remote | URL | Push |
|--------|-----|------|
| origin | https://github.com/karlorz/cpa-freetier2api-plugin | allowed |
| upstream | https://github.com/Likhixang/cpa-freetier2api-plugin | disabled |

Observed on host macos-dev: `/Users/karlchow/Desktop/code/cpa-freetier2api-plugin`

## Paths

| Role | Path |
|------|------|
| Live overlay (kr01) | `/root/cliproxyapi/plugins/linux/arm64/freetier2api-v0.1.49.so` |
| Stock backup (kr01) | `freetier2api-v0.1.49.so.bak-checkin-20261110` |
| Built linux/arm64 `.so` (gitignored) | `dist/freetier2api.so` |
| Overlay sha256 | `12fff03b76a12789f53017a5818b4c8998bd46b9de822fd80c8e2b78ce325759` |
| Management page | https://clifree.karldigi.dev/management.html#/plugin-pages/freetier2api/0 |

## Forbidden

- `git push upstream` / any push to Likhixang
- Public PR to Likhixang unless the operator asks
- GitHub Release / plugin-store publish / `registry.json` upload
- Relabeling the live `.so` away from `v0.1.49` unless the operator asks

A plugin-store reinstall of stock 0.1.49 would overwrite the live overlay.

## Allowed

- `git push origin` (karlorz fork)
- `git fetch upstream` then merge/rebase locally when asked
- `go test ./...` on Mac
- linux/arm64 c-shared rebuild on kr01, then overlay copy + `systemctl --user restart cliproxyapi`
- Do **not** restart the leftover **system** unit (port 8317 bind race)

## Patch files

- `internal/vendors/workbuddy/tasks.go` — `billingChatRequestSendEvent` (arrays, required zero-fields, `deepseek-v4.1-flash`, dashed UUIDv7)
- `internal/vendors/workbuddy/tasks_test.go`

Wiki: `projects/cliproxyapi/work/2026-11-10-freetier2api-global-beacon-private-fork/`
Query: `queries/2026-11-10-kr01-freetier2api-workbuddy-global-checkin-10001.md`
