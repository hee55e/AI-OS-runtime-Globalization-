# Preview

> 코드 동기 기준: 2026-02-03
> 원칙: 문서보다 코드가 우선입니다.

## 현재 구현
- PreviewRenderer는 image/video/audio/pdf/markdown 중심 미디어 미리보기를 제공합니다.
- 코드/앱 미리보기는 AppRenderer -> ArtifactRenderer(샌드박스 iframe) 경로를 사용합니다.
- 즉 “미디어 preview”와 “앱/코드 artifact preview”가 분리되어 있습니다.

## 프론트엔드 연결
- 미디어 preview: `components/viewport/slots/PreviewRenderer.tsx`
- 앱 preview: `components/viewport/slots/AppRenderer.tsx`, `ArtifactRenderer.tsx`

## 백엔드 연결
- Preview 슬롯 manifest: `kait_os/core/viewport/slots/preview/manifest.json`
- App/Artifact 결과는 세그먼트(`app`, `visual_block`)를 통해 전달됩니다.

## TODO
- [ ] PreviewRenderer의 executeAction mock을 실제 액션 API와 연결
- [ ] PDF/문서 미리보기 기능 고도화(페이지네이션/검색)

## 관련 코드
- `kait_os/kait_studio/src/components/viewport/slots/PreviewRenderer.tsx`
- `kait_os/kait_studio/src/components/viewport/slots/AppRenderer.tsx`
- `kait_os/kait_studio/src/components/viewport/slots/ArtifactRenderer.tsx`
- `kait_os/core/viewport/slots/preview/manifest.json`
