# 그래프 바인딩 AI

> 코드 동기 기준: 2026-02-03
> 원칙: 문서보다 코드가 우선입니다.

## 현재 구현
- 현재는 “그래프 전용 바인딩 AI 모드”가 별도로 분리되어 있지 않습니다.
- 실제 동작은 공통 BindingModal + 기존 그래프 편집 기능 조합으로 처리됩니다.
- 그래프 조작은 바인딩 결과를 사람이 확인 후 적용하거나, UTCP graph_editor 도구를 통해 수행합니다.

## 프론트엔드 연결
- 그래프 편집기: `GraphEditor.tsx`
- 공통 바인딩 모달: `BindingModal.tsx`

## 백엔드 연결
- 그래프 편집 도구 카테고리: `kait_os/utcp/categories/ai_builder/graph_editor/`
- 노드/엣지 스키마 API: `kait_os/routers/system/node_schemas.py`, `kait_os/routers/execution/graph.py`

## TODO
- [ ] 그래프 액션(노드 추가/엣지 생성/조건식 수정)을 구조화 응답으로 직접 제안하는 전용 모드 추가
- [ ] 적용 전 diff 프리뷰 + 원클릭 승인 플로우 추가

## 관련 코드
- `kait_os/kait_studio/src/components/graph/GraphEditor.tsx`
- `kait_os/kait_studio/src/components/binding/BindingModal.tsx`
- `kait_os/utcp/categories/ai_builder/graph_editor/get_graph.json`
- `kait_os/routers/execution/graph.py`
