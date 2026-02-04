# Diff

> 코드 동기 기준: 2026-02-03
> 원칙: 문서보다 코드가 우선입니다.

## 현재 구현
- 파일 Diff는 FileRenderer의 Monaco DiffEditor(Inline)로 렌더링됩니다.
- 채팅 툴 블록에서는 `react-diff-view` 기반 DiffStyle 컴포넌트로 변경점을 표시합니다.
- Diff 데이터는 뷰포트 state(`diff`, `diffStats`)로 전달되어 저장/해제 토글이 가능합니다.

## 프론트엔드 연결
- 파일 뷰포트 Diff: `components/viewport/slots/FileRenderer.tsx`
- 채팅 도구 Diff: `components/chat/blocks/tool_call/DiffStyle.tsx`

## 백엔드 연결
- 도구 결과 세그먼트는 `tool_output`으로 전달되며 diff 문자열은 도구 구현에 따라 생성됩니다.

## TODO
- [ ] Diff 상태를 세션 히스토리와 연동해 재접속 시 복원
- [ ] 다중 파일 변경 배치 Diff 뷰 제공

## 관련 코드
- `kait_os/kait_studio/src/components/viewport/slots/FileRenderer.tsx`
- `kait_os/kait_studio/src/components/chat/blocks/tool_call/DiffStyle.tsx`
- `kait_os/core/common/segment.py`
