# OpenClaw Performance Report

- Lane: mock-provider
- Run: kova-261012-053437-59402e
- Generated: 2026-10-12T05:56:43.225Z
- Target: local-build:/home/runner/_work/openclaw/openclaw
- Statuses: FAIL: 6
- Repeat: 3

## Key metrics

| Scenario | State | Metric | Median | p95 | Max |
| --- | --- | --- | ---: | ---: | ---: |
| gateway-performance | many-bundled-plugins | Primary RSS | 1,788 MB | 1,842 MB | 1,848 MB |
| gateway-performance | many-bundled-plugins | Gateway RSS | 1,788 MB | 1,842 MB | 1,848 MB |
| gateway-performance | many-bundled-plugins | Max CPU | 238 % | 244 % | 244 % |
| gateway-performance | many-bundled-plugins | Event Loop Max | 73.4 ms | 74.6 ms | 74.7 ms |
| agent-cold-warm-message | mock-openai-provider | Primary RSS | 1,455 MB | 1,468 MB | 1,470 MB |
| agent-cold-warm-message | mock-openai-provider | Gateway RSS | 0 MB | 0 MB | 0 MB |
| agent-cold-warm-message | mock-openai-provider | Max CPU | 188 % | 195 % | 195 % |
| agent-cold-warm-message | mock-openai-provider | Agent Turn p95 | 8,236 ms | 8,327 ms | 8,337 ms |
| agent-cold-warm-message | mock-openai-provider | Cold Agent Turn | 7,527 ms | 7,783 ms | 7,811 ms |
| agent-cold-warm-message | mock-openai-provider | Warm Agent Turn | 8,273 ms | 8,356 ms | 8,365 ms |
| agent-cold-warm-message | mock-openai-provider | Pre-Provider p95 | 7,897 ms | 7,940 ms | 7,945 ms |

## Threshold violations

| Scenario | State | Metric | Actual | Threshold |
| --- | --- | --- | ---: | ---: |
| gateway-performance | many-bundled-plugins | peakRssMb | 1,769 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 2,084 | <= 1440 |
| gateway-performance | many-bundled-plugins | resourceByRole.status-cli.peakRssMb | 1,020 | <= 900 |
| gateway-performance | many-bundled-plugins | warmReadyMs | 15,181 | <= 15000 |
| gateway-performance | many-bundled-plugins | peakRssMb | 1,848 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 2,298 | <= 1440 |
| gateway-performance | many-bundled-plugins | peakRssMb | 1,788 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 2,108 | <= 1440 |
| gateway-performance | many-bundled-plugins | resourceByRole.status-cli.peakRssMb | 1,059 | <= 900 |
| agent-cold-warm-message | mock-openai-provider | peakRssMb | 1,455 | <= 1150 |
| agent-cold-warm-message | mock-openai-provider | resourceByRole.command-tree.peakRssMb | 1,557 | <= 1400 |
| agent-cold-warm-message | mock-openai-provider | peakRssMb | 1,470 | <= 1150 |
| agent-cold-warm-message | mock-openai-provider | resourceByRole.command-tree.peakRssMb | 1,571 | <= 1400 |
| agent-cold-warm-message | mock-openai-provider | peakRssMb | 1,254 | <= 1150 |

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
- Tested SHA: a5710f05606286ad6981fc1e514b595544906585
- Workflow ref: main
- Workflow SHA: a5710f05606286ad6981fc1e514b595544906585
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

The complete Kova bundle remains in [Actions artifact 11728507671](https://github.com/openclaw/openclaw/actions/runs/38208383728/artifacts/11728507671); its checksum is published under the bundles directory.
