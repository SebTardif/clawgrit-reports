# OpenClaw Performance Report

- Lane: mock-provider
- Run: kova-261011-052701-1adb77
- Generated: 2026-10-11T05:46:50.307Z
- Target: local-build:/home/runner/_work/openclaw/openclaw
- Statuses: FAIL: 6
- Repeat: 3

## Key metrics

| Scenario | State | Metric | Median | p95 | Max |
| --- | --- | --- | ---: | ---: | ---: |
| gateway-performance | many-bundled-plugins | Primary RSS | 1,710 MB | 1,783 MB | 1,792 MB |
| gateway-performance | many-bundled-plugins | Gateway RSS | 1,710 MB | 1,783 MB | 1,792 MB |
| gateway-performance | many-bundled-plugins | Max CPU | 227 % | 232 % | 232 % |
| gateway-performance | many-bundled-plugins | Event Loop Max | 22.5 ms | 26.6 ms | 27 ms |
| agent-cold-warm-message | mock-openai-provider | Primary RSS | 1,352 MB | 1,383 MB | 1,386 MB |
| agent-cold-warm-message | mock-openai-provider | Gateway RSS | 0 MB | 0 MB | 0 MB |
| agent-cold-warm-message | mock-openai-provider | Max CPU | 191 % | 200 % | 201 % |
| agent-cold-warm-message | mock-openai-provider | Agent Turn p95 | 6,664 ms | 7,188 ms | 7,246 ms |
| agent-cold-warm-message | mock-openai-provider | Cold Agent Turn | 6,474 ms | 7,192 ms | 7,272 ms |
| agent-cold-warm-message | mock-openai-provider | Warm Agent Turn | 6,682 ms | 6,745 ms | 6,752 ms |
| agent-cold-warm-message | mock-openai-provider | Pre-Provider p95 | 6,416 ms | 6,924 ms | 6,981 ms |

## Threshold violations

| Scenario | State | Metric | Actual | Threshold |
| --- | --- | --- | ---: | ---: |
| gateway-performance | many-bundled-plugins | peakRssMb | 1,710 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 2,009 | <= 1440 |
| gateway-performance | many-bundled-plugins | peakRssMb | 1,678 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 1,979 | <= 1440 |
| gateway-performance | many-bundled-plugins | resourceByRole.status-cli.peakRssMb | 1,017 | <= 900 |
| gateway-performance | many-bundled-plugins | peakRssMb | 1,792 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 2,092 | <= 1440 |
| agent-cold-warm-message | mock-openai-provider | peakRssMb | 1,309 | <= 1150 |
| agent-cold-warm-message | mock-openai-provider | resourceByRole.command-tree.peakRssMb | 1,410 | <= 1400 |
| agent-cold-warm-message | mock-openai-provider | peakRssMb | 1,386 | <= 1150 |
| agent-cold-warm-message | mock-openai-provider | resourceByRole.command-tree.peakRssMb | 1,488 | <= 1400 |
| agent-cold-warm-message | mock-openai-provider | peakRssMb | 1,352 | <= 1150 |
| agent-cold-warm-message | mock-openai-provider | resourceByRole.command-tree.peakRssMb | 1,454 | <= 1400 |

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
- Tested SHA: 9a62c5b5cd2eb98a47e7091dfa1484cfe8dd7809
- Workflow ref: main
- Workflow SHA: 9a62c5b5cd2eb98a47e7091dfa1484cfe8dd7809
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

The complete Kova bundle remains in [Actions artifact 11693413165](https://github.com/openclaw/openclaw/actions/runs/38114691829/artifacts/11693413165); its checksum is published under the bundles directory.
