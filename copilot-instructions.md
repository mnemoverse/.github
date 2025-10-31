# Copilot Instructions — Mnemoverse (Org Level)

Concise, actionable rules for AI coding agents across this workspace. Defer to repo-level instructions when present (e.g., SmartKeys, Mnemoverse Arch).

## Big Picture
- Multi-repo system: agent core (`mnemoverse-arch`), MCP servers (`github-mcp-server`, `gitea-api`, `mcp-docs-server`), UIs (`mnemoverse-chat-ui`, `mnemoverse-web-client`), docs (`mnemoverse-docs`), native macOS app (`smartkeys`).
- Memory layer: Knowledge Delta (KD) API lives in `mnemoverse-arch` and is consumed by other services via HTTP.
- Local orchestration: many repos ship `workspace.sh`/`dev.sh` targets (`dev`, `mcp`, `web`, `docs`); VS Code Tasks are pre-wired.

## High-Signal Repos
- `mnemoverse-arch` (Python/FastAPI): KD client facade (use this import): `from mnemoverse_arch.core.kd_client import KDRestClient, create_kd_client, MockKDClient`. KD base path: `/api/v1/knowledge-delta` (health, memory, search, insights, evolution, stats). ENV: `KD_BASE_URL`, `KD_API_KEY`, `KD_TIMEOUT_MS`, and KE thresholds (`KE_BRIEF_MIN`, `KE_STANDARD_MIN`, `KE_SKIP_THRESHOLD`). Keep green: `tests/test_kd_client.py`, `tests/test_knowledge_evolution_module.py`, `tests/security/`.
- `smartkeys` (Swift/macOS-only): requires macOS 13+ and Xcode 15+. Build with `xcodebuild` (allow ~180s). Scripts: `./scripts/ci_local.sh`, `./scripts/dev_run.sh`. Key files: `SmartKeysDevApp.swift`, `EventTapController.swift`, `PermissionManager.swift`, `RingBuffer.swift`. Perf budget p95 < 8ms.
- MCP servers: `github-mcp-server` (Go), `gitea-api` (Python), `mcp-docs-server` (Node/TS). Start via repo `dev.sh mcp` or `workspace.sh dev`; check `./workspace.sh status`.
- UIs & Docs: `mnemoverse-chat-ui`/`mnemoverse-web-client` (Next/Vite); `mnemoverse-docs` (VitePress, architecture under `docs/architecture/`).

## Conventions
- Imports: prefer package-root imports (e.g., `mnemoverse_arch.*`), keep KD client facade stable.
- Logging (Python): structlog with `request_id`, `agent_id`, `user_id` when available.
- Secrets/config: never commit; read from ENV. Security toggles for KD API exist (e.g., `KD_ENABLE_ACL`, `KD_ENABLE_RATE_LIMITING`).
- Contracts: when APIs change, update contracts and run consumer/provider tests (see `mnemoverse-docs/docs/architecture/contracts/`).
- SmartKeys commits: include `SWK-XXX` IDs and follow its repo instructions.

## Core Workflows
- KD/KE tests (arch):
  - `pytest -q tests/test_kd_client.py tests/test_knowledge_evolution_module.py tests/security`
  - Subset: `pytest -q -k "kd or knowledge_evolution"`
- SmartKeys (macOS):
  - Build: `xcodebuild -project macos/SmartKeysDev/SmartKeysDev/SmartKeysDev.xcodeproj -scheme SmartKeysDev -configuration Debug -destination 'platform=macOS' build`
  - Run: `./scripts/dev_run.sh` (grant Accessibility)
- UIs/Docs: `npm install && npm run dev|build|preview` in the repo.
- MCP servers: `./workspace.sh dev` or `./dev.sh mcp`; logs via `./workspace.sh logs`.

## Do / Don’t
- Do: move magic numbers to config/ENV; add/adjust tests with behavior changes; respect SmartKeys’ macOS constraints.
- Don’t: break KD endpoints/KE contracts without spec update; refactor unrelated legacy suites in KD/KE-scoped PRs; log/commit sensitive data.

## Pointers
- KD config: `src/mnemoverse_arch/configs/providers.yaml`
- KD/KE code: `src/mnemoverse_arch/core/`, `src/mnemoverse_arch/modules/`
- SmartKeys Swift: `macos/SmartKeysDev/`, `core/`, `scripts/` (see repo instructions)
- Evaluation & TDD: `mnemoverse-docs/docs/architecture/evaluation/`, draft: `mnemoverse-docs/drafts/ai-dev/ai-tdd.md`

If anything is outdated or missing, open a small PR here and link to the authoritative repo-level guide.