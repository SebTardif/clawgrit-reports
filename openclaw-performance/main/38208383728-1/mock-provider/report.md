# Kova OpenClaw Runtime Report

> **❌ [FAIL]** — gateway peak RSS 1769.4 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2084.2 MB, gateway 1769.4 MB, command-tree 1020.2 MB

## Verdict

| Field | Value |
|---|---|
| Verdict | FAIL |
| Reason | gateway peak RSS 1769.4 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2084.2 MB, gateway 1769.4 MB, command-tree 1020.2 MB |
| Blocking findings | 14 |
| Warnings | 0 |
| Records | 6 (FAIL:6) |

## Proof Completeness

- Completeness: complete: 6
- Required obligations: 358 total, 0 missing, 0 failed
- Categories: command: 304, artifact: 6, cleanup: 6, collector: 6, invariant: 36

## Run

| Field | Value |
|---|---|
| Run ID | `kova-261012-053437-59402e` |
| Generated | 2026-10-12T05:56:43.228Z |
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
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway peak RSS 1769.4 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2084.2 MB, gateway 1769.4 MB, command-tree 1020.2 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 51 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway-tree peak RSS 2084.2 MB exceeded threshold 1440 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 51 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | status-cli peak RSS 1020.2 MB exceeded threshold 900 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 51 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | ocm service restart 'kova-gateway-performance-man-1e8be6a8-kova-261012-053437-59402e' took 15181ms, over threshold 15000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 65 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway peak RSS 1847.6 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2298.1 MB, gateway 1847.6 MB, command-tree 861.5 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 65 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway-tree peak RSS 2298.1 MB exceeded threshold 1440 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 65 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway peak RSS 1787.5 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2107.7 MB, gateway 1787.5 MB, command-tree 1059.2 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 56 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway-tree peak RSS 2107.7 MB exceeded threshold 1440 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 56 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | status-cli peak RSS 1059.2 MB exceeded threshold 900 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 56 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | agent-process peak RSS 1455.2 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1557.3 MB, agent-process 1455.2 MB, status-cli 872.4 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1455.2 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | command-tree peak RSS 1557.3 MB exceeded threshold 1400 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1455.2 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | agent-process peak RSS 1469.5 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1571 MB, agent-process 1469.5 MB, status-cli 948.6 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1469.5 |
| info | Kova | report | 2 additional finding(s) omitted from Markdown | see summary JSON |

## Performance Summary

- Resource measurement scope: product
- Resource headline contract: `primary-role-product-scope-v4`

| Scenario | Samples | Status | Health Ready | Gateway RSS | Tracked RSS | CPU | Cold Turn | Warm Turn | Cold Pre-Provider |
|---|---:|---|---:|---:|---:|---:|---:|---:|---:|
| gateway-performance/many-bundled-plugins | 3 | FAIL:3 | 56ms | 1787.5MB | n/a | 238.3% | n/a | n/a | n/a |
| agent-cold-warm-message/mock-openai-provider | 3 | FAIL:3 | n/a | 0MB | n/a | 187.7% | 7527ms | 8273ms | 7163ms |

## Samples

| Sample | Status | Scenario | Upgrade From | Health Ready | Gateway RSS | Tracked RSS | Cold Turn | Warm Turn | Blocker |
|---:|---|---|---|---:|---:|---:|---:|---:|---|
| 1 | FAIL | gateway-performance/many-bundled-plugins |  | 51ms | 1769.4 MB | 2906.7 MB | n/a | n/a | gateway peak RSS 1769.4 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2084.2 MB, gateway 1769.4 MB, command-tree 1020.2 MB |
| 2 | FAIL | gateway-performance/many-bundled-plugins |  | 65ms | 1847.6 MB | 2841.2 MB | n/a | n/a | ocm service restart 'kova-gateway-performance-man-1e8be6a8-kova-261012-053437-59402e' took 15181ms, over threshold 15000ms |
| 3 | FAIL | gateway-performance/many-bundled-plugins |  | 56ms | 1787.5 MB | 2963.3 MB | n/a | n/a | gateway peak RSS 1787.5 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2107.7 MB, gateway 1787.5 MB, command-tree 1059.2 MB |
| 1 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1629.7 MB | 7527ms | 8273ms | agent-process peak RSS 1455.2 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1557.3 MB, agent-process 1455.2 MB, status-cli 872.4 MB |
| 2 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1643.2 MB | 7811ms | 8365ms | agent-process peak RSS 1469.5 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1571 MB, agent-process 1469.5 MB, status-cli 948.6 MB |
| 3 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1427 MB | 7061ms | 7810ms | agent-process peak RSS 1254.2 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1355.7 MB, agent-process 1254.2 MB, status-cli 1015.1 MB |

## Resource Roles

- Measurement scope: product
- Headline contract: `primary-role-product-scope-v4`
- gateway-tree: RSS 2298.1 MB (scenario gateway-performance/many-bundled-plugins); CPU 282.4% (scenario gateway-performance/many-bundled-plugins)
- gateway: RSS 1847.6 MB (scenario gateway-performance/many-bundled-plugins); CPU 244.3% (scenario gateway-performance/many-bundled-plugins)
- command-tree: RSS 1571 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 204.9% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-process: RSS 1469.5 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 195.3% (scenario agent-cold-warm-message/mock-openai-provider)
- status-cli: RSS 1059.2 MB (scenario gateway-performance/many-bundled-plugins); CPU 183% (scenario agent-cold-warm-message/mock-openai-provider)
- uncategorized: RSS 839.2 MB (scenario gateway-performance/many-bundled-plugins); CPU 164.2% (scenario gateway-performance/many-bundled-plugins)
- agent-cli: RSS 204.3 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 141.8% (scenario agent-cold-warm-message/mock-openai-provider)
- mock-provider: RSS 73.1 MB (scenario gateway-performance/many-bundled-plugins); CPU 10% (scenario gateway-performance/many-bundled-plugins)

## Selected Sample Details

### gateway-performance sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261012-053437-59402e/kova-gateway-performance-man-005107f3-kova-261012-053437-59402e
Measurements:
- startup: listening 1ms; health 51ms; readiness ready (gateway became healthy within the readiness threshold); gateway running; restarts 4
- health: startup p95 50ms; post-ready p95 3ms; failures 0; final failures 0; slowest final/final 80ms
- resources: scope product; contract primary-role-product-scope-v4; gateway RSS 1769.4 MB; tracked total 2906.7 MB; max CPU 244.3%; samples 43; roles gateway-tree 2084.2MB/282.4%, gateway 1769.4MB/244.3%, command-tree 1020.2MB/163.6%, status-cli 1020.2MB/163.6%
- agent: not-run
- Agent turn stats: count 0; p95 n/a; max n/a; pre-provider p95 n/a
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages 0; warm reuse true
- diagnostics: timeline available; slowest span sidecars.subagent-recovery 1849.08ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - gateway peak RSS 1769.4 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2084.2 MB, gateway 1769.4 MB, command-tree 1020.2 MB
  - gateway-tree peak RSS 2084.2 MB exceeded threshold 1440 MB
  - status-cli peak RSS 1020.2 MB exceeded threshold 900 MB

### gateway-performance sample 2

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261012-053437-59402e/kova-gateway-performance-man-1e8be6a8-kova-261012-053437-59402e
Measurements:
- startup: listening 0ms; health 65ms; readiness ready (gateway became healthy within the readiness threshold); gateway running; restarts 4
- health: startup p95 65ms; post-ready p95 6ms; failures 0; final failures 0; slowest startup-sample/cold-start 65ms
- resources: scope product; contract primary-role-product-scope-v4; gateway RSS 1847.6 MB; tracked total 2841.2 MB; max CPU 238.3%; samples 45; roles gateway-tree 2298.1MB/278.8%, gateway 1847.6MB/238.3%, command-tree 861.5MB/162.7%, uncategorized 839.2MB/164.2%
- agent: not-run
- Agent turn stats: count 0; p95 n/a; max n/a; pre-provider p95 n/a
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages 0; warm reuse true
- diagnostics: timeline available; slowest span gateway.request-runtime 1468.85ms; embedded traces 0; liveness warnings 0; open spans 5 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - ocm service restart 'kova-gateway-performance-man-1e8be6a8-kova-261012-053437-59402e' took 15181ms, over threshold 15000ms
  - gateway peak RSS 1847.6 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2298.1 MB, gateway 1847.6 MB, command-tree 861.5 MB
  - gateway-tree peak RSS 2298.1 MB exceeded threshold 1440 MB

### gateway-performance sample 3

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261012-053437-59402e/kova-gateway-performance-man-958fde53-kova-261012-053437-59402e
Measurements:
- startup: listening 0ms; health 56ms; readiness ready (gateway became healthy within the readiness threshold); gateway running; restarts 4
- health: startup p95 56ms; post-ready p95 3ms; failures 0; final failures 0; slowest final/final 93ms
- resources: scope product; contract primary-role-product-scope-v4; gateway RSS 1787.5 MB; tracked total 2963.3 MB; max CPU 224.5%; samples 42; roles gateway-tree 2107.7MB/268%, gateway 1787.5MB/224.5%, command-tree 1059.2MB/166.8%, status-cli 1059.2MB/166.8%
- agent: not-run
- Agent turn stats: count 0; p95 n/a; max n/a; pre-provider p95 n/a
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages 0; warm reuse true
- diagnostics: timeline available; slowest span sidecars.subagent-recovery 1394.2ms; embedded traces 0; liveness warnings 0; open spans 5 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - gateway peak RSS 1787.5 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2107.7 MB, gateway 1787.5 MB, command-tree 1059.2 MB
  - gateway-tree peak RSS 2107.7 MB exceeded threshold 1440 MB
  - status-cli peak RSS 1059.2 MB exceeded threshold 900 MB

### agent-cold-warm-message sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261012-053437-59402e/kova-agent-cold-warm-message-8e2a29af-kova-261012-053437-59402e
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1455.2 MB; tracked total 1629.7 MB; max CPU 195.3%; samples 27; roles command-tree 1557.3MB/204.9%, agent-process 1455.2MB/195.3%, status-cli 872.4MB/183%, agent-cli 204.3MB/112.3%
- agent: turn 8273ms; cold/warm 7527ms/8273ms; cold-warm delta 0ms; pre-provider 7986ms; provider 0ms; metadata scans 8 (217.61ms); event-loop n/a; polls 0; cleanup n/a; diagnosis agent-latency-attributed; leaks 0
- Agent turn stats: count 2; p95 8235.7ms; max 8273ms; pre-provider p95 7944.85ms
- agent CLI attribution: cold known 3327ms / unattributed 3836ms; warm known 4272ms / unattributed 3714ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span agent.startup 1706.57ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1455.2 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1557.3 MB, agent-process 1455.2 MB, status-cli 872.4 MB
  - command-tree peak RSS 1557.3 MB exceeded threshold 1400 MB
- Agent turns:
  - cold: total 7527ms; pre-provider 7163ms; provider 2ms; post-provider 362ms; response true
    - active window: metadata scans 4 (94.28ms total, max 49.39ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7163ms; provider 2ms; post-provider 362ms; unknown 3770.74ms; source agent.prepare 3053.16ms; plugins.metadata.scan 339.1ms
  - warm: total 8273ms; pre-provider 7986ms; provider 0ms; post-provider 287ms; response true
    - active window: metadata scans 4 (123.33ms total, max 68.82ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7986ms; provider 0ms; post-provider 287ms; unknown 4593.74ms; source agent.prepare 3053.16ms; plugins.metadata.scan 339.1ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 7163 ms | 3327 ms | 3836 ms | 2 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261012-053437-59402e/kova-agent-cold-warm-message-8e2a29af-kova-261012-053437-59402e/openclaw/timeline.jsonl |
  | warm | 7986 ms | 4272 ms | 3714 ms | 0 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261012-053437-59402e/kova-agent-cold-warm-message-8e2a29af-kova-261012-053437-59402e/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 1743 ms | 487 ms |
  | cold | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1701 ms | 657 ms |
  | cold | `agent.startup` | `agent.startup` x8 | 8 | 0 | 1068 ms | 672 ms |
  | cold | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 95 ms | 49 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 16 ms | 16 ms |
  | cold | `cli.main.core-imports` | `cli.startup` | 1 | 0 | 5 ms | 5 ms |
  | warm | `agent.startup` | `agent.startup` x9 | 9 | 0 | 2581 ms | 1707 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 1914 ms | 567 ms |
  | warm | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1353 ms | 628 ms |
  | warm | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 124 ms | 69 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 16 ms | 16 ms |
  | warm | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 9 ms | 5 ms |

### agent-cold-warm-message sample 2

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261012-053437-59402e/kova-agent-cold-warm-message-2ab680e0-kova-261012-053437-59402e
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1469.5 MB; tracked total 1643.2 MB; max CPU 187.3%; samples 27; roles command-tree 1571MB/199.4%, agent-process 1469.5MB/187.3%, status-cli 948.6MB/182.6%, agent-cli 202.4MB/136.2%
- agent: turn 8365ms; cold/warm 7811ms/8365ms; cold-warm delta 0ms; pre-provider 7920ms; provider 1ms; metadata scans 8 (204.23ms); event-loop n/a; polls 0; cleanup n/a; diagnosis agent-latency-attributed; leaks 0
- Agent turn stats: count 2; p95 8337.3ms; max 8365ms; pre-provider p95 7896.5ms
- agent CLI attribution: cold known 3524ms / unattributed 3926ms; warm known 4195ms / unattributed 3725ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span agent.startup 1639.86ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1469.5 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1571 MB, agent-process 1469.5 MB, status-cli 948.6 MB
  - command-tree peak RSS 1571 MB exceeded threshold 1400 MB
- Agent turns:
  - cold: total 7811ms; pre-provider 7450ms; provider 2ms; post-provider 359ms; response true
    - active window: metadata scans 4 (100.91ms total, max 52.78ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7450ms; provider 2ms; post-provider 359ms; unknown 4000.11ms; source agent.prepare 3127.34ms; plugins.metadata.scan 322.55ms
  - warm: total 8365ms; pre-provider 7920ms; provider 1ms; post-provider 444ms; response true
    - active window: metadata scans 4 (103.32ms total, max 56.99ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7920ms; provider 1ms; post-provider 444ms; unknown 4470.11ms; source agent.prepare 3127.34ms; plugins.metadata.scan 322.55ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 7450 ms | 3524 ms | 3926 ms | 2 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261012-053437-59402e/kova-agent-cold-warm-message-2ab680e0-kova-261012-053437-59402e/openclaw/timeline.jsonl |
  | warm | 7920 ms | 4195 ms | 3725 ms | 1 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261012-053437-59402e/kova-agent-cold-warm-message-2ab680e0-kova-261012-053437-59402e/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `cli.command-startup` | `cli.command-startup` x10 | 10 | 0 | 1930 ms | 545 ms |
  | cold | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1683 ms | 674 ms |
  | cold | `agent.startup` | `agent.startup` x9 | 9 | 0 | 1178 ms | 773 ms |
  | cold | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 100 ms | 52 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 17 ms | 17 ms |
  | cold | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 7 ms | 4 ms |
  | warm | `agent.startup` | `agent.startup` x9 | 9 | 0 | 2463 ms | 1640 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 1796 ms | 538 ms |
  | warm | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1448 ms | 650 ms |
  | warm | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 104 ms | 57 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 17 ms | 17 ms |
  | warm | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 7 ms | 3 ms |

### agent-cold-warm-message sample 3

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261012-053437-59402e/kova-agent-cold-warm-message-67b331a3-kova-261012-053437-59402e
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1254.2 MB; tracked total 1427 MB; max CPU 187.7%; samples 25; roles command-tree 1355.7MB/197.8%, agent-process 1254.2MB/187.7%, status-cli 1015.1MB/174.3%, agent-cli 183.9MB/141.8%
- agent: turn 7810ms; cold/warm 7061ms/7810ms; cold-warm delta 0ms; pre-provider 7568ms; provider 1ms; metadata scans 8 (206.89ms); event-loop n/a; polls 0; cleanup n/a; diagnosis agent-latency-attributed; leaks 0
- Agent turn stats: count 2; p95 7772.55ms; max 7810ms; pre-provider p95 7527.25ms
- agent CLI attribution: cold known 3223ms / unattributed 3530ms; warm known 4035ms / unattributed 3533ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span agent.startup 1523.58ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1254.2 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1355.7 MB, agent-process 1254.2 MB, status-cli 1015.1 MB
- Agent turns:
  - cold: total 7061ms; pre-provider 6753ms; provider 2ms; post-provider 306ms; response true
    - active window: metadata scans 4 (103.03ms total, max 53.38ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 6753ms; provider 2ms; post-provider 306ms; unknown 3527.69ms; source agent.prepare 2901.89ms; plugins.metadata.scan 323.42ms
  - warm: total 7810ms; pre-provider 7568ms; provider 1ms; post-provider 241ms; response true
    - active window: metadata scans 4 (103.86ms total, max 54ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7568ms; provider 1ms; post-provider 241ms; unknown 4342.69ms; source agent.prepare 2901.89ms; plugins.metadata.scan 323.42ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 6753 ms | 3223 ms | 3530 ms | 2 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261012-053437-59402e/kova-agent-cold-warm-message-67b331a3-kova-261012-053437-59402e/openclaw/timeline.jsonl |
  | warm | 7568 ms | 4035 ms | 3533 ms | 1 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261012-053437-59402e/kova-agent-cold-warm-message-67b331a3-kova-261012-053437-59402e/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 1886 ms | 524 ms |
  | cold | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1497 ms | 603 ms |
  | cold | `agent.startup` | `agent.startup` x8 | 8 | 0 | 1045 ms | 674 ms |
  | cold | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 102 ms | 53 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 16 ms | 16 ms |
  | cold | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 7 ms | 4 ms |
  | warm | `agent.startup` | `agent.startup` x9 | 9 | 0 | 2295 ms | 1524 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 1833 ms | 529 ms |
  | warm | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1404 ms | 641 ms |
  | warm | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 104 ms | 54 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 17 ms | 17 ms |
  | warm | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 13 ms | 10 ms |

## Artifacts

- markdown-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-provider/kova-261012-053437-59402e-diagnostic.md
- json-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-provider/kova-261012-053437-59402e-diagnostic.json
- summary-json: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-provider/kova-261012-053437-59402e-diagnostic.summary.json
- collector-root gateway-performance#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261012-053437-59402e/kova-gateway-performance-man-005107f3-kova-261012-053437-59402e
- collector-root gateway-performance#2: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261012-053437-59402e/kova-gateway-performance-man-1e8be6a8-kova-261012-053437-59402e
- collector-root gateway-performance#3: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261012-053437-59402e/kova-gateway-performance-man-958fde53-kova-261012-053437-59402e
- collector-root agent-cold-warm-message#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261012-053437-59402e/kova-agent-cold-warm-message-8e2a29af-kova-261012-053437-59402e
- collector-root agent-cold-warm-message#2: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261012-053437-59402e/kova-agent-cold-warm-message-2ab680e0-kova-261012-053437-59402e
- collector-root agent-cold-warm-message#3: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261012-053437-59402e/kova-agent-cold-warm-message-67b331a3-kova-261012-053437-59402e

## Target Cleanup

- Runtime: `kova-local-mv4ti0v9-3ud-4c3f6a90`
- Result: removed
- Duration: 589ms

