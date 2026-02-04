# 갤러리 바인딩 AI

> 코드 동기 기준: 2026-02-03
> 원칙: 문서보다 코드가 우선입니다.

## 현재 구현
- GalleryModal은 아이템 선택/첨부 후 바인딩 AI 질의(`useGalleryAI`)를 실행할 수 있습니다.
- 이미지/비디오 자산은 URL 참조로 관리되고 필요 시 첨부 형태로 ChatMini에 전달됩니다.
- 실시간 자산 생성 이벤트(`asset_created`, `media_generated`)를 받아 목록을 갱신합니다.

## 프론트엔드 연결
- 갤러리 모달: `components/gallery/GalleryModal.tsx`
- 갤러리 AI 훅: `hooks/useGalleryAI.ts`
- 이미지 편집 모달: `components/gallery/ImageEditModal.tsx`

## 백엔드 연결
- 갤러리 API: `kait_os/routers/data/gallery.py`
- 이미지/비디오 매니저: `kait_os/modules/image_manager`, `kait_os/modules/video_manager`

## TODO
- [ ] 오디오 자산(`media_type=audio`) 조회/편집/바인딩 지원 추가
- [ ] 갤러리 AI 질의 결과를 그래프/도구 제작 액션으로 이어주는 단축 플로우 추가

## 관련 코드
- `kait_os/kait_studio/src/components/gallery/GalleryModal.tsx`
- `kait_os/kait_studio/src/hooks/useGalleryAI.ts`
- `kait_os/routers/data/gallery.py`
