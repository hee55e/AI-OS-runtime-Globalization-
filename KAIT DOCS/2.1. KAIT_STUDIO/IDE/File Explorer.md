# File Explorer

> 코드 동기 기준: 2026-02-03
> 원칙: 문서보다 코드가 우선입니다.

## 현재 구현
- File Explorer는 로컬 파일시스템을 탐색/편집하는 UI이며 컨텍스트 메뉴 기반 CRUD를 지원합니다.
- 백엔드 API는 허용 경로 검사(`_is_path_allowed`)를 통해 경로 탈출을 차단합니다.
- AI별 VFS(`/api/v1/vfs/{ai_id}`)와 로컬 파일 브라우저(`/api/v1/file-browser/*`)는 별도 경로입니다.

## 프론트엔드 연결
- 뷰: `components/sidebar/FileExplorerView.tsx`
- VFS 스토어: `features/vfs/store/useVFSStore.ts`

## 백엔드 연결
- 로컬 파일 브라우저 라우터: `kait_os/routers/data/file_browser.py`
- AI VFS 라우터: `kait_os/routers/vfs.py`
- AI VFS 어댑터: `kait_os/core/vfs/adapters/ai_vfs.py`

## TODO
- [ ] AI별 워크스페이스 전용 필터링 정책(루트 잠금) UI 강화
- [ ] 대규모 디렉터리 탐색 성능 최적화(증분 로딩/인덱스 검색) 확장

## 관련 코드
- `kait_os/kait_studio/src/components/sidebar/FileExplorerView.tsx`
- `kait_os/routers/data/file_browser.py`
- `kait_os/routers/vfs.py`
- `kait_os/core/vfs/adapters/ai_vfs.py`
