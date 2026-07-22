# PR Evidence — superset-sh/superset

Twelve PRs (one merged, one reopened-as-follow-up, ten open), each rebased onto latest `main`, identity-clean (`Divyam Talwar <divyamtalwar15@gmail.com>`, author + committer), and verified keyless (before/after). Verification uses mocked fetch/DB/auth, `bun audit`, `tsc`, and `actionlint` — no API keys or cloud login — on discovered free ports.

| Folder | PR | Status | Area | Title | Before → After |
|---|---|---|---|---|---|
| **PR1** | [#5466](https://github.com/superset-sh/superset/pull/5466) | Merged | Web / Auth | Require exact public auth route matches | 10 route bypasses fail → 29 pass |
| **PR2** | [#5473](https://github.com/superset-sh/superset/pull/5473) | Open | Host / Auth | Refresh minted JWTs after source token rotation | stale JWT (1 fail) → 9 pass |
| **PR3** | [#5468](https://github.com/superset-sh/superset/pull/5468) | Open | tRPC / Auth | Honor organization header for JWT callers | wrong-org (4 fail) → 7 pass |
| **PR4** | [#5467](https://github.com/superset-sh/superset/pull/5467) | Open | API / Security | Keep proxied Linear images out of shared caches | `public,immutable` → `no-store` (13 pass) |
| **PR5** | [#5470](https://github.com/superset-sh/superset/pull/5470) | Open | Electric / Security | Lock tenant filters and auth stripping | unguarded → 14 contracts (regression caught) |
| **PR6** | [#5469](https://github.com/superset-sh/superset/pull/5469) | Open | API / Test-integrity | Run committed API route tests in CI | script-not-found → 16 pass |
| **PR7** | [#5471](https://github.com/superset-sh/superset/pull/5471) | Open | SDK | Sync version metadata and task-status exports | `TaskStatuses` undefined → exported |
| **PR8** | [#5472](https://github.com/superset-sh/superset/pull/5472) | Open | SDK | Expose host agent launch options | tsc 4 errors → 0 errors |
| **PR9** | [#5474](https://github.com/superset-sh/superset/pull/5474) | Open | CI | Build Vercel apps on pull requests | no build job → 5-app matrix (actionlint clean) |
| **PR10** | [#5476](https://github.com/superset-sh/superset/pull/5476) | Open | CI / Security | Skip preview deployments for forked PRs | 0 guards → 7 gated (fork→SKIP) |
| **PR11** | [#5477](https://github.com/superset-sh/superset/pull/5477) | Open | CI / Release | Serialize production deployments | no concurrency → serialized |
| **PR12** | [#5874](https://github.com/superset-sh/superset/pull/5874) | Open | Dependencies / Security | Update axios override to patched release | axios 1.14.0: 28 advisories → 1.18.1: 0 |

Each `PRx/` contains: `README.md` (issue → root cause → fix → before/after → risk → honest CI note), `screenshots/` (2× terminal captures), and `transcripts/` (raw command output the shots were rendered from).

### Honesty notes
- **PR1** is merged; its before/after runs the merged regression suite against a verbatim reconstruction of the pre-merge matcher.
- **PR5** is a hardening / regression-contract PR (no runtime bug on base); the "before" shows main has no guards + a deliberately-introduced regression being caught.
- **PR9 / PR10 / PR11** are GitHub-Actions workflow changes — there is no runnable stack, so the evidence is the diff + `actionlint` validation (+ a guard truth-table for PR10), labeled as config-level.
- **PR12** supersedes the maintainer-closed #5478 (closed while it carried a lockfile conflict, now resolved); opened as a follow-up because `main` is still on the vulnerable axios pin.
