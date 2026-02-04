# 외부 연동 API (토큰 인증)

> 코드 동기 기준: 2026-02-03
> 원칙: 문서보다 코드가 우선입니다.

## 현재 구현
- 외부 클라이언트 연동은 사용자 API 키(`kait_dev_*`/`kait_live_*`) 발급 후 Bearer 인증으로 사용합니다.
- OpenAI 호환 엔드포인트(`/v1/chat/completions`, `/v1/models`)를 제공해 기존 OpenAI SDK와 연동 가능합니다.
- 요청의 `model` 필드는 AI Instance 이름/ID/`default`로 매핑되어 내부 파이프라인을 실행합니다.

## 프론트엔드 연결
- 외부 앱/CLI는 Studio가 아닌 독립 클라이언트로 `/v1/*` 호출 가능

## 백엔드 연결
- OpenAI compat 라우터: `kait_os/routers/system/openai_compat.py`
- API 키 CRUD: `kait_os/routers/system/api_keys.py`
- API 키 모델: `kait_os/db_models/api_keys.py`
- API 키 검증 서비스: `kait_os/services/system/api_key_service.py`

## TODO
- [ ] API 키 scope/쿼터/회전 정책 UI 및 정책 엔진 강화
- [ ] 외부 연동용 표준 예제(curl/python/js) 문서 보강

## 관련 코드
- `kait_os/routers/system/openai_compat.py`
- `kait_os/routers/system/api_keys.py`
- `kait_os/db_models/api_keys.py`
- `kait_os/services/system/api_key_service.py`
