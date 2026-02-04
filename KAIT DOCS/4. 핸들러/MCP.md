# MCP 핸들러

> 코드 동기 기준: 2026-02-03
> 원칙: 문서보다 코드가 우선입니다.

## 현재 구현
- MCP 핸들러는 사용자별 MCP 서버를 연결하고 도구를 검색/실행하는 브리지입니다.
- 테스트 후 변환된 MCP 도구를 사용자 도구(UTCP 형태)로 등록할 수 있습니다.
- 멀티테넌트 격리를 위해 사용자/세션 단위 프로세스 풀이 사용됩니다.

## 프론트엔드 연결
- MCPServersPanel/ConnectorsModal에서 서버 추가와 테스트를 수행합니다.

## 백엔드 연결
- 핸들러: `kait_os/tools/handlers/mcp/`
- MCP API: `kait_os/routers/tools/mcp_tools.py`
- 보안 문서: `docs/SECURITY_AND_CONFIGURATION.md` Section 8

## TODO
- [ ] MCP 서버별 헬스체크/자동 재연결 정책 UI 제공
- [ ] MCP 도구 권한 정책(allowlist) 세분화

## 관련 코드
- `kait_os/tools/handlers/mcp/manifest.json`
- `kait_os/routers/tools/mcp_tools.py`
- `docs/SECURITY_AND_CONFIGURATION.md`
