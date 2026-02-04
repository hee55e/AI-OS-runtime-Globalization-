# 뷰포트 바인딩 AI

> 코드 동기 기준: 2026-02-03
> 원칙: 문서보다 코드가 우선입니다.

## 현재 구현
- 브라우저 뷰포트는 포커스 요소/선택 텍스트/페이지 컨텍스트를 수집해 Binding 요청에 포함합니다.
- 멀티모달 첨부(이미지/스크린샷)도 함께 전송할 수 있으며 ask 모드로 질의형 응답이 가능합니다.
- 서버 측에서도 Viewport 컨트롤러를 통해 실시간 컨텍스트 pull을 시도합니다.

## 프론트엔드 연결
- 브라우저 컨텍스트 수집: `BindingProvider.tsx` + Electron bridge
- 뷰포트 렌더러: `components/viewport/slots/browser/ElectronBrowserRenderer.tsx`

## 백엔드 연결
- Binding 실시간 컨텍스트 pull: `BindingService._fetch_realtime_context()`
- 브라우저 제어 라우터: `kait_os/routers/viewport/electron_browser.py`

## TODO
- [ ] 터미널/파일/코퍼스 뷰포트용 컨텍스트 어댑터 표준화
- [ ] 뷰포트 타입별 generationMode 기본값 정책 정리

## 관련 코드
- `kait_os/kait_studio/src/components/binding/BindingProvider.tsx`
- `kait_os/kait_studio/src/components/viewport/slots/browser/ElectronBrowserRenderer.tsx`
- `kait_os/core/binding/service.py`
- `kait_os/routers/viewport/electron_browser.py`
