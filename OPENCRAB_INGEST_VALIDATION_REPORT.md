# OPENCRAB_INGEST_VALIDATION_REPORT (v0.1 candidate)

- Repository: `https://github.com/psa0426/korea-homeless-welfare-self-reliance-ontology-pack`
- Branch: `main`
- Path: `docs`
- Document limit: `200`
- Validation time: 2026-05-19 (session runtime)

## 0) 결론

**검증 중단(FAIL-BLOCKED)**

중단 사유:
1. OpenCrab ingest 히스토리 화면/엔드포인트 접근 불가
2. ingest 성공/실패 메타(문서 수, chunk 수, node/edge 생성 여부)를 확인할 수 없음

요청된 중단 조건 중 **`ingest 실패`에 준하는 운영상 실패(ingest 상태 확인 불가)** 로 판정.

---

## 1) 수행 내역

### A. OpenCrab 접속 시도
- `https://app.opencrab.ai` 접속 시도 → **실패**
  - 오류: `Navigation failed: net::ERR_NAME_NOT_RESOLVED`

### B. 대체 URL 탐색
- `https://opencrab.ai` 접속 성공 (랜딩 페이지)
  - 상태: 공개 랜딩/문의 페이지(Coming Soon 성격)
- `https://opencrab.ai/app` → 404 성격 페이지(未找到页面)
- `https://opencrab.ai/login` → 404 성격 페이지(未找到页面)
- `https://opencrab.ai/dashboard` → 404 성격 페이지(未找到页面)

### C. 로컬 포트 확인
- 현재 세션에서 OpenCrab 웹 앱 포트(예: 3000/8080 등) 리스닝 확인 실패
- 확인 가능한 것은 브라우저/시스템 기본 포트 위주

---

## 2) ingest History 확인 결과

요구 항목 | 결과
---|---
성공 여부 | 확인 불가
문서 수 | 확인 불가
chunk 수 | 확인 불가
node 생성 여부 | 확인 불가
edge 생성 여부 | 확인 불가

> 원인: OpenCrab 워크스페이스/대시보드에 진입하지 못해 ingest history 자체를 조회할 수 없음.

---

## 3) 실패 시 에러 원문 기록

- `Navigation failed: net::ERR_NAME_NOT_RESOLVED`
- OpenCrab 도메인 하위 경로(`/app`, `/login`, `/dashboard`)에서 대시보드 대신 미존재 페이지(未找到页面) 노출

---

## 4) 질의응답 품질 검증(요청 5문항)

현재 상태: **미실행**

사유: ingest 결과 인덱스(문서/chunk/node/edge) 확인 전제 충족 실패.

검증 불가 문항:
1. 팩 목적/제외 범위
2. 핵심 엔티티
3. 시설-서비스 관계
4. 사용 금지 자료
5. 최신성 관리 방법

---

## 5) docs 근거 참조 점검

현재 상태: **미실행(ingest 기반 답변 미확보)**

---

## 6) Marketplace 출시 전 보강 필요 문서(사전 제안)

※ ingest 복구 후 즉시 반영 권장

1. `docs/08_public_source_catalog.md`
   - 최신성 관리 규칙(검토 주기, 버전/고시일, 폐기/대체 추적) 명문화
2. `docs/07_data_quality_and_governance.md`
   - citation freshness SLA(예: 월 1회/분기 1회) 및 담당 역할 추가
3. `docs/01_scope_and_policy.md`
   - "내부자료 사용 금지"를 검색 질의에 잘 걸리도록 키워드형 금지문(국/영 혼용) 추가
4. `docs/03_relationships.md`
   - 시설-서비스 관계를 예시 트리플 3~5개 더 확장
5. `docs/02_core_entities.md`
   - 엔티티별 정의/동의어(국문 표기 변형) 추가로 검색 회수율 개선

---

## 7) 재검증 재개 조건

아래 중 하나가 제공되면 즉시 재실행 가능:
- 실제 OpenCrab 워크스페이스 URL(대시보드 URL)
- 접근 가능한 로그인 경로/테넌트 경로
- (로컬 실행형인 경우) OpenCrab UI 로컬 포트 정보

재개 시 본 보고서를 `v0.1-r1`로 갱신하여 ingest 수치 + 5문항 응답품질 + 근거참조 여부를 완결 보고함.
