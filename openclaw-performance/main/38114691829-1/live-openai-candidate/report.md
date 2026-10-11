# Kova OpenClaw Runtime Report

> **❌ [FAIL]** — agent-process peak RSS 1302.8 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1404.5 MB, agent-process 1302.8 MB, status-cli 744.4 MB

## Verdict

| Field | Value |
|---|---|
| Verdict | FAIL |
| Reason | agent-process peak RSS 1302.8 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1404.5 MB, agent-process 1302.8 MB, status-cli 744.4 MB |
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
| Run ID | `kova-261011-052630-b2f590` |
| Generated | 2026-10-11T05:29:07.708Z |
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
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | agent-process peak RSS 1302.8 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1404.5 MB, agent-process 1302.8 MB, status-cli 744.4 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1302.8 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | command-tree peak RSS 1404.5 MB exceeded threshold 1400 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1302.8 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | cold agent spent 11113ms before provider work, over threshold 10000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1302.8 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | warm agent spent 10848ms before provider work, over threshold 10000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1302.8 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | cold pre-provider latency was 11113ms, over threshold 10000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1302.8 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | warm pre-provider latency was 10848ms, over threshold 10000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1302.8 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | cold provider was fast (1676ms), but OpenClaw spent 11113ms before provider work. | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1302.8 |

## Performance Summary

- Resource measurement scope: product
- Resource headline contract: `primary-role-product-scope-v4`

| Scenario | Samples | Status | Health Ready | Gateway RSS | Tracked RSS | CPU | Cold Turn | Warm Turn | Cold Pre-Provider |
|---|---:|---|---:|---:|---:|---:|---:|---:|---:|
| agent-cold-warm-message/mock-openai-provider | 1 | FAIL:1 | n/a | 0MB | n/a | 168.7% | 13154ms | 12968ms | 11113ms |

## Samples

| Sample | Status | Scenario | Upgrade From | Health Ready | Gateway RSS | Tracked RSS | Cold Turn | Warm Turn | Blocker |
|---:|---|---|---|---:|---:|---:|---:|---:|---|
| 1 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1404.5 MB | 13154ms | 12968ms | agent-process peak RSS 1302.8 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1404.5 MB, agent-process 1302.8 MB, status-cli 744.4 MB |

## Resource Roles

- Measurement scope: product
- Headline contract: `primary-role-product-scope-v4`
- command-tree: RSS 1404.5 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 178.7% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-process: RSS 1302.8 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 168.7% (scenario agent-cold-warm-message/mock-openai-provider)
- status-cli: RSS 744.4 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 176.8% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-cli: RSS 186.7 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 71.2% (scenario agent-cold-warm-message/mock-openai-provider)

## Selected Sample Details

### agent-cold-warm-message sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261011-052630-b2f590/kova-agent-cold-warm-message-2c26dd1d-kova-261011-052630-b2f590
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1302.8 MB; tracked total 1404.5 MB; max CPU 168.7%; samples 37; roles command-tree 1404.5MB/178.7%, agent-process 1302.8MB/168.7%, status-cli 744.4MB/176.8%, agent-cli 186.7MB/71.2%
- agent: turn 13154ms; cold/warm 13154ms/12968ms; cold-warm delta 186ms; pre-provider 11113ms; provider 1676ms; metadata scans 12 (388ms); event-loop n/a; polls 0; cleanup n/a; diagnosis pre-provider-stall; leaks 0
- Agent turn stats: count 2; p95 13144.7ms; max 13154ms; pre-provider p95 11099.75ms
- agent CLI attribution: cold known 4816ms / unattributed 6297ms; warm known 5365ms / unattributed 5483ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span cli.command-startup 2574.61ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1302.8 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1404.5 MB, agent-process 1302.8 MB, status-cli 744.4 MB
  - command-tree peak RSS 1404.5 MB exceeded threshold 1400 MB
  - cold agent spent 11113ms before provider work, over threshold 10000ms
  - warm agent spent 10848ms before provider work, over threshold 10000ms
  - cold pre-provider latency was 11113ms, over threshold 10000ms
  - warm pre-provider latency was 10848ms, over threshold 10000ms
  - cold provider was fast (1676ms), but OpenClaw spent 11113ms before provider work.
- Agent turns:
  - cold: total 13154ms; pre-provider 11113ms; provider 1676ms; post-provider 365ms; response true
    - active window: metadata scans 6 (192.77ms total, max 92.93ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 11113ms; provider 1676ms; post-provider 365ms; unknown 9041.91ms; source agent.prepare 1263.39ms; plugins.metadata.scan 807.7ms
  - warm: total 12968ms; pre-provider 10848ms; provider 1797ms; post-provider 323ms; response true
    - active window: metadata scans 6 (195.23ms total, max 89.49ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 10848ms; provider 1797ms; post-provider 323ms; unknown 8776.91ms; source agent.prepare 1263.39ms; plugins.metadata.scan 807.7ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 11113 ms | 4816 ms | 6297 ms | 1676 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261011-052630-b2f590/kova-agent-cold-warm-message-2c26dd1d-kova-261011-052630-b2f590/openclaw/timeline.jsonl |
  | warm | 10848 ms | 5365 ms | 5483 ms | 1797 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261011-052630-b2f590/kova-agent-cold-warm-message-2c26dd1d-kova-261011-052630-b2f590/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 6645 ms | 2575 ms |
  | cold | `agent.startup` | `agent.startup` x9 | 9 | 0 | 955 ms | 587 ms |
  | cold | `agent.prepare` | `agent.prepare` x10 | 10 | 0 | 381 ms | 147 ms |
  | cold | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3, `agent.startup` x2 | 6 | 0 | 192 ms | 93 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 17 ms | 17 ms |
  | cold | `plugins.metadata.freeze` | `cli.command-startup` x3, `agent.startup` x2 | 5 | 0 | 14 ms | 4 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x8 | 8 | 0 | 5636 ms | 2269 ms |
  | warm | `agent.startup` | `agent.startup` x9 | 9 | 0 | 1440 ms | 1047 ms |
  | warm | `agent.prepare` | `agent.prepare` x9 | 9 | 0 | 883 ms | 643 ms |
  | warm | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3, `agent.startup` x2 | 6 | 0 | 197 ms | 90 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 16 ms | 16 ms |
  | warm | `plugins.metadata.freeze` | `cli.command-startup` x3, `agent.startup` x2 | 5 | 0 | 13 ms | 3 ms |

## Artifacts

- markdown-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/live-openai-candidate/kova-261011-052630-b2f590-diagnostic.md
- json-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/live-openai-candidate/kova-261011-052630-b2f590-diagnostic.json
- summary-json: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/live-openai-candidate/kova-261011-052630-b2f590-diagnostic.summary.json
- collector-root agent-cold-warm-message#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261011-052630-b2f590/kova-agent-cold-warm-message-2c26dd1d-kova-261011-052630-b2f590

## Target Cleanup

- Runtime: `kova-local-mv3drqg1-3t0-2f23fa24`
- Result: removed
- Duration: 496ms

