# Kova OpenClaw Runtime Report

> **❌ [FAIL]** — gateway peak RSS 1705.8 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2021.9 MB, gateway 1705.8 MB, command-tree 1264.8 MB

## Verdict

| Field | Value |
|---|---|
| Verdict | FAIL |
| Reason | gateway peak RSS 1705.8 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2021.9 MB, gateway 1705.8 MB, command-tree 1264.8 MB |
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
| Run ID | `kova-261012-053446-3f8d65` |
| Generated | 2026-10-12T05:45:10.111Z |
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
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway peak RSS 1705.8 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2021.9 MB, gateway 1705.8 MB, command-tree 1264.8 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 239 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway-tree peak RSS 2021.9 MB exceeded threshold 1440 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 239 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | warm agent turn took 17726ms, over threshold 15000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1937.6 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | cold provider was fast (836ms), but OpenClaw spent 18290ms before provider work. | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1937.6 |

## Performance Summary

- Resource measurement scope: product
- Resource headline contract: `primary-role-product-scope-v4`

| Scenario | Samples | Status | Health Ready | Gateway RSS | Tracked RSS | CPU | Cold Turn | Warm Turn | Cold Pre-Provider |
|---|---:|---|---:|---:|---:|---:|---:|---:|---:|
| gateway-performance/many-bundled-plugins | 1 | FAIL:1 | 239ms | 1705.8MB | n/a | 299.5% | n/a | n/a | n/a |
| agent-cold-warm-message/mock-openai-provider | 1 | FAIL:1 | n/a | 0MB | n/a | 323.4% | 21097ms | 17726ms | 18290ms |

## Samples

| Sample | Status | Scenario | Upgrade From | Health Ready | Gateway RSS | Tracked RSS | Cold Turn | Warm Turn | Blocker |
|---:|---|---|---|---:|---:|---:|---:|---:|---|
| 1 | FAIL | gateway-performance/many-bundled-plugins |  | 239ms | 1705.8 MB | 3113 MB | n/a | n/a | gateway peak RSS 1705.8 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2021.9 MB, gateway 1705.8 MB, command-tree 1264.8 MB |
| 1 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 2119.3 MB | 21097ms | 17726ms | warm agent turn took 17726ms, over threshold 15000ms |

## Resource Roles

- Measurement scope: product
- Headline contract: `primary-role-product-scope-v4`
- command-tree: RSS 2046.3 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 411.2% (scenario agent-cold-warm-message/mock-openai-provider)
- gateway-tree: RSS 2021.9 MB (scenario gateway-performance/many-bundled-plugins); CPU 323.4% (scenario gateway-performance/many-bundled-plugins)
- status-cli: RSS 1358.7 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 411.2% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-process: RSS 1937.6 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 323.4% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-cli: RSS 256.7 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 359.8% (scenario agent-cold-warm-message/mock-openai-provider)
- gateway: RSS 1705.8 MB (scenario gateway-performance/many-bundled-plugins); CPU 299.5% (scenario gateway-performance/many-bundled-plugins)
- uncategorized: RSS 849.3 MB (scenario gateway-performance/many-bundled-plugins); CPU 243.9% (scenario gateway-performance/many-bundled-plugins)
- model-cli: RSS 435.3 MB (scenario gateway-performance/many-bundled-plugins); CPU 198.7% (scenario gateway-performance/many-bundled-plugins)

## Selected Sample Details

### gateway-performance sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261012-053446-3f8d65/kova-gateway-performance-man-d48bd949-kova-261012-053446-3f8d65
Measurements:
- startup: listening 0ms; health 239ms; readiness ready (gateway became healthy within the readiness threshold); gateway running; restarts 4
- health: startup p95 239ms; post-ready p95 3ms; failures 0; final failures 0; slowest startup-sample/warm-restart 239ms
- resources: scope product; contract primary-role-product-scope-v4; gateway RSS 1705.8 MB; tracked total 3113 MB; max CPU 299.5%; samples 151; roles gateway-tree 2021.9MB/323.4%, gateway 1705.8MB/299.5%, command-tree 1264.8MB/298.8%, status-cli 1264.8MB/272.3%; performance thresholds skipped 10 (instrumented)
- agent: not-run
- Agent turn stats: count 0; p95 n/a; max n/a; pre-provider p95 n/a
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages 0; warm reuse true
- diagnostics: timeline available; slowest span cli.command-startup 1790.79ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 19/19/13
- Violations:
  - gateway peak RSS 1705.8 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2021.9 MB, gateway 1705.8 MB, command-tree 1264.8 MB
  - gateway-tree peak RSS 2021.9 MB exceeded threshold 1440 MB

### agent-cold-warm-message sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261012-053446-3f8d65/kova-agent-cold-warm-message-2c26dd1d-kova-261012-053446-3f8d65
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1937.6 MB; tracked total 2119.3 MB; max CPU 323.4%; samples 191; roles command-tree 2046.3MB/411.2%, agent-process 1937.6MB/323.4%, status-cli 1358.7MB/411.2%, agent-cli 256.7MB/359.8%; performance thresholds skipped 15 (instrumented)
- agent: turn 21097ms; cold/warm 21097ms/17726ms; cold-warm delta 3371ms; pre-provider 18290ms; provider 836ms; metadata scans 14 (622.49ms); event-loop n/a; polls 0; cleanup n/a; diagnosis pre-provider-stall; leaks 0
- Agent turn stats: count 2; p95 20928.45ms; max 21097ms; pre-provider p95 18190.5ms
- agent CLI attribution: cold known 10298ms / unattributed 7992ms; warm known 8755ms / unattributed 7545ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span agent.startup 2892.19ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 67/49/9
- Violations:
  - warm agent turn took 17726ms, over threshold 15000ms
  - cold provider was fast (836ms), but OpenClaw spent 18290ms before provider work.
- Agent turns:
  - cold: total 21097ms; pre-provider 18290ms; provider 836ms; post-provider 1971ms; response true
    - active window: metadata scans 7 (392.34ms total, max 186.66ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 18290ms; provider 836ms; post-provider 1971ms; unknown 6609.26ms; source agent.prepare 10918.23ms; plugins.metadata.scan 762.51ms
  - warm: total 17726ms; pre-provider 16300ms; provider 1ms; post-provider 1425ms; response true
    - active window: metadata scans 7 (230.15ms total, max 84.94ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 16300ms; provider 1ms; post-provider 1425ms; unknown 4619.26ms; source agent.prepare 10918.23ms; plugins.metadata.scan 762.51ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 18290 ms | 10298 ms | 7992 ms | 836 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261012-053446-3f8d65/kova-agent-cold-warm-message-2c26dd1d-kova-261012-053446-3f8d65/openclaw/timeline.jsonl |
  | warm | 16300 ms | 8755 ms | 7545 ms | 1 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261012-053446-3f8d65/kova-agent-cold-warm-message-2c26dd1d-kova-261012-053446-3f8d65/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 7299 ms | 2146 ms |
  | cold | `agent.startup` | `agent.startup` x9 | 9 | 0 | 3490 ms | 1697 ms |
  | cold | `cli.command-startup` | `cli.command-startup` x10 | 10 | 0 | 3243 ms | 826 ms |
  | cold | `plugins.metadata.scan` | `cli.command-startup` x3, `startup` x4 | 7 | 0 | 392 ms | 186 ms |
  | cold | `cli.main.core-imports` | `cli.startup` | 1 | 0 | 28 ms | 28 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 22 ms | 22 ms |
  | warm | `agent.startup` | `agent.startup` x9 | 9 | 0 | 5022 ms | 2892 ms |
  | warm | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 3623 ms | 1249 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x10 | 10 | 0 | 2836 ms | 752 ms |
  | warm | `plugins.metadata.scan` | `cli.command-startup` x3, `startup` x4 | 7 | 0 | 231 ms | 85 ms |
  | warm | `cli.main.register-primary` | `cli.startup` | 1 | 0 | 33 ms | 33 ms |
  | warm | `cli.main.core-imports` | `cli.startup` | 1 | 0 | 30 ms | 30 ms |

## Artifacts

- markdown-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-deep-profile/kova-261012-053446-3f8d65-diagnostic.md
- json-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-deep-profile/kova-261012-053446-3f8d65-diagnostic.json
- summary-json: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-deep-profile/kova-261012-053446-3f8d65-diagnostic.summary.json
- collector-root gateway-performance#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261012-053446-3f8d65/kova-gateway-performance-man-d48bd949-kova-261012-053446-3f8d65
- collector-root agent-cold-warm-message#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-deep-profile/artifacts/kova-261012-053446-3f8d65/kova-agent-cold-warm-message-2c26dd1d-kova-261012-053446-3f8d65

## Target Cleanup

- Runtime: `kova-local-mv4ti8h0-3ud-19f1869b`
- Result: removed
- Duration: 666ms

