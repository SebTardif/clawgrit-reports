# Kova OpenClaw Runtime Report

> **❌ [FAIL]** — agent-process peak RSS 1353.9 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1555.7 MB, agent-process 1353.9 MB, status-cli 868.1 MB

## Verdict

| Field | Value |
|---|---|
| Verdict | FAIL |
| Reason | agent-process peak RSS 1353.9 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1555.7 MB, agent-process 1353.9 MB, status-cli 868.1 MB |
| Blocking findings | 7 |
| Warnings | 0 |
| Records | 1 (FAIL:1) |

## Proof Completeness

- Completeness: complete: 1
- Required obligations: 23 total, 0 missing, 0 failed
- Categories: command: 8, invariant: 12, artifact: 1, cleanup: 1, collector: 1

## Run

| Field | Value |
|---|---|
| Run ID | `kova-261014-052433-c1163a` |
| Generated | 2026-10-14T05:27:20.411Z |
| Mode | execution |
| Target | `local-build:/home/runner/_work/openclaw/openclaw` |
| Platform | linux 6.6.141 (x64) · v24.19.0 |
| Repeat / parallel | 1 / 1 |
| Auth | live (openai) |
| Network frontage | port |

## Coverage

| Field | Value |
|---|---:|
| Records | 1 |
| Scenarios | 1 |
| States | 1 |
| FAIL | 1 |

## Findings

| Severity | Area | Scenario | Finding | Evidence |
|---|---|---|---|---|
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | agent-process peak RSS 1353.9 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1555.7 MB, agent-process 1353.9 MB, status-cli 868.1 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1353.9 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | command-tree peak RSS 1555.7 MB exceeded threshold 1400 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1353.9 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | cold agent spent 10402ms before provider work, over threshold 10000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1353.9 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | warm agent spent 10025ms before provider work, over threshold 10000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1353.9 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | cold pre-provider latency was 10402ms, over threshold 10000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1353.9 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | warm pre-provider latency was 10025ms, over threshold 10000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1353.9 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | cold provider was fast (1355ms), but OpenClaw spent 10402ms before provider work. | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1353.9 |

## Performance Summary

- Resource measurement scope: product
- Resource headline contract: `primary-role-product-scope-v4`

| Scenario | Samples | Status | Health Ready | Gateway RSS | Tracked RSS | CPU | Cold Turn | Warm Turn | Cold Pre-Provider |
|---|---:|---|---:|---:|---:|---:|---:|---:|---:|
| agent-cold-warm-message/mock-openai-provider | 1 | FAIL:1 | n/a | 0MB | n/a | 167.9% | 12042ms | 11900ms | 10402ms |

## Samples

| Sample | Status | Scenario | Upgrade From | Health Ready | Gateway RSS | Tracked RSS | Cold Turn | Warm Turn | Blocker |
|---:|---|---|---|---:|---:|---:|---:|---:|---|
| 1 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1555.7 MB | 12042ms | 11900ms | agent-process peak RSS 1353.9 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1555.7 MB, agent-process 1353.9 MB, status-cli 868.1 MB |

## Resource Roles

- Measurement scope: product
- Headline contract: `primary-role-product-scope-v4`
- command-tree: RSS 1555.7 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 186.6% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-process: RSS 1353.9 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 167.9% (scenario agent-cold-warm-message/mock-openai-provider)
- status-cli: RSS 868.1 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 186.6% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-cli: RSS 268.5 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 92.2% (scenario agent-cold-warm-message/mock-openai-provider)

## Selected Sample Details

### agent-cold-warm-message sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261014-052433-c1163a/kova-agent-cold-warm-message-2c26dd1d-kova-261014-052433-c1163a
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1353.9 MB; tracked total 1555.7 MB; max CPU 167.9%; samples 34; roles command-tree 1555.7MB/186.6%, agent-process 1353.9MB/167.9%, status-cli 868.1MB/186.6%, agent-cli 268.5MB/92.2%
- agent: turn 12042ms; cold/warm 12042ms/11900ms; cold-warm delta 142ms; pre-provider 10402ms; provider 1355ms; metadata scans 12 (358.63ms); event-loop n/a; polls 0; cleanup n/a; diagnosis pre-provider-stall; leaks 0
- Agent turn stats: count 2; p95 12034.9ms; max 12042ms; pre-provider p95 10383.15ms
- agent CLI attribution: cold known 6186ms / unattributed 4216ms; warm known 5711ms / unattributed 4314ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span cli.command-startup 2025.87ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1353.9 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1555.7 MB, agent-process 1353.9 MB, status-cli 868.1 MB
  - command-tree peak RSS 1555.7 MB exceeded threshold 1400 MB
  - cold agent spent 10402ms before provider work, over threshold 10000ms
  - warm agent spent 10025ms before provider work, over threshold 10000ms
  - cold pre-provider latency was 10402ms, over threshold 10000ms
  - warm pre-provider latency was 10025ms, over threshold 10000ms
  - cold provider was fast (1355ms), but OpenClaw spent 10402ms before provider work.
- Agent turns:
  - cold: total 12042ms; pre-provider 10402ms; provider 1355ms; post-provider 285ms; response true
    - active window: metadata scans 6 (176.42ms total, max 73.47ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 10402ms; provider 1355ms; post-provider 285ms; unknown 7354.5ms; source agent.prepare 2219.31ms; plugins.metadata.scan 828.19ms
  - warm: total 11900ms; pre-provider 10025ms; provider 1471ms; post-provider 404ms; response true
    - active window: metadata scans 6 (182.21ms total, max 74.17ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 10025ms; provider 1471ms; post-provider 404ms; unknown 6977.5ms; source agent.prepare 2219.31ms; plugins.metadata.scan 828.19ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 10402 ms | 6186 ms | 4216 ms | 1355 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261014-052433-c1163a/kova-agent-cold-warm-message-2c26dd1d-kova-261014-052433-c1163a/openclaw/timeline.jsonl |
  | warm | 10025 ms | 5711 ms | 4314 ms | 1471 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261014-052433-c1163a/kova-agent-cold-warm-message-2c26dd1d-kova-261014-052433-c1163a/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 5716 ms | 2026 ms |
  | cold | `agent.startup` | `agent.startup` x9 | 9 | 0 | 2820 ms | 1738 ms |
  | cold | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 917 ms | 397 ms |
  | cold | `plugins.metadata.scan` | `cli.command-startup` x3, `startup`, `agent.startup` x2 | 6 | 0 | 176 ms | 73 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 21 ms | 21 ms |
  | cold | `plugins.metadata.freeze` | `cli.command-startup` x3, `agent.startup` x2 | 5 | 0 | 14 ms | 6 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 4202 ms | 1630 ms |
  | warm | `agent.startup` | `agent.startup` x9 | 9 | 0 | 2927 ms | 1766 ms |
  | warm | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1302 ms | 589 ms |
  | warm | `plugins.metadata.scan` | `cli.command-startup` x3, `startup`, `agent.startup` x2 | 6 | 0 | 183 ms | 75 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 21 ms | 21 ms |
  | warm | `plugins.metadata.freeze` | `cli.command-startup` x3, `agent.startup` x2 | 5 | 0 | 12 ms | 3 ms |

## Artifacts

- markdown-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/live-openai-candidate/kova-261014-052433-c1163a-diagnostic.md
- json-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/live-openai-candidate/kova-261014-052433-c1163a-diagnostic.json
- summary-json: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/live-openai-candidate/kova-261014-052433-c1163a-diagnostic.summary.json
- collector-root agent-cold-warm-message#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261014-052433-c1163a/kova-agent-cold-warm-message-2c26dd1d-kova-261014-052433-c1163a

## Target Cleanup

- Runtime: `kova-local-mv7o0sb3-3t1-6445f667`
- Result: removed
- Duration: 593ms

