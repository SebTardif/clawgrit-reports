# OpenClaw Performance Report

- Lane: mock-deep-profile
- Run: kova-261012-053446-3f8d65
- Generated: 2026-10-12T05:45:10.109Z
- Target: local-build:/home/runner/_work/openclaw/openclaw
- Statuses: FAIL: 2
- Repeat: 1

## Key metrics

| Scenario | State | Metric | Median | p95 | Max |
| --- | --- | --- | ---: | ---: | ---: |
| gateway-performance | many-bundled-plugins | Primary RSS | 1,706 MB | 1,706 MB | 1,706 MB |
| gateway-performance | many-bundled-plugins | Gateway RSS | 1,706 MB | 1,706 MB | 1,706 MB |
| gateway-performance | many-bundled-plugins | Max CPU | 300 % | 300 % | 300 % |
| gateway-performance | many-bundled-plugins | Event Loop Max | 72.7 ms | 72.7 ms | 72.7 ms |
| agent-cold-warm-message | mock-openai-provider | Primary RSS | 1,938 MB | 1,938 MB | 1,938 MB |
| agent-cold-warm-message | mock-openai-provider | Gateway RSS | 0 MB | 0 MB | 0 MB |
| agent-cold-warm-message | mock-openai-provider | Max CPU | 323 % | 323 % | 323 % |
| agent-cold-warm-message | mock-openai-provider | Agent Turn p95 | 20,928 ms | 20,928 ms | 20,928 ms |
| agent-cold-warm-message | mock-openai-provider | Cold Agent Turn | 21,097 ms | 21,097 ms | 21,097 ms |
| agent-cold-warm-message | mock-openai-provider | Warm Agent Turn | 17,726 ms | 17,726 ms | 17,726 ms |
| agent-cold-warm-message | mock-openai-provider | Pre-Provider p95 | 18,191 ms | 18,191 ms | 18,191 ms |

## Threshold violations

| Scenario | State | Metric | Actual | Threshold |
| --- | --- | --- | ---: | ---: |
| gateway-performance | many-bundled-plugins | peakRssMb | 1,706 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 2,022 | <= 1440 |
| agent-cold-warm-message | mock-openai-provider | totalTurnMs | 17,726 | <= 15000 |
| agent-cold-warm-message | mock-openai-provider | agentLatencyDiagnosis | pre-provider-stall | no cold pre-provider stall |

## Records

| Scenario | State | Status | Failure |
| --- | --- | --- | --- |
| gateway-performance | many-bundled-plugins | FAIL |  |
| agent-cold-warm-message | mock-openai-provider | FAIL |  |

## Test scope

- Repository: openclaw/openclaw
- Tested ref: main
- Tested SHA: a5710f05606286ad6981fc1e514b595544906585
- Workflow ref: main
- Workflow SHA: a5710f05606286ad6981fc1e514b595544906585
- Kova repository: openclaw/Kova
- Kova ref: 88d9a7efa5e6569f902bf8d298fd6a21c6be2e7b
- Kova profile: diagnostic
- Kova scenario timeout: 300000ms
- Lane auth: mock
- Lane model: gpt-5.6-luna
- Lane repeat: 1
- Include filters: scenario:fresh-install,scenario:gateway-performance,scenario:agent-cold-warm-message

## Full diagnostic artifact

The complete Kova bundle remains in [Actions artifact 11729081018](https://github.com/openclaw/openclaw/actions/runs/38208383728/artifacts/11729081018); its checksum is published under the bundles directory.
