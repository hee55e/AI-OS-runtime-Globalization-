# Primary AI

> 코드 동기 기준: 2026-02-03
> 원칙: 문서보다 코드가 우선입니다.

## 현재 구현
- 현재 DB/스키마에는 `primary_ai_instance_id` 필드가 없습니다.
- Binding AI 기본 선택은 `BindingService._get_user_default_ai()`에서 “최근 생성 AI 1개”를 사용합니다.
- Studio 사이드바에는 즐겨찾기(favorites)는 있지만 “Primary AI 고정” UI는 아직 없습니다.
- 즉, 지금의 Primary AI는 제품 컨셉 단계이며 코드 레벨 강제 단일 기본 AI는 미구현입니다.

## 프론트엔드 연결
- AI 목록/즐겨찾기: `kait_os/kait_studio/src/components/sidebar/Sidebar.tsx`
- Binding 모달의 AI 선택: `kait_os/kait_studio/src/components/binding/BindingModal.tsx`

## 백엔드 연결
- 기본 AI fallback: `kait_os/core/binding/service.py`
- AI 모델/스키마: `kait_os/db_models/cognitive_architecture.py`, `kait_os/schemas/cognitive_architecture.py`

## TODO
- [ ] 사용자 단위 `primary_ai_instance_id` 저장/검증(본인 소유 + 단일값) 추가
- [ ] Surface별 override(갤러리/브라우저/그래프 등) 우선순위 해석기 추가
- [ ] UI에서 Primary 지정/교체/삭제 보호 플로우 추가

## 관련 코드
- `kait_os/core/binding/service.py`
- `kait_os/db_models/cognitive_architecture.py`
- `kait_os/kait_studio/src/components/sidebar/Sidebar.tsx`
- `docs/architecture/2026/PRIMARY_AI_ARCHITECTURE.md`
