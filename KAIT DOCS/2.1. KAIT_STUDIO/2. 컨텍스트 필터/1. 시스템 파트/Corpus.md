# 컨텍스트 필터: Corpus

> 코드 동기 기준: 2026-02-03
> 원칙: 문서보다 코드가 우선입니다.

## 현재 구현
- `corpus_filter`는 시스템 프롬프트 파트에 코퍼스/지식 문맥을 삽입하는 역할입니다.
- 코퍼스 데이터는 `NeuralImprint` 모델 기반이며 검색/인덱싱 훅과 연결됩니다.
- LLM 컨텍스트에서는 텍스트 요약 형태로 주입되고, 원문 저장소는 별도 유지됩니다.

## 프론트엔드 연결
- Corpus 뷰포트/관리 UI는 Viewport 타입(`corpus`)과 데이터 패널에서 접근합니다.

## 백엔드 연결
- 필터 구현: `kait_os/core/context/filters/system_prompt_parts/base/corpus_filter/`
- 코퍼스 라우터: `kait_os/routers/data/corpus.py`
- DB 모델: `kait_os/db_models/corpus.py`

## TODO
- [ ] 코퍼스 필터 주입량(토큰 예산) 자동 최적화 옵션 제공
- [ ] 코퍼스 스코프(user/system/registry) 선택 UI 강화

## 관련 코드
- `kait_os/core/context/filters/system_prompt_parts/base/corpus_filter/corpus_filter.py`
- `kait_os/routers/data/corpus.py`
- `kait_os/db_models/corpus.py`
