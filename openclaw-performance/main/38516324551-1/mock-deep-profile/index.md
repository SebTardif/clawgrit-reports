# OpenClaw Performance Report

- Lane: mock-deep-profile
- Run: kova-261014-052433-733d9e
- Generated: 2026-10-14T05:36:10.336Z
- Target: local-build:/home/runner/_work/openclaw/openclaw
- Statuses: FAIL: 2
- Repeat: 1

## Key metrics

| Scenario | State | Metric | Median | p95 | Max |
| --- | --- | --- | ---: | ---: | ---: |
| gateway-performance | many-bundled-plugins | Primary RSS | 2,044 MB | 2,044 MB | 2,044 MB |
| gateway-performance | many-bundled-plugins | Gateway RSS | 2,044 MB | 2,044 MB | 2,044 MB |
| gateway-performance | many-bundled-plugins | Max CPU | 312 % | 312 % | 312 % |
| gateway-performance | many-bundled-plugins | Event Loop Max | 53.1 ms | 53.1 ms | 53.1 ms |
| agent-cold-warm-message | mock-openai-provider | Primary RSS | 1,782 MB | 1,782 MB | 1,782 MB |
| agent-cold-warm-message | mock-openai-provider | Gateway RSS | 0 MB | 0 MB | 0 MB |
| agent-cold-warm-message | mock-openai-provider | Max CPU | 297 % | 297 % | 297 % |
| agent-cold-warm-message | mock-openai-provider | Agent Turn p95 | 19,215 ms | 19,215 ms | 19,215 ms |
| agent-cold-warm-message | mock-openai-provider | Cold Agent Turn | 19,061 ms | 19,061 ms | 19,061 ms |
| agent-cold-warm-message | mock-openai-provider | Warm Agent Turn | 19,223 ms | 19,223 ms | 19,223 ms |
| agent-cold-warm-message | mock-openai-provider | Pre-Provider p95 | 17,341 ms | 17,341 ms | 17,341 ms |

## Threshold violations

| Scenario | State | Metric | Actual | Threshold |
| --- | --- | --- | ---: | ---: |
| gateway-performance | many-bundled-plugins | resourceCpuCoverage | ["Product CPU interval or terminal wait accounting is incomplete"] | complete CPU interval evidence |
| gateway-performance | many-bundled-plugins | peakRssMb | 2,044 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 2,302 | <= 1440 |
| agent-cold-warm-message | mock-openai-provider | resourceByRole.agent-cli.maxCpuPercent | {"lower":275.6,"upper":349.5} | <= 300 |
| agent-cold-warm-message | mock-openai-provider | totalTurnMs | 19,223 | <= 15000 |
| agent-cold-warm-message | mock-openai-provider | agentLatencyDiagnosis | pre-provider-stall | no cold pre-provider stall |

## Records

| Scenario | State | Status | Failure |
| --- | --- | --- | --- |
| gateway-performance | many-bundled-plugins | FAIL |  |
| agent-cold-warm-message | mock-openai-provider | FAIL |  |

## Test scope

- Repository: openclaw/openclaw
- Tested ref: main
- Tested SHA: 30fb4feba23f4afe6e29065dc69a9b756f821e87
- Workflow ref: main
- Workflow SHA: 30fb4feba23f4afe6e29065dc69a9b756f821e87
- Kova repository: openclaw/Kova
- Kova ref: 88d9a7efa5e6569f902bf8d298fd6a21c6be2e7b
- Kova profile: diagnostic
- Kova scenario timeout: 300000ms
- Lane auth: mock
- Lane model: gpt-5.6-luna
- Lane repeat: 1
- Include filters: scenario:fresh-install,scenario:gateway-performance,scenario:agent-cold-warm-message

## Full diagnostic artifact

The complete Kova bundle remains in [Actions artifact 11871778854](https://github.com/openclaw/openclaw/actions/runs/38516324551/artifacts/11871778854); its checksum is published under the bundles directory.
