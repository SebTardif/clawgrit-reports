# OpenClaw Performance Report

- Lane: mock-deep-profile
- Run: kova-261015-052503-d06c37
- Generated: 2026-10-15T05:35:07.088Z
- Target: local-build:/home/runner/_work/openclaw/openclaw
- Statuses: FAIL: 2
- Repeat: 1

## Key metrics

| Scenario | State | Metric | Median | p95 | Max |
| --- | --- | --- | ---: | ---: | ---: |
| gateway-performance | many-bundled-plugins | Primary RSS | 2,114 MB | 2,114 MB | 2,114 MB |
| gateway-performance | many-bundled-plugins | Gateway RSS | 2,114 MB | 2,114 MB | 2,114 MB |
| gateway-performance | many-bundled-plugins | Max CPU | 303 % | 303 % | 303 % |
| gateway-performance | many-bundled-plugins | Event Loop Max | 44.3 ms | 44.3 ms | 44.3 ms |
| agent-cold-warm-message | mock-openai-provider | Primary RSS | 1,935 MB | 1,935 MB | 1,935 MB |
| agent-cold-warm-message | mock-openai-provider | Gateway RSS | 0 MB | 0 MB | 0 MB |
| agent-cold-warm-message | mock-openai-provider | Max CPU | 333 % | 333 % | 333 % |
| agent-cold-warm-message | mock-openai-provider | Agent Turn p95 | 15,719 ms | 15,719 ms | 15,719 ms |
| agent-cold-warm-message | mock-openai-provider | Cold Agent Turn | 15,571 ms | 15,571 ms | 15,571 ms |
| agent-cold-warm-message | mock-openai-provider | Warm Agent Turn | 15,727 ms | 15,727 ms | 15,727 ms |
| agent-cold-warm-message | mock-openai-provider | Pre-Provider p95 | 14,193 ms | 14,193 ms | 14,193 ms |

## Threshold violations

| Scenario | State | Metric | Actual | Threshold |
| --- | --- | --- | ---: | ---: |
| gateway-performance | many-bundled-plugins | resourceCpuCoverage | ["Product CPU interval or terminal wait accounting is incomplete"] | complete CPU interval evidence |
| gateway-performance | many-bundled-plugins | peakRssMb | 2,114 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 2,319 | <= 1440 |
| agent-cold-warm-message | mock-openai-provider | totalTurnMs | 15,727 | <= 15000 |
| agent-cold-warm-message | mock-openai-provider | agentLatencyDiagnosis | pre-provider-stall | no cold pre-provider stall |

## Records

| Scenario | State | Status | Failure |
| --- | --- | --- | --- |
| gateway-performance | many-bundled-plugins | FAIL |  |
| agent-cold-warm-message | mock-openai-provider | FAIL |  |

## Test scope

- Repository: openclaw/openclaw
- Tested ref: main
- Tested SHA: 54691736d026cba16ee8623bb3729f8c2c4c5af7
- Workflow ref: main
- Workflow SHA: 54691736d026cba16ee8623bb3729f8c2c4c5af7
- Kova repository: openclaw/Kova
- Kova ref: 88d9a7efa5e6569f902bf8d298fd6a21c6be2e7b
- Kova profile: diagnostic
- Kova scenario timeout: 300000ms
- Lane auth: mock
- Lane model: gpt-5.6-luna
- Lane repeat: 1
- Include filters: scenario:fresh-install,scenario:gateway-performance,scenario:agent-cold-warm-message

## Full diagnostic artifact

The complete Kova bundle remains in [Actions artifact 11950348613](https://github.com/openclaw/openclaw/actions/runs/38686484695/artifacts/11950348613); its checksum is published under the bundles directory.
