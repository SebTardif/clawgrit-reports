# Kova OpenClaw Runtime Report

> **❌ [FAIL]** — Product CPU interval evidence is incomplete

## Verdict

| Field | Value |
|---|---|
| Verdict | FAIL |
| Reason | Product CPU interval evidence is incomplete |
| Blocking findings | 5 |
| Warnings | 0 |
| Records | 2 (FAIL:2) |

## Proof Completeness

- Completeness: complete: 2
- Required obligations: 120 total, 0 missing, 0 failed
- Categories: command: 102, artifact: 2, cleanup: 2, collector: 2, invariant: 12

## Run

| Field | Value |
|---|---|
| Run ID | `kova-261015-052503-d06c37` |
| Generated | 2026-10-15T05:35:07.090Z |
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
| fail | OpenClaw | gateway-performance/many-bundled-plugins | Product CPU interval evidence is incomplete | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 19 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway peak RSS 2113.5 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2318.6 MB, gateway 2113.5 MB, command-tree 1045.4 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 19 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway-tree peak RSS 2318.6 MB exceeded threshold 1440 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 19 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | warm agent turn took 15727ms, over threshold 15000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1935.2 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | warm provider was fast (0ms), but OpenClaw spent 14216ms before provider work. | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1935.2 |

## Performance Summary

- Resource measurement scope: product
- Resource headline contract: `primary-role-product-scope-v4`

| Scenario | Samples | Status | Health Ready | Gateway RSS | Tracked RSS | CPU | Cold Turn | Warm Turn | Cold Pre-Provider |
|---|---:|---|---:|---:|---:|---:|---:|---:|---:|
| gateway-performance/many-bundled-plugins | 1 | FAIL:1 | 19ms | 2113.5MB | n/a | 302.7% | n/a | n/a | n/a |
| agent-cold-warm-message/mock-openai-provider | 1 | FAIL:1 | n/a | 0MB | n/a | 333.2% | 15571ms | 15727ms | 13746ms |

## Samples

| Sample | Status | Scenario | Upgrade From | Health Ready | Gateway RSS | Tracked RSS | Cold Turn | Warm Turn | Blocker |
|---:|---|---|---|---:|---:|---:|---:|---:|---|
| 1 | FAIL | gateway-performance/many-bundled-plugins |  | 19ms | 2113.5 MB | 2959.9 MB | n/a | n/a | Product CPU interval evidence is incomplete |
| 1 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 2219.2 MB | 15571ms | 15727ms | warm agent turn took 15727ms, over threshold 15000ms |

## Resource Roles

- Measurement scope: product
- Headline contract: `primary-role-product-scope-v4`
- gateway-tree: RSS 2318.6 MB (scenario gateway-performance/many-bundled-plugins); CPU 333.7% (scenario gateway-performance/many-bundled-plugins)
- agent-cli: RSS 306.5 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 390% (scenario agent-cold-warm-message/mock-openai-provider)
- command-tree: RSS 2145.4 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 390% (scenario agent-cold-warm-message/mock-openai-provider)
- gateway: RSS 2113.5 MB (scenario gateway-performance/many-bundled-plugins); CPU 302.7% (scenario gateway-performance/many-bundled-plugins)
- status-cli: RSS 1282.5 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 371.6% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-process: RSS 1935.2 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 333.2% (scenario agent-cold-warm-message/mock-openai-provider)
- uncategorized: RSS 611.8 MB (scenario gateway-performance/many-bundled-plugins); CPU 241% (scenario gateway-performance/many-bundled-plugins)
- model-cli: RSS 532 MB (scenario gateway-performance/many-bundled-plugins); CPU 183.5% (scenario gateway-performance/many-bundled-plugins)

## Selected Sample Details

### gateway-performance sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261015-052503-d06c37/kova-gateway-performance-man-d48bd949-kova-261015-052503-d06c37
Measurements:
- startup: listening 1ms; health 19ms; readiness ready (gateway became healthy within the readiness threshold); gateway running; restarts 4
- health: startup p95 18ms; post-ready p95 3ms; failures 0; final failures 0; slowest startup-sample/cold-start 18ms
- resources: scope product; contract primary-role-product-scope-v4; gateway RSS 2113.5 MB; tracked total 2959.9 MB; max CPU 302.7%; samples 134; roles gateway-tree 2318.6MB/333.7%, gateway 2113.5MB/302.7%, command-tree 1045.4MB/287.3%, status-cli 1045.4MB/287.3%; performance thresholds skipped 6 (instrumented)
- agent: not-run
- Agent turn stats: count 0; p95 n/a; max n/a; pre-provider p95 n/a
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages 0; warm reuse true
- diagnostics: timeline available; slowest span cli.command-startup 1649.12ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 28/28/14
- Violations:
  - Product CPU interval evidence is incomplete
  - gateway peak RSS 2113.5 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2318.6 MB, gateway 2113.5 MB, command-tree 1045.4 MB
  - gateway-tree peak RSS 2318.6 MB exceeded threshold 1440 MB

### agent-cold-warm-message sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261015-052503-d06c37/kova-agent-cold-warm-message-2c26dd1d-kova-261015-052503-d06c37
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1935.2 MB; tracked total 2219.2 MB; max CPU 333.2%; samples 162; roles command-tree 2145.4MB/390%, agent-cli 306.5MB/390%, agent-process 1935.2MB/333.2%, status-cli 1282.5MB/371.6%; performance thresholds skipped 15 (instrumented)
- agent: turn 15727ms; cold/warm 15571ms/15727ms; cold-warm delta 0ms; pre-provider 14216ms; provider 0ms; metadata scans 14 (486.69ms); event-loop n/a; polls 0; cleanup n/a; diagnosis pre-provider-stall; leaks 0
- Agent turn stats: count 2; p95 15719.2ms; max 15727ms; pre-provider p95 14192.5ms
- agent CLI attribution: cold known 8396ms / unattributed 5350ms; warm known 9565ms / unattributed 4651ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span agent.startup 2703.1ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 67/46/8
- Violations:
  - warm agent turn took 15727ms, over threshold 15000ms
  - warm provider was fast (0ms), but OpenClaw spent 14216ms before provider work.
- Agent turns:
  - cold: total 15571ms; pre-provider 13746ms; provider 464ms; post-provider 1361ms; response true
    - active window: metadata scans 7 (234.85ms total, max 83.72ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 13746ms; provider 464ms; post-provider 1361ms; unknown 4773.3ms; source agent.prepare 8327.1ms; plugins.metadata.scan 645.6ms
  - warm: total 15727ms; pre-provider 14216ms; provider 0ms; post-provider 1511ms; response true
    - active window: metadata scans 7 (251.84ms total, max 104.15ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 14216ms; provider 0ms; post-provider 1511ms; unknown 5243.3ms; source agent.prepare 8327.1ms; plugins.metadata.scan 645.6ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 13746 ms | 8396 ms | 5350 ms | 464 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261015-052503-d06c37/kova-agent-cold-warm-message-2c26dd1d-kova-261015-052503-d06c37/openclaw/timeline.jsonl |
  | warm | 14216 ms | 9565 ms | 4651 ms | 0 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261015-052503-d06c37/kova-agent-cold-warm-message-2c26dd1d-kova-261015-052503-d06c37/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 3999 ms | 1198 ms |
  | cold | `agent.startup` | `agent.startup` x9 | 9 | 0 | 3930 ms | 1787 ms |
  | cold | `cli.command-startup` | `cli.command-startup` x10 | 10 | 0 | 3397 ms | 872 ms |
  | cold | `plugins.metadata.scan` | `startup` x4, `cli.command-startup` x3 | 7 | 0 | 234 ms | 84 ms |
  | cold | `cli.main.core-imports` | `cli.startup` | 1 | 0 | 50 ms | 50 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 24 ms | 24 ms |
  | warm | `agent.startup` | `agent.startup` x9 | 9 | 0 | 4815 ms | 2703 ms |
  | warm | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 4332 ms | 1369 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x10 | 10 | 0 | 3168 ms | 920 ms |
  | warm | `plugins.metadata.scan` | `startup` x4, `cli.command-startup` x3 | 7 | 0 | 252 ms | 104 ms |
  | warm | `cli.main.core-imports` | `cli.startup` | 1 | 0 | 34 ms | 34 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 23 ms | 23 ms |

## Artifacts

- markdown-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-deep-profile/kova-261015-052503-d06c37-diagnostic.md
- json-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-deep-profile/kova-261015-052503-d06c37-diagnostic.json
- summary-json: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-deep-profile/kova-261015-052503-d06c37-diagnostic.summary.json
- collector-root gateway-performance#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261015-052503-d06c37/kova-gateway-performance-man-d48bd949-kova-261015-052503-d06c37
- collector-root agent-cold-warm-message#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261015-052503-d06c37/kova-agent-cold-warm-message-2c26dd1d-kova-261015-052503-d06c37

## Target Cleanup

- Runtime: `kova-local-mv93ha53-3tk-d64baa59`
- Result: removed
- Duration: 599ms

