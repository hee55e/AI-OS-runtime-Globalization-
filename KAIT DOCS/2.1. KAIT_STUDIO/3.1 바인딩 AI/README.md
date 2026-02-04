# 바인딩 AI 개요

> 코드 동기 기준: 2026-02-03
> 원칙: 문서보다 코드가 우선입니다.

## 현재 구현
- Binding AI는 “대화”가 아니라 “현재 맥락에 맞는 값/응답 생성”에 초점을 둔 Layer 6 인터페이스입니다.
- 공식 엔드포인트는 `/api/v1/binding/fill`, `/api/v1/binding/fill/stream`입니다.
- 모드 필드는 `fill|action|suggest`를 받지만 현재 구현은 `fill`만 동작합니다.
- AI 미지정 시 기본 선택은 최신 생성 AI 1개 fallback입니다.

## 프론트엔드 연결
- 전역 Provider: `components/binding/BindingProvider.tsx`
- 입력 모달: `components/binding/BindingModal.tsx`
- 클라이언트 훅: `hooks/useBinding.ts`

## 백엔드 연결
- 요청 스키마: `kait_os/core/binding/request.py`
- 서비스: `kait_os/core/binding/service.py`
- 라우터: `kait_os/routers/binding/binding.py`

## TODO
- [ ] action/suggest 모드 구현 및 프론트 UX 연결
- [ ] Primary AI 해석 우선순위(요청/세션/서피스/primary) 정식 도입

## 관련 코드
- `kait_os/core/binding/request.py`
- `kait_os/core/binding/service.py`
- `kait_os/routers/binding/binding.py`
- `kait_os/kait_studio/src/components/binding/BindingProvider.tsx`
