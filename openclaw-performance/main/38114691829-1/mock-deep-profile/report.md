# Kova OpenClaw Runtime Report

> **❌ [FAIL]** — gateway peak RSS 1683.4 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 1982.8 MB, gateway 1683.4 MB, command-tree 1263.6 MB

## Verdict

| Field | Value |
|---|---|
| Verdict | FAIL |
| Reason | gateway peak RSS 1683.4 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 1982.8 MB, gateway 1683.4 MB, command-tree 1263.6 MB |
| Blocking findings | 4 |
| Warnings | 0 |
| Records | 2 (FAIL:2) |

## Proof Completeness

- Completeness: complete: 2
- Required obligations: 120 total, 0 missing, 0 failed
- Categories: command: 102, artifact: 2, cleanup: 2, collector: 2, invariant: 12

## Run

| Field | Value |
|---|---|
| Run ID | `kova-261011-052637-56e5b9` |
| Generated | 2026-10-11T05:35:26.344Z |
| Mode | execution |
| Target | `local-build:/home/runner/_work/openclaw/openclaw` |
| Platform | linux 6.6.141 (x64) · v24.19.0 |
| Repeat / parallel | 1 / 1 |
| Auth | mock (openai) |
| Network frontage | port |

## Coverage

| Field | Value |
|---|---:|
| Records | 2 |
| Scenarios | 2 |
| States | 2 |
| FAIL | 2 |

## Findings

| Severity | Area | Scenario | Finding | Evidence |
|---|---|---|---|---|
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway peak RSS 1683.4 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 1982.8 MB, gateway 1683.4 MB, command-tree 1263.6 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 266 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway-tree peak RSS 1982.8 MB exceeded threshold 1440 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 266 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | status-cli max CPU interval \[166.4%, 281.3%\] crosses threshold 200%; CPU measurement is inconclusive | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 266 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | warm provider was fast (1ms), but OpenClaw spent 12180ms before provider work. | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1848.2 |

## Performance Summary

- Resource measurement scope: product
- Resource headline contract: `primary-role-product-scope-v4`

| Scenario | Samples | Status | Health Ready | Gateway RSS | Tracked RSS | CPU | Cold Turn | Warm Turn | Cold Pre-Provider |
|---|---:|---|---:|---:|---:|---:|---:|---:|---:|
| gateway-performance/many-bundled-plugins | 1 | FAIL:1 | 266ms | 1683.4MB | n/a | 239.1% | n/a | n/a | n/a |
| agent-cold-warm-message/mock-openai-provider | 1 | FAIL:1 | n/a | 0MB | n/a | 336.9% | 13408ms | 13691ms | 11930ms |

## Samples

| Sample | Status | Scenario | Upgrade From | Health Ready | Gateway RSS | Tracked RSS | Cold Turn | Warm Turn | Blocker |
|---:|---|---|---|---:|---:|---:|---:|---:|---|
| 1 | FAIL | gateway-performance/many-bundled-plugins |  | 266ms | 1683.4 MB | 3044.3 MB | n/a | n/a | gateway peak RSS 1683.4 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 1982.8 MB, gateway 1683.4 MB, command-tree 1263.6 MB |
| 1 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 2028.7 MB | 13408ms | 13691ms | warm provider was fast (1ms), but OpenClaw spent 12180ms before provider work. |

## Resource Roles

- Measurement scope: product
- Headline contract: `primary-role-product-scope-v4`
- gateway-tree: RSS 1982.8 MB (scenario gateway-performance/many-bundled-plugins); CPU 286.9% (scenario gateway-performance/many-bundled-plugins)
- command-tree: RSS 1956.5 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 382.1% (scenario agent-cold-warm-message/mock-openai-provider)
- status-cli: RSS 1381.1 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 349.4% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-process: RSS 1848.2 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 336.9% (scenario agent-cold-warm-message/mock-openai-provider)
- gateway: RSS 1683.4 MB (scenario gateway-performance/many-bundled-plugins); CPU 239.1% (scenario gateway-performance/many-bundled-plugins)
- uncategorized: RSS 722.4 MB (scenario gateway-performance/many-bundled-plugins); CPU 221% (scenario gateway-performance/many-bundled-plugins)
- model-cli: RSS 426.6 MB (scenario gateway-performance/many-bundled-plugins); CPU 191.9% (scenario gateway-performance/many-bundled-plugins)
- plugin-cli: RSS 364.8 MB (scenario gateway-performance/many-bundled-plugins); CPU 192% (scenario gateway-performance/many-bundled-plugins)

## Selected Sample Details

### gateway-performance sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261011-052637-56e5b9/kova-gateway-performance-man-d48bd949-kova-261011-052637-56e5b9
Measurements:
- startup: listening 1ms; health 266ms; readiness ready (gateway became healthy within the readiness threshold); gateway running; restarts 4
- health: startup p95 265ms; post-ready p95 2ms; failures 0; final failures 0; slowest startup-sample/cold-start 265ms
- resources: scope product; contract primary-role-product-scope-v4; gateway RSS 1683.4 MB; tracked total 3044.3 MB; max CPU 239.1%; samples 119; roles gateway-tree 1982.8MB/286.9%, gateway 1683.4MB/239.1%, command-tree 1263.6MB/281.3%, status-cli 1263.6MB/281.3%; performance thresholds skipped 8 (instrumented)
- agent: not-run
- Agent turn stats: count 0; p95 n/a; max n/a; pre-provider p95 n/a
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages 0; warm reuse true
- diagnostics: timeline available; slowest span cli.command-startup 1334.63ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 19/19/13
- Violations:
  - gateway peak RSS 1683.4 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 1982.8 MB, gateway 1683.4 MB, command-tree 1263.6 MB
  - gateway-tree peak RSS 1982.8 MB exceeded threshold 1440 MB
  - status-cli max CPU interval \[166.4%, 281.3%\] crosses threshold 200%; CPU measurement is inconclusive

### agent-cold-warm-message sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261011-052637-56e5b9/kova-agent-cold-warm-message-2c26dd1d-kova-261011-052637-56e5b9
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1848.2 MB; tracked total 2028.7 MB; max CPU 336.9%; samples 138; roles command-tree 1956.5MB/382.1%, agent-process 1848.2MB/336.9%, status-cli 1381.1MB/349.4%, agent-cli 222.2MB/191.9%; performance thresholds skipped 15 (instrumented)
- agent: turn 13691ms; cold/warm 13408ms/13691ms; cold-warm delta 0ms; pre-provider 12180ms; provider 1ms; metadata scans 14 (381.85ms); event-loop n/a; polls 0; cleanup n/a; diagnosis pre-provider-stall; leaks 0
- Agent turn stats: count 2; p95 13676.85ms; max 13691ms; pre-provider p95 12167.5ms
- agent CLI attribution: cold known 5669ms / unattributed 6261ms; warm known 6135ms / unattributed 6045ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span agent.startup 1710.48ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 67/49/9
- Violations:
  - warm provider was fast (1ms), but OpenClaw spent 12180ms before provider work.
- Agent turns:
  - cold: total 13408ms; pre-provider 11930ms; provider 2ms; post-provider 1476ms; response true
    - active window: metadata scans 7 (170.69ms total, max 56.93ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 11930ms; provider 2ms; post-provider 1476ms; unknown 7440.09ms; source agent.prepare 3988.81ms; plugins.metadata.scan 501.1ms
  - warm: total 13691ms; pre-provider 12180ms; provider 1ms; post-provider 1510ms; response true
    - active window: metadata scans 7 (211.16ms total, max 68.34ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 12180ms; provider 1ms; post-provider 1510ms; unknown 7690.09ms; source agent.prepare 3988.81ms; plugins.metadata.scan 501.1ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 11930 ms | 5669 ms | 6261 ms | 2 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261011-052637-56e5b9/kova-agent-cold-warm-message-2c26dd1d-kova-261011-052637-56e5b9/openclaw/timeline.jsonl |
  | warm | 12180 ms | 6135 ms | 6045 ms | 1 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261011-052637-56e5b9/kova-agent-cold-warm-message-2c26dd1d-kova-261011-052637-56e5b9/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `cli.command-startup` | `cli.command-startup` x10 | 10 | 0 | 2589 ms | 661 ms |
  | cold | `agent.startup` | `agent.startup` x9 | 9 | 0 | 2270 ms | 1130 ms |
  | cold | `agent.prepare` | `agent.prepare` x9 | 9 | 0 | 1994 ms | 1012 ms |
  | cold | `plugins.metadata.scan` | `cli.command-startup` x3, `startup` x4 | 7 | 0 | 169 ms | 57 ms |
  | cold | `cli.main.core-imports` | `cli.startup` | 1 | 0 | 20 ms | 20 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 18 ms | 18 ms |
  | warm | `agent.startup` | `agent.startup` x9 | 9 | 0 | 2782 ms | 1711 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x10 | 10 | 0 | 2378 ms | 620 ms |
  | warm | `agent.prepare` | `agent.prepare` x9 | 9 | 0 | 1994 ms | 1045 ms |
  | warm | `plugins.metadata.scan` | `cli.command-startup` x3, `startup` x4 | 7 | 0 | 212 ms | 69 ms |
  | warm | `cli.main.core-imports` | `cli.startup` | 1 | 0 | 22 ms | 22 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 18 ms | 18 ms |

## Artifacts

- markdown-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-deep-profile/kova-261011-052637-56e5b9-diagnostic.md
- json-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-deep-profile/kova-261011-052637-56e5b9-diagnostic.json
- summary-json: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-deep-profile/kova-261011-052637-56e5b9-diagnostic.summary.json
- collector-root gateway-performance#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261011-052637-56e5b9/kova-gateway-performance-man-d48bd949-kova-261011-052637-56e5b9
- collector-root agent-cold-warm-message#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261011-052637-56e5b9/kova-agent-cold-warm-message-2c26dd1d-kova-261011-052637-56e5b9

## Target Cleanup

- Runtime: `kova-local-mv3drvw5-3tg-42a5b79e`
- Result: removed
- Duration: 503ms

