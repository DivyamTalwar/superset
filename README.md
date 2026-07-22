# PR Evidence — superset-sh/superset

One merged + five open PRs, each rebased onto latest `main`, identity-clean, and verified keyless (before/after `bun test`).

| Folder | PR | Status | Area | Title |
|---|---|---|---|---|
| **PR1** | [#5466](https://github.com/superset-sh/superset/pull/5466) | MERGED | Web / Auth | Require exact public auth route matches |
| **PR2** | [#5473](https://github.com/superset-sh/superset/pull/5473) | OPEN | Host-service / Auth | Refresh minted JWTs after source token rotation |
| **PR3** | [#5468](https://github.com/superset-sh/superset/pull/5468) | OPEN | tRPC / Auth | Honor organization header for JWT callers |
| **PR4** | [#5467](https://github.com/superset-sh/superset/pull/5467) | OPEN | API / Security | Keep proxied Linear images out of shared caches |
| **PR5** | [#5470](https://github.com/superset-sh/superset/pull/5470) | OPEN | Electric-proxy / Security | Lock tenant filters and upstream auth stripping |
| **PR6** | [#5469](https://github.com/superset-sh/superset/pull/5469) | OPEN | API / Test-integrity | Run committed API route tests in CI |

Each `PRx/` has: `README.md` (issue → root cause → fix → before/after → risk → CI), `screenshots/` (2× terminal captures), and `transcripts/` (raw `bun test` output).

Author: Divyam Talwar <divyamtalwar15@gmail.com>. All verification is keyless (mocked fetch/DB/auth), run on discovered free ports.
