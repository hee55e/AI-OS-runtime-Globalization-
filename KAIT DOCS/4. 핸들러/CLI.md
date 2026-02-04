# CLI 핸들러

> 코드 동기 기준: 2026-02-03
> 원칙: 문서보다 코드가 우선입니다.

## 현재 구현
- CLI 계열은 `cli` handler + terminal/run_command 계열 도구 조합으로 실행됩니다.
- 상태 유지 상호작용은 `terminal`(PTY), 단발 실행은 `run_command`가 담당합니다.
- 아직 `kait` 통합 CLI 부트스트랩 계약은 설계 문서 단계입니다.

## 프론트엔드 연결
- Terminal connector 패널에서 정책/허용 경로를 설정합니다.

## 백엔드 연결
- 핸들러 manifest: `kait_os/tools/handlers/cli/manifest.json`
- 터미널 핸들러: `kait_os/tools/handlers/terminal/terminal_handler.py`
- 커맨드 러너: `kait_os/tools/handlers/terminal/command_runner.py`

## TODO
- [ ] CLI bootstrap API와 `kait --json` 표준 계약 구현
- [ ] Primary AI 자동 조작 흐름과 CLI 세션 상태 연동

## 관련 코드
- `kait_os/tools/handlers/cli/manifest.json`
- `kait_os/tools/handlers/terminal/terminal_handler.py`
- `kait_os/utcp/categories/core/terminal.json`
- `docs/architecture/2026/KAIT_STUDIO_CLI_ARCHITECTURE.md`
