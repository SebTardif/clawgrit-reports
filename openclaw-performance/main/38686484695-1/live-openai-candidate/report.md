# Kova OpenClaw Runtime Report

> **❌ [FAIL]** — agent-process peak RSS 1476.7 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1676.4 MB, agent-process 1476.7 MB, status-cli 860.1 MB

## Verdict

| Field | Value |
|---|---|
| Verdict | FAIL |
| Reason | agent-process peak RSS 1476.7 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1676.4 MB, agent-process 1476.7 MB, status-cli 860.1 MB |
| Blocking findings | 5 |
| Warnings | 0 |
| Records | 1 (FAIL:1) |

## Proof Completeness

- Completeness: complete: 1
- Required obligations: 23 total, 0 missing, 0 failed
- Categories: command: 8, invariant: 12, artifact: 1, cleanup: 1, collector: 1

## Run

| Field | Value |
|---|---|
| Run ID | `kova-261015-052506-068116` |
| Generated | 2026-10-15T05:27:53.475Z |
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
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | agent-process peak RSS 1476.7 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1676.4 MB, agent-process 1476.7 MB, status-cli 860.1 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1476.7 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | command-tree peak RSS 1676.4 MB exceeded threshold 1400 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1476.7 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | cold agent spent 12266ms before provider work, over threshold 10000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1476.7 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | cold pre-provider latency was 12266ms, over threshold 10000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1476.7 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | cold provider was fast (1168ms), but OpenClaw spent 12266ms before provider work. | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1476.7 |

## Performance Summary

- Resource measurement scope: product
- Resource headline contract: `primary-role-product-scope-v4`

| Scenario | Samples | Status | Health Ready | Gateway RSS | Tracked RSS | CPU | Cold Turn | Warm Turn | Cold Pre-Provider |
|---|---:|---|---:|---:|---:|---:|---:|---:|---:|
| agent-cold-warm-message/mock-openai-provider | 1 | FAIL:1 | n/a | 0MB | n/a | 207.7% | 13743ms | 11154ms | 12266ms |

## Samples

| Sample | Status | Scenario | Upgrade From | Health Ready | Gateway RSS | Tracked RSS | Cold Turn | Warm Turn | Blocker |
|---:|---|---|---|---:|---:|---:|---:|---:|---|
| 1 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1676.4 MB | 13743ms | 11154ms | agent-process peak RSS 1476.7 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1676.4 MB, agent-process 1476.7 MB, status-cli 860.1 MB |

## Resource Roles

- Measurement scope: product
- Headline contract: `primary-role-product-scope-v4`
- command-tree: RSS 1676.4 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 221.6% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-process: RSS 1476.7 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 207.7% (scenario agent-cold-warm-message/mock-openai-provider)
- status-cli: RSS 860.1 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 179.4% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-cli: RSS 221 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 136.8% (scenario agent-cold-warm-message/mock-openai-provider)

## Selected Sample Details

### agent-cold-warm-message sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261015-052506-068116/kova-agent-cold-warm-message-2c26dd1d-kova-261015-052506-068116
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1476.7 MB; tracked total 1676.4 MB; max CPU 207.7%; samples 36; roles command-tree 1676.4MB/221.6%, agent-process 1476.7MB/207.7%, status-cli 860.1MB/179.4%, agent-cli 221MB/136.8%
- agent: turn 13743ms; cold/warm 13743ms/11154ms; cold-warm delta 2589ms; pre-provider 12266ms; provider 1168ms; metadata scans 12 (489.06ms); event-loop n/a; polls 0; cleanup n/a; diagnosis pre-provider-stall; leaks 0
- Agent turn stats: count 2; p95 13613.55ms; max 13743ms; pre-provider p95 12129.75ms
- agent CLI attribution: cold known 7360ms / unattributed 4906ms; warm known 5544ms / unattributed 3997ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span cli.command-startup 2616.6ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1476.7 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1676.4 MB, agent-process 1476.7 MB, status-cli 860.1 MB
  - command-tree peak RSS 1676.4 MB exceeded threshold 1400 MB
  - cold agent spent 12266ms before provider work, over threshold 10000ms
  - cold pre-provider latency was 12266ms, over threshold 10000ms
  - cold provider was fast (1168ms), but OpenClaw spent 12266ms before provider work.
- Agent turns:
  - cold: total 13743ms; pre-provider 12266ms; provider 1168ms; post-provider 309ms; response true
    - active window: metadata scans 6 (299.67ms total, max 133.8ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 12266ms; provider 1168ms; post-provider 309ms; unknown 9275.52ms; source agent.prepare 2033.72ms; plugins.metadata.scan 956.76ms
  - warm: total 11154ms; pre-provider 9541ms; provider 1309ms; post-provider 304ms; response true
    - active window: metadata scans 6 (189.39ms total, max 79.81ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 9541ms; provider 1309ms; post-provider 304ms; unknown 6550.52ms; source agent.prepare 2033.72ms; plugins.metadata.scan 956.76ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 12266 ms | 7360 ms | 4906 ms | 1168 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261015-052506-068116/kova-agent-cold-warm-message-2c26dd1d-kova-261015-052506-068116/openclaw/timeline.jsonl |
  | warm | 9541 ms | 5544 ms | 3997 ms | 1309 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261015-052506-068116/kova-agent-cold-warm-message-2c26dd1d-kova-261015-052506-068116/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `cli.command-startup` | `cli.command-startup` x10 | 10 | 0 | 7665 ms | 2617 ms |
  | cold | `agent.startup` | `agent.startup` x9 | 9 | 0 | 2917 ms | 1812 ms |
  | cold | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 873 ms | 382 ms |
  | cold | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3, `agent.startup` x2 | 6 | 0 | 300 ms | 134 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 31 ms | 31 ms |
  | cold | `plugins.metadata.freeze` | `cli.command-startup` x3, `agent.startup` x2 | 5 | 0 | 14 ms | 5 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 4146 ms | 1583 ms |
  | warm | `agent.startup` | `agent.startup` x9 | 9 | 0 | 2821 ms | 1737 ms |
  | warm | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1161 ms | 520 ms |
  | warm | `plugins.metadata.scan` | `cli.command-startup` x3, `startup`, `agent.startup` x2 | 6 | 0 | 190 ms | 80 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 21 ms | 21 ms |
  | warm | `plugins.metadata.freeze` | `cli.command-startup` x3, `agent.startup` x2 | 5 | 0 | 11 ms | 3 ms |

## Artifacts

- markdown-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/live-openai-candidate/kova-261015-052506-068116-diagnostic.md
- json-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/live-openai-candidate/kova-261015-052506-068116-diagnostic.json
- summary-json: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/live-openai-candidate/kova-261015-052506-068116-diagnostic.summary.json
- collector-root agent-cold-warm-message#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261015-052506-068116/kova-agent-cold-warm-message-2c26dd1d-kova-261015-052506-068116

## Target Cleanup

- Runtime: `kova-local-mv93hcbp-3tl-9cd0064b`
- Result: removed
- Duration: 587ms

