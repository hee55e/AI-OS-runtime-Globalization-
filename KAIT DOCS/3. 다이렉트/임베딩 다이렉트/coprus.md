# 임베딩 다이렉트와 Corpus

> 코드 동기 기준: 2026-02-03
> 원칙: 문서보다 코드가 우선입니다.

## 현재 구현
- 임베딩 생성 자체는 `embedding_direct`가 담당하고 현재 provider는 `openai` 구현체가 존재합니다.
- 코퍼스(NeuralImprint) 인덱싱은 memory worker가 문서 텍스트를 벡터화해 Chroma 컬렉션에 저장합니다.
- RAG 조회는 `rag_direct`(chroma/gemini/postgres_fts) 경로와 결합해 사용할 수 있습니다.

## 프론트엔드 연결
- Corpus 관련 UI는 뷰포트/필터/검색 패널 조합으로 노출됩니다.

## 백엔드 연결
- Embedding providers: `kait_os/core/embedding_direct/providers/`
- Memory worker: `kait_os/workers/memory_worker.py`
- Chroma store: `kait_os/core/memory/store/chroma_store.py`
- Corpus 모델: `kait_os/db_models/corpus.py`

## TODO
- [ ] 임베딩 provider 다중화(비용/품질 선택) 지원
- [ ] 코퍼스 인덱스 상태(최신화 지연/실패) 대시보드 제공

## 관련 코드
- `kait_os/core/embedding_direct/providers/openai`
- `kait_os/workers/memory_worker.py`
- `kait_os/core/memory/store/chroma_store.py`
- `kait_os/db_models/corpus.py`
