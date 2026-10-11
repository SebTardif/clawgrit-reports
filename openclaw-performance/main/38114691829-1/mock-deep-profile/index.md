# OpenClaw Performance Report

- Lane: mock-deep-profile
- Run: kova-261011-052637-56e5b9
- Generated: 2026-10-11T05:35:26.342Z
- Target: local-build:/home/runner/_work/openclaw/openclaw
- Statuses: FAIL: 2
- Repeat: 1

## Key metrics

| Scenario | State | Metric | Median | p95 | Max |
| --- | --- | --- | ---: | ---: | ---: |
| gateway-performance | many-bundled-plugins | Primary RSS | 1,683 MB | 1,683 MB | 1,683 MB |
| gateway-performance | many-bundled-plugins | Gateway RSS | 1,683 MB | 1,683 MB | 1,683 MB |
| gateway-performance | many-bundled-plugins | Max CPU | 239 % | 239 % | 239 % |
| gateway-performance | many-bundled-plugins | Event Loop Max | 20.7 ms | 20.7 ms | 20.7 ms |
| agent-cold-warm-message | mock-openai-provider | Primary RSS | 1,848 MB | 1,848 MB | 1,848 MB |
| agent-cold-warm-message | mock-openai-provider | Gateway RSS | 0 MB | 0 MB | 0 MB |
| agent-cold-warm-message | mock-openai-provider | Max CPU | 337 % | 337 % | 337 % |
| agent-cold-warm-message | mock-openai-provider | Agent Turn p95 | 13,677 ms | 13,677 ms | 13,677 ms |
| agent-cold-warm-message | mock-openai-provider | Cold Agent Turn | 13,408 ms | 13,408 ms | 13,408 ms |
| agent-cold-warm-message | mock-openai-provider | Warm Agent Turn | 13,691 ms | 13,691 ms | 13,691 ms |
| agent-cold-warm-message | mock-openai-provider | Pre-Provider p95 | 12,168 ms | 12,168 ms | 12,168 ms |

## Threshold violations

| Scenario | State | Metric | Actual | Threshold |
| --- | --- | --- | ---: | ---: |
| gateway-performance | many-bundled-plugins | peakRssMb | 1,683 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 1,983 | <= 1440 |
| gateway-performance | many-bundled-plugins | resourceByRole.status-cli.maxCpuPercent | {"lower":166.4,"upper":281.3} | <= 200 |
| agent-cold-warm-message | mock-openai-provider | agentLatencyDiagnosis | pre-provider-stall | no cold pre-provider stall |

## Records

| Scenario | State | Status | Failure |
| --- | --- | --- | --- |
| gateway-performance | many-bundled-plugins | FAIL |  |
| agent-cold-warm-message | mock-openai-provider | FAIL |  |

## Test scope

- Repository: openclaw/openclaw
- Tested ref: main
- Tested SHA: 9a62c5b5cd2eb98a47e7091dfa1484cfe8dd7809
- Workflow ref: main
- Workflow SHA: 9a62c5b5cd2eb98a47e7091dfa1484cfe8dd7809
- Kova repository: openclaw/Kova
- Kova ref: 88d9a7efa5e6569f902bf8d298fd6a21c6be2e7b
- Kova profile: diagnostic
- Kova scenario timeout: 300000ms
- Lane auth: mock
- Lane model: gpt-5.6-luna
- Lane repeat: 1
- Include filters: scenario:fresh-install,scenario:gateway-performance,scenario:agent-cold-warm-message

## Full diagnostic artifact

The complete Kova bundle remains in [Actions artifact 11693387344](https://github.com/openclaw/openclaw/actions/runs/38114691829/artifacts/11693387344); its checksum is published under the bundles directory.
