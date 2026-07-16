# 심우현 (SIM WOOHYUN)
> **AI 에이전트 엔지니어 x 풀스택 엔지니어 (AI Agent x Fullstack Engineer)**  
> [심우현 개발자 포트폴리오](https://simwoohyun.vercel.app) | wmr06244@naver.com

제한된 자원(리소스 제약, 비용 한계, 네트워크 지연) 속에서 합리적인 설계 결정(Trade-off)을 내리고 비즈니스 신뢰성을 확보하는 것을 최우선으로 생각하는 엔지니어입니다.

비결정적인 LLM의 불안정성(환각, 루프 비용, 응답 지연)을 시스템 및 통계 지표(RAGAS)로 통제하는 AI 에이전트 아키텍처 설계와, 프론트엔드-백엔드 간의 데이터 정밀 동기화 및 테스트 결정성 확보에 깊은 관심을 가지고 해결해 나가고 있습니다.

---

## 🛠️ Tech Stack & Competencies

| 분류 | 기술 스택 |
| :--- | :--- |
| **AI & RAG** | `LangGraph (Multi-Agent)`, `LangChain`, `Pinecone (Vector DB)`, `SQLite FTS5`, `BM25`, `RAGAS Evaluation`, `OpenAI API` |
| **Frontend & UX** | `React`, `TypeScript`, `Next.js`, `Zustand`, `TanStack Query`, `React Hook Form`, `Tailwind CSS`, `Playwright (E2E)` |
| **Backend & Data** | `Node.js`, `FastAPI`, `Express`, `PostgreSQL`, `MySQL`, `TypeORM`, `Zod`, `Vitest` |
| **DevOps & Infra** | `Docker`, `Docker Compose`, `GitHub Actions (CI/CD)`, `Vercel`, `Render` |

---

## 📂 Featured Projects

| Project | Description | Links |
| :--- | :--- | :--- |
| **TechDocs** | 멀티 에이전트 RAG 기반 특허 문서 AI 검색 서비스 | [GitHub](https://github.com/neverleaveualong/TechDocs) • [Demo](https://techdocs-app.vercel.app) |
| **TechLens** | 특허 공공데이터 기반 검색·분석 서비스 | [GitHub](https://github.com/Douzone-Keycom-Internship-woohyun-2025) • [Demo](https://frontend-techlens.vercel.app/login) |
| **Playce** | 위치 기반 스포츠 중계 장소 검색 서비스 | [GitHub](https://github.com/neverleaveualong/PlayceV) • [Demo](https://playce-app.vercel.app) |
| **HyperStar** | AI 인플루언서 마케팅 B2B SaaS (CES 2026 시연 제품) | *Source Private (CES 2026)* |

---

## 🔍 Project Details & Troubleshooting

### 1️⃣ TechDocs (자율 수집 RAG 특허 검색 서비스)
> 사용자의 질문 의도를 다각도로 분석하여 특허 문서를 검색하고, 필요시 자율적으로 공공 데이터를 인제스천하여 신뢰성 있는 답변을 생성하는 RAG 시스템입니다.

*   **Stack**: `FastAPI`, `LangGraph`, `LangChain`, `Pinecone`, `SQLite (FTS5)`, `SSE Streaming`, `RAGAS`, `Docker`
*   **핵심 구현 요약**: LangGraph 기반의 순환형 멀티 에이전트 오케스트레이션, 실시간 추론 타임라인 가시화를 위한 FastAPI SSE 스트리밍 구축, Pinecone Vector Search와 BM25 키워드 검색을 병합한 하이브리드 검색 구현.

#### 🛠️ 핵심 설계 결정 및 트러블슈팅 (Troubleshooting)

##### ① Render 512MB RAM 인프라 제약 극복을 위한 형태소 분석기(Kiwi) 배제
*   **문제 정의**: 저사양 배포 서버 환경(Render.com 프리티어 512MB RAM)에서 한국어 형태소 분석기인 Kiwi C++ 모듈 로드 시, 메모리 오버플로우로 인한 컨테이너 크래시(OOM Killed) 및 스레드 데드락 장애 지속 발생.
*   **대안 비교 및 채택**:
    *   *대안 A (서버 스케일업)*: 비용이 크게 증가함 (기각).
    *   *대안 B (KoNLPy/Mecab)*: Java Virtual Machine(JVM) 구동을 위한 메모리 베이스라인이 300MB를 상회해 FastAPI 구동 불가 (기각).
    *   *대안 C (정규식 기반 조사 필터링 스태머)*: 추가 메모리 사용량 0MB. 형태소 분석 정확도 하락 리스크 (선택).
*   **결과 검증**: C안을 채택해 사용자 정의 형태소 원형 매칭 알고리즘을 구현하였으며, RAGAS 정량적 평가 결과 기존 Kiwi 적용 대비 검색 정확도 하락이 **2% 미만**임을 확인하여 저사양 사양 환경에서 100% 가용성을 확보함.

##### ② Pinecone 네트워크 지연 및 인덱스 빌드 병목을 해결한 SQLite FTS5 로컬 검색 우회
*   **문제 정의**: 검색 요청 시마다 Pinecone 벡터스토어에서 전체 원본 텍스트를 네트워크로 긁어와 메모리 단에서 BM25 인덱스를 동적으로 생성하던 방식에서 **평균 5초 이상의 네트워크 지연 및 API 타임아웃** 발생.
*   **대안 비교 및 채택**:
    *   *대안 A (Elasticsearch 클러스터 도입)*: 가장 대중적이나, 최소 1GB 이상의 백그라운드 메모리가 필요해 리소스 제약 상 불가 (기각).
    *   *대안 B (SQLite FTS5 가상 테이블 로컬 FTS)*: 메모리 부담이 거의 없고 인프로세스로 즉시 조회가 가능하지만, 다중 서버(Scale-out) 환경 진입 시 데이터 동기화 이슈 존재 (선택).
*   **결과 검증**: SQLite FTS5 가상 테이블을 구축하여 로컬 하이브리드 검색 구조로 전환, 후속 검색 레이턴시를 **0.1초 내외**로 50배 단축함. 서버 확장 시에는 Redisearch로 마이그레이션할 아키텍처 이정표 수립.

##### ③ 비결정적 에이전트 무한 루프로 인한 API 비용 폭탄 제어
*   **문제 정의**: RAG 품질 평가(RAGAS) 시, 데이터 부족으로 인한 검색 신뢰도 저하 상태에서 Supervisor 에이전트가 `INGEST`와 `SEARCH` 단계를 판단 루프로 인식하여 동일 구간을 무한 반복 호출하며 불필요한 OpenAI API 비용을 소모함.
*   **대안 및 해결**: 에이전트 상태 관리에 `max_iterations = 4` 리밋을 명시적으로 설계하고, LLM 판단 실패에 대응하는 규칙 기반 **Fallback Decision 레이어**를 이중으로 마련하여 예외 조건 발생 시 무한 비용 유출을 원천 방어함.

---

### 2️⃣ TechLens (특허 공공데이터 기반 검색·분석 서비스)
> KIPRIS API 데이터를 배치 수집/정제하고 연도별 출원 추이, 등록 상태 등을 시각화하여 제공하는 대시보드 플랫폼입니다.

*   **Stack**: `React`, `TypeScript`, `Express`, `PostgreSQL`, `Zod`, `Chart.js`
*   **핵심 구현 요약**: JWT (Access/Refresh) 기반 보안 인증, 통계 처리를 위한 DB 스키마 설계, Controller-Service-Repository 패턴 적용을 통한 비즈니스 로직 격리.

#### 🛠️ 핵심 설계 결정 및 트러블슈팅 (Troubleshooting)

##### ① Axios API 호출 예외 시 인증 서비스 키(Service Key) 노출 보안 리스크 해결
*   **문제 정의**: KIPRIS 공공 API 호출 실패 시 발생하는 Axios 에러 객체의 `config` 프로퍼티 내부 URL에 **비공개 API 서비스 키**가 노출되어, 서버 스택트레이스 및 외부 모니터링 로그에 전송되는 기밀 유출 보안 취약점 발견.
*   **대안 및 해결**: 백엔드 API 서비스 레이어의 모든 외부 요청 catch 블록에 Axios Error 판정 조건식을 적용하여, 예외 버블링 전에 `err.config` 데이터를 즉시 `undefined`로 초기화하도록 가로채기(Interceptor) 보안 레이어 추가.
*   **결과 검증**: 외부 연동 장애 시 로그 모니터링 툴에 API Key 평문 노출 가능성을 0%로 통제함.

##### ② 외부 API 레이턴시 병목 우회를 위한 Idempotent 배치 파이프라인 및 Zod 검증 설계
*   **문제 정의**: KIPRIS API의 엄격한 일일 호출 쿼터 제한 및 느린 레이턴시(호출당 3초 이상)로 인해 사용자 요청 마다 대시보드를 실시간 쿼리 시 타임아웃 장애 빈발. 공공데이터 특유의 Null 값 유실 및 불규칙한 데이터 포맷으로 인한 Postgres Insert 실패.
*   **대안 및 해결**: 
    1.  **배치 격리**: 실시간 조회를 백그라운드 동기화 스케줄러로 격리하고, DB 중복 인서트 에러 방지를 위해 PostgreSQL의 `ON CONFLICT (application_number) DO UPDATE` 구문을 사용해 멱등성(Idempotency)을 보장함.
    2.  **Zod 필터링**: XML-to-JSON 파싱 과정에서 들어오는 유실되거나 비정상적인 데이터 규격을 검증하기 위해 **Zod 스키마 검증** 레이어를 데이터 인제스천 진입점에 격리 배치하여 적재 안정성 확보.
*   **결과 검증**: 실시간 API 호출 병목을 차단하여 대시보드 로딩 속도를 **0.1초 내외**로 개선하고 데이터 적재 무결성을 100% 유지함.

---

### 3️⃣ Playce (위치 기반 스포츠 중계 장소 검색 서비스)
> 사용자의 현재 위치를 기반으로 실시간 스포츠 중계를 방영하는 매장을 카카오맵에 매핑하고 필터링해주는 위치 기반 서비스입니다.

*   **Stack**: `React`, `TypeScript`, `Zustand`, `TanStack Query`, `Vitest`, `Playwright`, `Kakao Maps SDK`
*   **핵심 구현 요약**: Kakao Maps API 연동 및 드래그 바운더리 동적 마커 필터링 구현, Zustand를 통한 클라이언트 전역 상태 관리 및 TanStack Query를 통한 서버 캐싱 동기화.

#### 🛠️ 핵심 설계 결정 및 트러블슈팅 (Troubleshooting)

##### ① 비동기 지도 SDK 마운팅 지연에 따른 CI/CD E2E 테스트 Flakiness(결정성 결여) 제어
*   **문제 정의**: GitHub Actions CI 파이프라인에서 E2E 테스트 자동 실행 시, 카카오맵 외부 스크립트가 로딩 완료되기도 전에 Playwright 테스트 러너가 클릭/드래그 인터랙션을 실행하여 빌드가 무작위로 깨져 배포를 차단하는 장애 유발.
*   **대안 비교 및 채택**:
    *   *대안 A (임의의 sleep 대기)*: 빌드 속도를 무의식적으로 지연시키며 완벽한 타이밍 동기화 불가능 (기각).
    *   *대안 B (E2E 테스트 시 Canvas 마커 테스트 격리 및 Unit 보완)*: GPU 가속이 없는 가상화 headless 러너 특성상 WebGL 기반 마커 렌더링은 `test.skip(!!process.env.CI)`로 분리하되, 상태와 URL 로직은 로컬 단위 테스트로 촘촘히 보완 (선택).
*   **결과 검증**: 외부 SDK 로딩 비결정성으로 인해 깨지던 CI 테스트 빌드 실패율을 **0%**로 낮춰 배포 흐름을 안정화하고, 100개 이상의 유닛 테스트 커버리지로 비즈니스 로직 안정성 동시 확보.

##### ② 상태 결합성 해결을 위한 URLSearchParams 단방향 데이터 동기화 설계
*   **문제 정의**: 지도 뷰포트 좌표 상태, 필터 조건(Zustand), 그리고 뒤로가기/페이지 공유용 URL 파라미터가 3방향으로 얽히면서 무한 리렌더링 및 렌더 루프 상태가 발생하는 설계 버그 발견.
*   **대안 및 해결**: URL 쿼리 파라미터를 단 하나의 **싱글 소스 오브 트루스(SSOT)**로 격리하고, Zustand 스토어와 지도 SDK는 URL의 파라미터 변경 정보만을 구독(Subscribe)하여 단방향으로 흐르게 흐름을 정리함.
*   **결과 검증**: 상태 엉킴 현상과 무한 렌더링 발생률을 완전히 제거하여 사용자 브라우저 성능 최적화.

---

### 4️⃣ HyperStar (AI 인 인플루언서 마케팅 B2B SaaS)
*   **Stack**: `React`, `TypeScript`, `Zustand`, `React Query`, `Recharts`
*   **담당 업무**: **시연 제품 신뢰성 QA 및 백그라운드 상태 전송 설계** (CES 2026 출품)
*   **핵심 설계결정 및 트러블슈팅**:
    *   **대시보드 실시간 렌더링 병목 최적화**: 대용량 실시간 대시보드 차트 데이터를 처리할 때, Zustand 전역 스토어의 불필요한 상태 변경 감지로 화면 전체가 리렌더링되는 프레임 드랍 현상 발견. React Query의 `select` 옵션을 이용해 컴포넌트 단위로 필요한 서브셋 데이터만 얕은 비교(Shallow Compare)하도록 데이터 파이프라인을 튜닝하여, 렌더링 부하를 감소시키고 프레임 안정성(60fps) 확보.
    *   **예외 상태 추적 및 로깅**: 비공개 코드베이스 하에서 API 에러 발생 시 프론트엔드가 먹통이 되던 예외 상태를 방어하기 위해 Axios Interceptor에 에러 바운더리 레포팅 레이어를 설계하여 테스팅 효율 향상.
