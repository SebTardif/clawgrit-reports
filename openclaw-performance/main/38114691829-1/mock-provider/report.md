# Kova OpenClaw Runtime Report

> **❌ [FAIL]** — gateway peak RSS 1710.2 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2008.8 MB, gateway 1710.2 MB, command-tree 815.6 MB

## Verdict

| Field | Value |
|---|---|
| Verdict | FAIL |
| Reason | gateway peak RSS 1710.2 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2008.8 MB, gateway 1710.2 MB, command-tree 815.6 MB |
| Blocking findings | 13 |
| Warnings | 0 |
| Records | 6 (FAIL:6) |

## Proof Completeness

- Completeness: complete: 6
- Required obligations: 358 total, 0 missing, 0 failed
- Categories: command: 304, artifact: 6, cleanup: 6, collector: 6, invariant: 36

## Run

| Field | Value |
|---|---|
| Run ID | `kova-261011-052701-1adb77` |
| Generated | 2026-10-11T05:46:50.309Z |
| Mode | execution |
| Target | `local-build:/home/runner/_work/openclaw/openclaw` |
| Platform | linux 6.6.141 (x64) · v24.19.0 |
| Repeat / parallel | 3 / 1 |
| Auth | mock (openai) |
| Network frontage | port |

## Coverage

| Field | Value |
|---|---:|
| Records | 6 |
| Scenarios | 2 |
| States | 2 |
| FAIL | 6 |

## Findings

| Severity | Area | Scenario | Finding | Evidence |
|---|---|---|---|---|
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway peak RSS 1710.2 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2008.8 MB, gateway 1710.2 MB, command-tree 815.6 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 17 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway-tree peak RSS 2008.8 MB exceeded threshold 1440 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 17 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway peak RSS 1678.4 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 1978.7 MB, gateway 1678.4 MB, command-tree 1017.4 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 55 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway-tree peak RSS 1978.7 MB exceeded threshold 1440 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 55 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | status-cli peak RSS 1017.4 MB exceeded threshold 900 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 55 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway peak RSS 1791.6 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2091.7 MB, gateway 1791.6 MB, command-tree 815.1 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 43 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway-tree peak RSS 2091.7 MB exceeded threshold 1440 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 43 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | agent-process peak RSS 1308.5 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1410 MB, agent-process 1308.5 MB, status-cli 805.8 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1308.5 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | command-tree peak RSS 1410 MB exceeded threshold 1400 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1308.5 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | agent-process peak RSS 1386.4 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1488 MB, agent-process 1386.4 MB, status-cli 736.1 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1386.4 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | command-tree peak RSS 1488 MB exceeded threshold 1400 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1386.4 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | agent-process peak RSS 1352.1 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1453.9 MB, agent-process 1352.1 MB, status-cli 744.7 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1352.1 |
| info | Kova | report | 1 additional finding(s) omitted from Markdown | see summary JSON |

## Performance Summary

- Resource measurement scope: product
- Resource headline contract: `primary-role-product-scope-v4`

| Scenario | Samples | Status | Health Ready | Gateway RSS | Tracked RSS | CPU | Cold Turn | Warm Turn | Cold Pre-Provider |
|---|---:|---|---:|---:|---:|---:|---:|---:|---:|
| gateway-performance/many-bundled-plugins | 3 | FAIL:3 | 43ms | 1710.2MB | n/a | 226.9% | n/a | n/a | n/a |
| agent-cold-warm-message/mock-openai-provider | 3 | FAIL:3 | n/a | 0MB | n/a | 190.8% | 6474ms | 6682ms | 6226ms |

## Samples

| Sample | Status | Scenario | Upgrade From | Health Ready | Gateway RSS | Tracked RSS | Cold Turn | Warm Turn | Blocker |
|---:|---|---|---|---:|---:|---:|---:|---:|---|
| 1 | FAIL | gateway-performance/many-bundled-plugins |  | 17ms | 1710.2 MB | 2649.3 MB | n/a | n/a | gateway peak RSS 1710.2 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2008.8 MB, gateway 1710.2 MB, command-tree 815.6 MB |
| 2 | FAIL | gateway-performance/many-bundled-plugins |  | 55ms | 1678.4 MB | 2865.6 MB | n/a | n/a | gateway peak RSS 1678.4 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 1978.7 MB, gateway 1678.4 MB, command-tree 1017.4 MB |
| 3 | FAIL | gateway-performance/many-bundled-plugins |  | 43ms | 1791.6 MB | 2847.2 MB | n/a | n/a | gateway peak RSS 1791.6 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2091.7 MB, gateway 1791.6 MB, command-tree 815.1 MB |
| 1 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1481.2 MB | 6474ms | 6578ms | agent-process peak RSS 1308.5 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1410 MB, agent-process 1308.5 MB, status-cli 805.8 MB |
| 2 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1559.7 MB | 7272ms | 6752ms | agent-process peak RSS 1386.4 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1488 MB, agent-process 1386.4 MB, status-cli 736.1 MB |
| 3 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1525.7 MB | 6314ms | 6682ms | agent-process peak RSS 1352.1 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1453.9 MB, agent-process 1352.1 MB, status-cli 744.7 MB |

## Resource Roles

- Measurement scope: product
- Headline contract: `primary-role-product-scope-v4`
- gateway-tree: RSS 2091.7 MB (scenario gateway-performance/many-bundled-plugins); CPU 269.4% (scenario gateway-performance/many-bundled-plugins)
- gateway: RSS 1791.6 MB (scenario gateway-performance/many-bundled-plugins); CPU 232.4% (scenario gateway-performance/many-bundled-plugins)
- command-tree: RSS 1488 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 211.3% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-process: RSS 1386.4 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 201.4% (scenario agent-cold-warm-message/mock-openai-provider)
- status-cli: RSS 1017.4 MB (scenario gateway-performance/many-bundled-plugins); CPU 170.9% (scenario agent-cold-warm-message/mock-openai-provider)
- uncategorized: RSS 747.1 MB (scenario gateway-performance/many-bundled-plugins); CPU 135.2% (scenario gateway-performance/many-bundled-plugins)
- agent-cli: RSS 202.6 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 138.7% (scenario agent-cold-warm-message/mock-openai-provider)
- mock-provider: RSS 72.7 MB (scenario gateway-performance/many-bundled-plugins); CPU 8% (scenario gateway-performance/many-bundled-plugins)

## Selected Sample Details

### gateway-performance sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261011-052701-1adb77/kova-gateway-performance-man-005107f3-kova-261011-052701-1adb77
Measurements:
- startup: listening 1ms; health 17ms; readiness ready (gateway became healthy within the readiness threshold); gateway running; restarts 4
- health: startup p95 16ms; post-ready p95 2ms; failures 0; final failures 0; slowest startup-sample/cold-start 16ms
- resources: scope product; contract primary-role-product-scope-v4; gateway RSS 1710.2 MB; tracked total 2649.3 MB; max CPU 226.9%; samples 37; roles gateway-tree 2008.8MB/269.4%, gateway 1710.2MB/226.9%, command-tree 815.6MB/147.1%, status-cli 815.6MB/147.1%
- agent: not-run
- Agent turn stats: count 0; p95 n/a; max n/a; pre-provider p95 n/a
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages 0; warm reuse true
- diagnostics: timeline available; slowest span sidecars.subagent-recovery 1454.22ms; embedded traces 0; liveness warnings 0; open spans 2 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - gateway peak RSS 1710.2 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2008.8 MB, gateway 1710.2 MB, command-tree 815.6 MB
  - gateway-tree peak RSS 2008.8 MB exceeded threshold 1440 MB

### gateway-performance sample 2

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261011-052701-1adb77/kova-gateway-performance-man-1e8be6a8-kova-261011-052701-1adb77
Measurements:
- startup: listening 0ms; health 55ms; readiness ready (gateway became healthy within the readiness threshold); gateway running; restarts 4
- health: startup p95 55ms; post-ready p95 2ms; failures 0; final failures 0; slowest startup-sample/cold-start 55ms
- resources: scope product; contract primary-role-product-scope-v4; gateway RSS 1678.4 MB; tracked total 2865.6 MB; max CPU 225.8%; samples 39; roles gateway-tree 1978.7MB/263.5%, gateway 1678.4MB/225.8%, command-tree 1017.4MB/156.4%, status-cli 1017.4MB/156.4%
- agent: not-run
- Agent turn stats: count 0; p95 n/a; max n/a; pre-provider p95 n/a
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages 0; warm reuse true
- diagnostics: timeline available; slowest span sidecars.subagent-recovery 1287.31ms; embedded traces 0; liveness warnings 0; open spans 1 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - gateway peak RSS 1678.4 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 1978.7 MB, gateway 1678.4 MB, command-tree 1017.4 MB
  - gateway-tree peak RSS 1978.7 MB exceeded threshold 1440 MB
  - status-cli peak RSS 1017.4 MB exceeded threshold 900 MB

### gateway-performance sample 3

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261011-052701-1adb77/kova-gateway-performance-man-958fde53-kova-261011-052701-1adb77
Measurements:
- startup: listening 1ms; health 43ms; readiness ready (gateway became healthy within the readiness threshold); gateway running; restarts 5
- health: startup p95 42ms; post-ready p95 2ms; failures 0; final failures 0; slowest startup-sample/warm-restart 42ms
- resources: scope product; contract primary-role-product-scope-v4; gateway RSS 1791.6 MB; tracked total 2847.2 MB; max CPU 232.4%; samples 38; roles gateway-tree 2091.7MB/262.6%, gateway 1791.6MB/232.4%, command-tree 815.1MB/149.6%, status-cli 815.1MB/149.6%
- agent: not-run
- Agent turn stats: count 0; p95 n/a; max n/a; pre-provider p95 n/a
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages 0; warm reuse true
- diagnostics: timeline available; slowest span sidecars.subagent-recovery 1382.38ms; embedded traces 0; liveness warnings 0; open spans 2 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - gateway peak RSS 1791.6 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2091.7 MB, gateway 1791.6 MB, command-tree 815.1 MB
  - gateway-tree peak RSS 2091.7 MB exceeded threshold 1440 MB

### agent-cold-warm-message sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261011-052701-1adb77/kova-agent-cold-warm-message-8e2a29af-kova-261011-052701-1adb77
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1308.5 MB; tracked total 1481.2 MB; max CPU 201.4%; samples 23; roles command-tree 1410MB/211.3%, agent-process 1308.5MB/201.4%, status-cli 805.8MB/166%, agent-cli 202.1MB/128.8%
- agent: turn 6578ms; cold/warm 6474ms/6578ms; cold-warm delta 0ms; pre-provider 6328ms; provider 0ms; metadata scans 8 (236.99ms); event-loop n/a; polls 0; cleanup n/a; diagnosis agent-latency-attributed; leaks 0
- Agent turn stats: count 2; p95 6572.8ms; max 6578ms; pre-provider p95 6322.9ms
- agent CLI attribution: cold known 2919ms / unattributed 3307ms; warm known 3262ms / unattributed 3066ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span agent.startup 978.74ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1308.5 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1410 MB, agent-process 1308.5 MB, status-cli 805.8 MB
  - command-tree peak RSS 1410 MB exceeded threshold 1400 MB
- Agent turns:
  - cold: total 6474ms; pre-provider 6226ms; provider 2ms; post-provider 246ms; response true
    - active window: metadata scans 4 (108.77ms total, max 55.43ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 6226ms; provider 2ms; post-provider 246ms; unknown 3956.32ms; source agent.prepare 1921.44ms; plugins.metadata.scan 348.24ms
  - warm: total 6578ms; pre-provider 6328ms; provider 0ms; post-provider 250ms; response true
    - active window: metadata scans 4 (128.22ms total, max 76.82ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 6328ms; provider 0ms; post-provider 250ms; unknown 4058.32ms; source agent.prepare 1921.44ms; plugins.metadata.scan 348.24ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 6226 ms | 2919 ms | 3307 ms | 2 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261011-052701-1adb77/kova-agent-cold-warm-message-8e2a29af-kova-261011-052701-1adb77/openclaw/timeline.jsonl |
  | warm | 6328 ms | 3262 ms | 3066 ms | 0 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261011-052701-1adb77/kova-agent-cold-warm-message-8e2a29af-kova-261011-052701-1adb77/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 1873 ms | 503 ms |
  | cold | `agent.prepare` | `agent.prepare` x9 | 9 | 0 | 970 ms | 594 ms |
  | cold | `agent.startup` | `agent.startup` x8 | 8 | 0 | 944 ms | 569 ms |
  | cold | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 108 ms | 56 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 16 ms | 16 ms |
  | cold | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 8 ms | 3 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x10 | 10 | 0 | 1784 ms | 512 ms |
  | warm | `agent.startup` | `agent.startup` x9 | 9 | 0 | 1324 ms | 979 ms |
  | warm | `agent.prepare` | `agent.prepare` x9 | 9 | 0 | 952 ms | 600 ms |
  | warm | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 129 ms | 77 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 17 ms | 17 ms |
  | warm | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 12 ms | 6 ms |

### agent-cold-warm-message sample 2

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261011-052701-1adb77/kova-agent-cold-warm-message-2ab680e0-kova-261011-052701-1adb77
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1386.4 MB; tracked total 1559.7 MB; max CPU 180%; samples 25; roles command-tree 1488MB/190.1%, agent-process 1386.4MB/180%, status-cli 736.1MB/165.2%, agent-cli 136.2MB/129.5%
- agent: turn 7272ms; cold/warm 7272ms/6752ms; cold-warm delta 520ms; pre-provider 7005ms; provider 2ms; metadata scans 8 (245.09ms); event-loop n/a; polls 0; cleanup n/a; diagnosis agent-latency-attributed; leaks 0
- Agent turn stats: count 2; p95 7246ms; max 7272ms; pre-provider p95 6980.5ms
- agent CLI attribution: cold known 3299ms / unattributed 3706ms; warm known 3279ms / unattributed 3236ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span agent.startup 1046.79ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1386.4 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1488 MB, agent-process 1386.4 MB, status-cli 736.1 MB
  - command-tree peak RSS 1488 MB exceeded threshold 1400 MB
- Agent turns:
  - cold: total 7272ms; pre-provider 7005ms; provider 2ms; post-provider 265ms; response true
    - active window: metadata scans 4 (136.24ms total, max 78.43ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7005ms; provider 2ms; post-provider 265ms; unknown 4647.03ms; source agent.prepare 1990.05ms; plugins.metadata.scan 367.92ms
  - warm: total 6752ms; pre-provider 6515ms; provider 0ms; post-provider 237ms; response true
    - active window: metadata scans 4 (108.85ms total, max 55.14ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 6515ms; provider 0ms; post-provider 237ms; unknown 4157.03ms; source agent.prepare 1990.05ms; plugins.metadata.scan 367.92ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 7005 ms | 3299 ms | 3706 ms | 2 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261011-052701-1adb77/kova-agent-cold-warm-message-2ab680e0-kova-261011-052701-1adb77/openclaw/timeline.jsonl |
  | warm | 6515 ms | 3279 ms | 3236 ms | 0 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261011-052701-1adb77/kova-agent-cold-warm-message-2ab680e0-kova-261011-052701-1adb77/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 2403 ms | 675 ms |
  | cold | `agent.startup` | `agent.startup` x8 | 8 | 0 | 1009 ms | 628 ms |
  | cold | `agent.prepare` | `agent.prepare` x10 | 10 | 0 | 1000 ms | 611 ms |
  | cold | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 137 ms | 79 ms |
  | cold | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 18 ms | 11 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 17 ms | 17 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 1744 ms | 506 ms |
  | warm | `agent.startup` | `agent.startup` x8 | 8 | 0 | 1343 ms | 1047 ms |
  | warm | `agent.prepare` | `agent.prepare` x9 | 9 | 0 | 990 ms | 621 ms |
  | warm | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 109 ms | 55 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 16 ms | 16 ms |
  | warm | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 6 ms | 2 ms |

### agent-cold-warm-message sample 3

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261011-052701-1adb77/kova-agent-cold-warm-message-67b331a3-kova-261011-052701-1adb77
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1352.1 MB; tracked total 1525.7 MB; max CPU 190.8%; samples 23; roles command-tree 1453.9MB/201%, agent-process 1352.1MB/190.8%, status-cli 744.7MB/170.9%, agent-cli 202.6MB/138.7%
- agent: turn 6682ms; cold/warm 6314ms/6682ms; cold-warm delta 0ms; pre-provider 6434ms; provider 1ms; metadata scans 8 (227.66ms); event-loop n/a; polls 0; cleanup n/a; diagnosis agent-latency-attributed; leaks 0
- Agent turn stats: count 2; p95 6663.6ms; max 6682ms; pre-provider p95 6415.75ms
- agent CLI attribution: cold known 2810ms / unattributed 3259ms; warm known 3235ms / unattributed 3199ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span agent.startup 997.5ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1352.1 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1453.9 MB, agent-process 1352.1 MB, status-cli 744.7 MB
  - command-tree peak RSS 1453.9 MB exceeded threshold 1400 MB
- Agent turns:
  - cold: total 6314ms; pre-provider 6069ms; provider 2ms; post-provider 243ms; response true
    - active window: metadata scans 4 (107.18ms total, max 54.32ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 6069ms; provider 2ms; post-provider 243ms; unknown 3786.22ms; source agent.prepare 1943.67ms; plugins.metadata.scan 339.11ms
  - warm: total 6682ms; pre-provider 6434ms; provider 1ms; post-provider 247ms; response true
    - active window: metadata scans 4 (120.48ms total, max 74.37ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 6434ms; provider 1ms; post-provider 247ms; unknown 4151.22ms; source agent.prepare 1943.67ms; plugins.metadata.scan 339.11ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 6069 ms | 2810 ms | 3259 ms | 2 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261011-052701-1adb77/kova-agent-cold-warm-message-67b331a3-kova-261011-052701-1adb77/openclaw/timeline.jsonl |
  | warm | 6434 ms | 3235 ms | 3199 ms | 1 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261011-052701-1adb77/kova-agent-cold-warm-message-67b331a3-kova-261011-052701-1adb77/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 1798 ms | 504 ms |
  | cold | `agent.prepare` | `agent.prepare` x9 | 9 | 0 | 980 ms | 603 ms |
  | cold | `agent.startup` | `agent.startup` x8 | 8 | 0 | 862 ms | 562 ms |
  | cold | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 109 ms | 55 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 16 ms | 16 ms |
  | cold | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 7 ms | 3 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x8 | 8 | 0 | 1724 ms | 497 ms |
  | warm | `agent.startup` | `agent.startup` x8 | 8 | 0 | 1317 ms | 998 ms |
  | warm | `agent.prepare` | `agent.prepare` x9 | 9 | 0 | 964 ms | 599 ms |
  | warm | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 120 ms | 74 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 17 ms | 17 ms |
  | warm | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 11 ms | 7 ms |

## Artifacts

- markdown-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-provider/kova-261011-052701-1adb77-diagnostic.md
- json-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-provider/kova-261011-052701-1adb77-diagnostic.json
- summary-json: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-provider/kova-261011-052701-1adb77-diagnostic.summary.json
- collector-root gateway-performance#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261011-052701-1adb77/kova-gateway-performance-man-005107f3-kova-261011-052701-1adb77
- collector-root gateway-performance#2: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261011-052701-1adb77/kova-gateway-performance-man-1e8be6a8-kova-261011-052701-1adb77
- collector-root gateway-performance#3: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261011-052701-1adb77/kova-gateway-performance-man-958fde53-kova-261011-052701-1adb77
- collector-root agent-cold-warm-message#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261011-052701-1adb77/kova-agent-cold-warm-message-8e2a29af-kova-261011-052701-1adb77
- collector-root agent-cold-warm-message#2: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261011-052701-1adb77/kova-agent-cold-warm-message-2ab680e0-kova-261011-052701-1adb77
- collector-root agent-cold-warm-message#3: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261011-052701-1adb77/kova-agent-cold-warm-message-67b331a3-kova-261011-052701-1adb77

## Target Cleanup

- Runtime: `kova-local-mv3dseun-3th-095c5fa9`
- Result: removed
- Duration: 503ms

