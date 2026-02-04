# 모달 바인딩 AI

> 코드 동기 기준: 2026-02-03
> 원칙: 문서보다 코드가 우선입니다.

## 현재 구현
- BindingModal은 ask/replace/append 모드를 제공하고 AI 선택 + 첨부 + 스트리밍 결과 표시를 지원합니다.
- 브라우저 컨텍스트 메뉴(Electron IPC) 이벤트와 키보드 단축키(Ctrl+K)로 호출됩니다.
- 모달 레벨에서 맥락 스냅샷을 붙여 요청을 구성하며 적용은 사용자가 최종 결정합니다.

## 프론트엔드 연결
- Provider: `BindingProvider.tsx`
- 모달: `BindingModal.tsx`
- 키보드/적용 훅: `useBindingKeyboard.ts`, `useBindingApply.ts`

## 백엔드 연결
- fill API 라우터: `kait_os/routers/binding/binding.py`
- 서비스 처리: `kait_os/core/binding/service.py`

## TODO
- [ ] 도구 제작/프로세서 제작 등 “구조화 생성” 전용 출력 포맷(JSON schema) 지원
- [ ] 모달 결과를 그래프/도구 편집기로 바로 라우팅하는 액션 버튼 세트 추가

## 관련 코드
- `kait_os/kait_studio/src/components/binding/BindingProvider.tsx`
- `kait_os/kait_studio/src/components/binding/BindingModal.tsx`
- `kait_os/routers/binding/binding.py`
