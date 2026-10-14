# Kova OpenClaw Runtime Report

> **❌ [FAIL]** — Product CPU interval evidence is incomplete

## Verdict

| Field | Value |
|---|---|
| Verdict | FAIL |
| Reason | Product CPU interval evidence is incomplete |
| Blocking findings | 6 |
| Warnings | 0 |
| Records | 2 (FAIL:2) |

## Proof Completeness

- Completeness: complete: 2
- Required obligations: 120 total, 0 missing, 0 failed
- Categories: command: 102, artifact: 2, cleanup: 2, collector: 2, invariant: 12

## Run

| Field | Value |
|---|---|
| Run ID | `kova-261014-052433-733d9e` |
| Generated | 2026-10-14T05:36:10.339Z |
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
| fail | OpenClaw | gateway-performance/many-bundled-plugins | Product CPU interval evidence is incomplete | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 109 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway peak RSS 2043.5 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2302.1 MB, gateway 2043.5 MB, command-tree 1127.2 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 109 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway-tree peak RSS 2302.1 MB exceeded threshold 1440 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 109 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | agent-cli max CPU interval \[275.6%, 349.5%\] crosses threshold 300%; CPU measurement is inconclusive | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1781.7 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | warm agent turn took 19223ms, over threshold 15000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1781.7 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | warm provider was fast (1ms), but OpenClaw spent 17429ms before provider work. | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1781.7 |

## Performance Summary

- Resource measurement scope: product
- Resource headline contract: `primary-role-product-scope-v4`

| Scenario | Samples | Status | Health Ready | Gateway RSS | Tracked RSS | CPU | Cold Turn | Warm Turn | Cold Pre-Provider |
|---|---:|---|---:|---:|---:|---:|---:|---:|---:|
| gateway-performance/many-bundled-plugins | 1 | FAIL:1 | 109ms | 2043.5MB | n/a | 312.3% | n/a | n/a | n/a |
| agent-cold-warm-message/mock-openai-provider | 1 | FAIL:1 | n/a | 0MB | n/a | 297% | 19061ms | 19223ms | 15662ms |

## Samples

| Sample | Status | Scenario | Upgrade From | Health Ready | Gateway RSS | Tracked RSS | Cold Turn | Warm Turn | Blocker |
|---:|---|---|---|---:|---:|---:|---:|---:|---|
| 1 | FAIL | gateway-performance/many-bundled-plugins |  | 109ms | 2043.5 MB | 3007.5 MB | n/a | n/a | Product CPU interval evidence is incomplete |
| 1 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 2064.8 MB | 19061ms | 19223ms | agent-cli max CPU interval \[275.6%, 349.5%\] crosses threshold 300%; CPU measurement is inconclusive |

## Resource Roles

- Measurement scope: product
- Headline contract: `primary-role-product-scope-v4`
- gateway-tree: RSS 2302.1 MB (scenario gateway-performance/many-bundled-plugins); CPU 357.5% (scenario gateway-performance/many-bundled-plugins)
- gateway: RSS 2043.5 MB (scenario gateway-performance/many-bundled-plugins); CPU 312.3% (scenario gateway-performance/many-bundled-plugins)
- command-tree: RSS 1990.9 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 353% (scenario agent-cold-warm-message/mock-openai-provider)
- status-cli: RSS 1211.9 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 353% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-process: RSS 1781.7 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 297% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-cli: RSS 301.1 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 349.5% (scenario agent-cold-warm-message/mock-openai-provider)
- uncategorized: RSS 588.7 MB (scenario gateway-performance/many-bundled-plugins); CPU 232.1% (scenario gateway-performance/many-bundled-plugins)
- model-cli: RSS 520.8 MB (scenario gateway-performance/many-bundled-plugins); CPU 201.2% (scenario gateway-performance/many-bundled-plugins)

## Selected Sample Details

### gateway-performance sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261014-052433-733d9e/kova-gateway-performance-man-d48bd949-kova-261014-052433-733d9e
Measurements:
- startup: listening 1ms; health 109ms; readiness ready (gateway became healthy within the readiness threshold); gateway running; restarts 4
- health: startup p95 108ms; post-ready p95 5ms; failures 0; final failures 0; slowest startup-sample/cold-start 108ms
- resources: scope product; contract primary-role-product-scope-v4; gateway RSS 2043.5 MB; tracked total 3007.5 MB; max CPU 312.3%; samples 163; roles gateway-tree 2302.1MB/357.5%, gateway 2043.5MB/312.3%, command-tree 1127.2MB/308.4%, status-cli 1127.2MB/308.4%; performance thresholds skipped 8 (instrumented)
- agent: not-run
- Agent turn stats: count 0; p95 n/a; max n/a; pre-provider p95 n/a
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages 0; warm reuse true
- diagnostics: timeline available; slowest span post-ready.maintenance 2621.54ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 28/28/14
- Violations:
  - Product CPU interval evidence is incomplete
  - gateway peak RSS 2043.5 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2302.1 MB, gateway 2043.5 MB, command-tree 1127.2 MB
  - gateway-tree peak RSS 2302.1 MB exceeded threshold 1440 MB

### agent-cold-warm-message sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261014-052433-733d9e/kova-agent-cold-warm-message-2c26dd1d-kova-261014-052433-733d9e
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1781.7 MB; tracked total 2064.8 MB; max CPU 297%; samples 199; roles command-tree 1990.9MB/353%, agent-process 1781.7MB/297%, status-cli 1211.9MB/353%, agent-cli 301.1MB/349.5%; performance thresholds skipped 15 (instrumented)
- agent: turn 19223ms; cold/warm 19061ms/19223ms; cold-warm delta 0ms; pre-provider 17429ms; provider 1ms; metadata scans 14 (485.05ms); event-loop n/a; polls 0; cleanup n/a; diagnosis pre-provider-stall; leaks 0
- Agent turn stats: count 2; p95 19214.9ms; max 19223ms; pre-provider p95 17340.65ms
- agent CLI attribution: cold known 9933ms / unattributed 5729ms; warm known 11477ms / unattributed 5952ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span agent.startup 3395.15ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 62/41/10
- Violations:
  - agent-cli max CPU interval \[275.6%, 349.5%\] crosses threshold 300%; CPU measurement is inconclusive
  - warm agent turn took 19223ms, over threshold 15000ms
  - warm provider was fast (1ms), but OpenClaw spent 17429ms before provider work.
- Agent turns:
  - cold: total 19061ms; pre-provider 15662ms; provider 1582ms; post-provider 1817ms; response true
    - active window: metadata scans 7 (233ms total, max 73.15ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 15662ms; provider 1582ms; post-provider 1817ms; unknown 4308ms; source agent.prepare 10698.01ms; plugins.metadata.scan 655.99ms
  - warm: total 19223ms; pre-provider 17429ms; provider 1ms; post-provider 1793ms; response true
    - active window: metadata scans 7 (252.05ms total, max 95.23ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 17429ms; provider 1ms; post-provider 1793ms; unknown 6075ms; source agent.prepare 10698.01ms; plugins.metadata.scan 655.99ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 15662 ms | 9933 ms | 5729 ms | 1582 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261014-052433-733d9e/kova-agent-cold-warm-message-2c26dd1d-kova-261014-052433-733d9e/openclaw/timeline.jsonl |
  | warm | 17429 ms | 11477 ms | 5952 ms | 1 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261014-052433-733d9e/kova-agent-cold-warm-message-2c26dd1d-kova-261014-052433-733d9e/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `agent.startup` | `agent.startup` x9 | 9 | 0 | 4908 ms | 2248 ms |
  | cold | `agent.prepare` | `agent.prepare` x12 | 12 | 0 | 4621 ms | 1703 ms |
  | cold | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 3498 ms | 917 ms |
  | cold | `plugins.metadata.scan` | `cli.command-startup` x3, `startup` x4 | 7 | 0 | 231 ms | 73 ms |
  | cold | `cli.main.core-imports` | `cli.startup` | 1 | 0 | 45 ms | 45 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 24 ms | 24 ms |
  | warm | `agent.startup` | `agent.startup` x9 | 9 | 0 | 5965 ms | 3395 ms |
  | warm | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 5118 ms | 1682 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 3571 ms | 964 ms |
  | warm | `plugins.metadata.scan` | `startup` x4, `cli.command-startup` x3 | 7 | 0 | 252 ms | 95 ms |
  | warm | `cli.main.core-imports` | `cli.startup` | 1 | 0 | 43 ms | 43 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 26 ms | 26 ms |

## Artifacts

- markdown-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-deep-profile/kova-261014-052433-733d9e-diagnostic.md
- json-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-deep-profile/kova-261014-052433-733d9e-diagnostic.json
- summary-json: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-deep-profile/kova-261014-052433-733d9e-diagnostic.summary.json
- collector-root gateway-performance#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261014-052433-733d9e/kova-gateway-performance-man-d48bd949-kova-261014-052433-733d9e
- collector-root agent-cold-warm-message#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261014-052433-733d9e/kova-agent-cold-warm-message-2c26dd1d-kova-261014-052433-733d9e

## Target Cleanup

- Runtime: `kova-local-mv7o0sts-3to-3ee0bc26`
- Result: removed
- Duration: 838ms

