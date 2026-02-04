# NATIVE 핸들러

> 코드 동기 기준: 2026-02-03
> 원칙: 문서보다 코드가 우선입니다.

## 현재 구현
- native 핸들러는 Python 함수 직접 실행 경로를 제공하며 UTCP provider_type `native`를 처리합니다.
- 샌드박스/권한/정책 검증을 통해 실행 가능 여부가 결정됩니다.
- 고위험 코드 실행은 cloud_strict 정책에서 fail-closed로 차단됩니다.

## 프론트엔드 연결
- 사용자 도구 생성 시 provider_type `native`를 선택해 구성할 수 있습니다.

## 백엔드 연결
- 핸들러: `kait_os/tools/handlers/native/manifest.json`
- 샌드박스/보안: `kait_os/core/security/*`, `SECURITY_AND_CONFIGURATION.md`
- 실행기: `kait_os/tools/tool_executor.py`

## TODO
- [ ] Native 도구 권한 템플릿(파일/네트워크/프로세스) 세분화
- [ ] 실행 감사 로그 표준화(입력/출력/실패 원인)

## 관련 코드
- `kait_os/tools/handlers/native/manifest.json`
- `kait_os/tools/tool_executor.py`
- `docs/SECURITY_AND_CONFIGURATION.md`
