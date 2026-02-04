# MCP

> 코드 동기 기준: 2026-02-03
> 원칙: 문서보다 코드가 우선입니다.

## 현재 구현
- MCP 연동은 전용 패널 + 커넥터 경로를 통해 수행하며 도구는 UTCP로 변환/등록 가능합니다.
- 테스트 API(`/api/v1/tools/mcp/test`)로 서버 연결과 도구 목록 변환을 검증할 수 있습니다.
- 멀티테넌트 격리는 사용자/세션별 프로세스 풀 정책을 따릅니다.

## 프론트엔드 연결
- MCP 패널: `components/mcp/MCPServersPanel.tsx`
- 커넥터 모달(커스텀 MCP): `components/connectors/ConnectorsModal.tsx`

## 백엔드 연결
- MCP 도구 라우터: `kait_os/routers/tools/mcp_tools.py`
- MCP 핸들러: `kait_os/tools/handlers/mcp/`
- 보안/격리 정책 문서: `docs/SECURITY_AND_CONFIGURATION.md`

## TODO
- [ ] MCP 패널과 커넥터 패널의 중복 플로우 통합
- [ ] MCP 서버 상태(헬스/지연/도구 수) 실시간 카드 제공

## 관련 코드
- `kait_os/kait_studio/src/components/mcp/MCPServersPanel.tsx`
- `kait_os/routers/tools/mcp_tools.py`
- `kait_os/tools/handlers/mcp`
- `docs/SECURITY_AND_CONFIGURATION.md`
