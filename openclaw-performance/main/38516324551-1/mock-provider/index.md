# OpenClaw Performance Report

- Lane: mock-provider
- Run: kova-261014-052432-3ccdcd
- Generated: 2026-10-14T05:47:54.794Z
- Target: local-build:/home/runner/_work/openclaw/openclaw
- Statuses: FAIL: 6
- Repeat: 3

## Key metrics

| Scenario | State | Metric | Median | p95 | Max |
| --- | --- | --- | ---: | ---: | ---: |
| gateway-performance | many-bundled-plugins | Primary RSS | 1,975 MB | 2,085 MB | 2,098 MB |
| gateway-performance | many-bundled-plugins | Gateway RSS | 1,975 MB | 2,085 MB | 2,098 MB |
| gateway-performance | many-bundled-plugins | Max CPU | 266 % | 276 % | 277 % |
| gateway-performance | many-bundled-plugins | Event Loop Max | 45.2 ms | 53.8 ms | 54.7 ms |
| agent-cold-warm-message | mock-openai-provider | Primary RSS | 1,468 MB | 1,470 MB | 1,470 MB |
| agent-cold-warm-message | mock-openai-provider | Gateway RSS | 0 MB | 0 MB | 0 MB |
| agent-cold-warm-message | mock-openai-provider | Max CPU | 210 % | 213 % | 213 % |
| agent-cold-warm-message | mock-openai-provider | Agent Turn p95 | 8,502 ms | 8,714 ms | 8,737 ms |
| agent-cold-warm-message | mock-openai-provider | Cold Agent Turn | 8,516 ms | 8,741 ms | 8,766 ms |
| agent-cold-warm-message | mock-openai-provider | Warm Agent Turn | 8,236 ms | 8,260 ms | 8,263 ms |
| agent-cold-warm-message | mock-openai-provider | Pre-Provider p95 | 7,958 ms | 8,188 ms | 8,213 ms |

## Threshold violations

| Scenario | State | Metric | Actual | Threshold |
| --- | --- | --- | ---: | ---: |
| gateway-performance | many-bundled-plugins | peakRssMb | 1,954 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 2,218 | <= 1440 |
| gateway-performance | many-bundled-plugins | openclawOpenRequiredSpanCount | 1 | 0 |
| gateway-performance | many-bundled-plugins | peakRssMb | 2,098 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 2,359 | <= 1440 |
| gateway-performance | many-bundled-plugins | openclawOpenRequiredSpanCount | 1 | 0 |
| gateway-performance | many-bundled-plugins | peakRssMb | 1,975 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 2,228 | <= 1440 |
| gateway-performance | many-bundled-plugins | openclawOpenRequiredSpanCount | 1 | 0 |
| agent-cold-warm-message | mock-openai-provider | peakRssMb | 1,470 | <= 1150 |
| agent-cold-warm-message | mock-openai-provider | resourceByRole.command-tree.peakRssMb | 1,666 | <= 1400 |
| agent-cold-warm-message | mock-openai-provider | peakRssMb | 1,418 | <= 1150 |
| agent-cold-warm-message | mock-openai-provider | resourceByRole.command-tree.peakRssMb | 1,618 | <= 1400 |
| agent-cold-warm-message | mock-openai-provider | peakRssMb | 1,468 | <= 1150 |
| agent-cold-warm-message | mock-openai-provider | resourceByRole.command-tree.peakRssMb | 1,664 | <= 1400 |

## Records

| Scenario | State | Status | Failure |
| --- | --- | --- | --- |
| gateway-performance | many-bundled-plugins | FAIL |  |
| gateway-performance | many-bundled-plugins | FAIL |  |
| gateway-performance | many-bundled-plugins | FAIL |  |
| agent-cold-warm-message | mock-openai-provider | FAIL |  |
| agent-cold-warm-message | mock-openai-provider | FAIL |  |
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
- Lane repeat: 3
- Include filters: scenario:fresh-install,scenario:gateway-performance,scenario:bundled-plugin-startup,scenario:agent-cold-warm-message

## Source probes

Additional gateway boot, memory, plugin pressure, mock hello-loop, CLI startup, and SQLite state smoke numbers are in [source/index.md](source/index.md).

## Full diagnostic artifact

The complete Kova bundle remains in [Actions artifact 11872439019](https://github.com/openclaw/openclaw/actions/runs/38516324551/artifacts/11872439019); its checksum is published under the bundles directory.
