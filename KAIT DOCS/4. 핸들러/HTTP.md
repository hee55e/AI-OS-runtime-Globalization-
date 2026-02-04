# HTTP 핸들러

> 코드 동기 기준: 2026-02-03
> 원칙: 문서보다 코드가 우선입니다.

## 현재 구현
- HTTP 계열은 `http`, `http_stream`, `sse`, `websocket`, `graphql`, `grpc` 핸들러로 분리되어 있습니다.
- UTCP provider_type에 따라 대응 핸들러가 선택되어 실행됩니다.
- 도구 입력/출력은 JSON schema를 통해 검증 및 정규화됩니다.

## 프론트엔드 연결
- Tool Builder에서 provider_type을 선택하면 해당 스키마 필드가 노출됩니다.

## 백엔드 연결
- 핸들러 디렉터리: `kait_os/tools/handlers/http`, `http_stream`, `sse`, `websocket`, `graphql`, `grpc`
- 핸들러 레지스트리: `kait_os/tools/handlers/registry.py`
- 실행기: `kait_os/tools/tool_executor.py`

## TODO
- [ ] 핸들러별 타임아웃/재시도/서킷브레이커 기본 정책 문서화
- [ ] 스트리밍 응답 표준 이벤트 포맷 통일

## 관련 코드
- `kait_os/tools/handlers/http/manifest.json`
- `kait_os/tools/handlers/http_stream/manifest.json`
- `kait_os/tools/handlers/sse/manifest.json`
- `kait_os/tools/handlers/websocket/manifest.json`
- `kait_os/tools/handlers/graphql/manifest.json`
- `kait_os/tools/handlers/grpc/manifest.json`
