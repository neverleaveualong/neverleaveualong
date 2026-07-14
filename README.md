# 심우현 (SIM WOOHYUN)
> **AI Agent Engineer x Fullstack Engineer**  
> [심우현 개발자 포트폴리오](https://simwoohyun.vercel.app) | wmr06244@naver.com

React/TypeScript 기반의 사용자 경험(UX) 최적화부터 RAG(검색 증강 생성) 파이프라인 구축, AI 검색, 그리고 자동화 워크플로우까지 엔드투엔드로 설계하고 해결하는 개발자입니다. 

비결정적인 LLM의 특성을 프로덕션 수준에서 다루기 위해 **사용자 인터페이스(UI) - API 설계 - 데이터 파이프라인 - LLM 응답 품질 평가(RAGAS) - 검색 피드백 루프**에 이르는 전체 데이터 흐름을 견고하게 연결하여 실제 비즈니스 문제를 정의하고 해결하는 것을 지향합니다.

---

## 🛠️ Tech Stack & Competencies

| 분류 | 기술 스택 |
| :--- | :--- |
| **Frontend & Fullstack** | `React`, `TypeScript`, `Next.js`, `Zustand`, `TanStack Query`, `Zod`, `Express` |
| **AI & RAG** | `LangChain`, `Pinecone`, `OpenAI API`, `BM25`, `RAGAS` |
| **Data & DevOps** | `PostgreSQL`, `Docker`, `GitHub Actions`, `Telegram Bot API` |
| **Testing** | `Vitest`, `Playwright` |

---

## 📂 Core Projects

### 1. TechDocs (RAG 기반 특허 문서 AI 검색 서비스)
> 특허 문서를 전처리 및 임베딩하여 사용자 의도에 부합하는 정보를 신뢰성 있게 도출하는 RAG 시스템입니다.
* **Stack**: `FastAPI`, `LangChain`, `Pinecone`, `OpenAI`, `BM25`, `RAGAS`, `Docker`
* **Key Achievements**:
  * KIPRIS 특허 문서 전처리 파이프라인 설계 및 Pinecone Vector DB 인덱싱 구축.
  * 검색 시인성과 정확도 향상을 위해 **BM25 키워드 검색**과 **Vector Search**를 결합한 하이브리드 검색 구조 설계.
  * **RAGAS 프레임워크**를 도입하여 청크(Chunk) 크기 및 파라미터별 답변 품질을 정량적으로 평가 및 비교 분석.
  * 지속적인 검색 성능 개선의 기반을 마련하기 위해 검색 로그 데이터베이스 설계 및 피드백 루프 구조화.
* **Link**: [GitHub](https://github.com/neverleaveualong/TechDocs) · [Demo](https://techdocs-psi.vercel.app)

### 2. TechLens (특허 공공데이터 기반 검색·분석 서비스)
> KIPRIS API 데이터를 정제하여 연도별 출원 추이 및 등록 상태 등을 제공하는 대시보드 및 서비스입니다.
* **Stack**: `React`, `TypeScript`, `Express`, `PostgreSQL`, `Zod`, `Chart.js`
* **Key Achievements**:
  * 대량의 특허 공공데이터 수집 파이프라인 설계 및 PostgreSQL 기반 데이터 스키마 구축.
  * 특허 출원 추이, IPC 분포, 등록 상태 등의 데이터를 시각화하는 인터랙티브 대시보드 컴포넌트 개발.
  * JWT (Access/Refresh Token) 기반 인증 및 API 보안 체계 구축.
  * 백엔드 코드의 안정성을 확보하기 위해 **Zod 스키마 검증** 레이어를 도입하고, **Controller-Service-Repository** 계층 분리 아키텍처를 도입하여 코드 유지보수성 향상.
* **Link**: [GitHub](https://github.com/Douzone-Keycom-Internship-woohyun-2025) · [Demo](https://frontend-techlens.vercel.app/login)

### 3. HyperStar (AI 인플루언서 B2B SaaS)
> AI 기술을 결합하여 인플루언서 마케팅 분석 및 성과 관리를 돕는 엔터프라이즈 대상 SaaS 제품입니다.
* **Stack**: `React`, `TypeScript`, `Zustand`, `React Query`, `Recharts`, `AWS`
* **Key Achievements**:
  * **CES 2026 시연 제품**의 QA 및 동작 신뢰성 검증을 전담하여 예외 케이스 식별 및 디버깅 수행.
  * Zustand 기반 전역 상태 관리와 React Query 서버 상태 조율을 통해 실시간 대용량 대시보드 데이터 흐름을 최적화.
  * API 응답 구조 및 모니터링을 분리하여 병목 현상 추적 및 프론트엔드-백엔드 연동성 강화.
* **Link**: *Source Private (CES 2026 Demo)*

### 4. Playce (위치 기반 스포츠 중계 장소 검색 서비스)
> 지도를 기반으로 근처 스포츠 중계 채널을 보유한 매장이나 장소를 찾을 수 있는 검색 플랫폼입니다.
* **Stack**: `React`, `TypeScript`, `Zustand`, `TanStack Query`, `Vitest`, `Playwright`
* **Key Achievements**:
  * Kakao Maps API 연동을 통한 위치 기반 실시간 검색 및 지도 동적 렌더링 최적화.
  * **Vitest(109개)**와 **Playwright(28개)**를 활용해 주요 유저 저니(User Journey)에 대한 견고한 유닛/E2E 테스트 커버리지 확보 및 GitHub Actions CI 파이프라인 연동.
  * Code Splitting 및 번들링 번들 최적화를 통해 초기 로드 용량 단축 및 모바일 브라우저 렌더링 성능 향상.
* **Link**: [GitHub](https://github.com/neverleaveualong/PlayceV) · [Demo](https://playce-app.vercel.app)

---

## 🤖 Toy Projects & Automation

### Morning Weather Bot
* **Stack**: `Python`, `Open-Meteo API`, `Google Calendar iCal`, `Telegram Bot API`, `GitHub Actions`
* **Description**:
  * 매일 오전/오후 8시에 오늘/내일의 일정(Google Calendar) 및 날씨 요약 브리핑을 텔레그램으로 자동 전송하는 워크플로우 봇.
  * 서버리스 환경(GitHub Actions CRON) 및 GitHub Secrets 기반의 API Credential 관리로 비용 없이 자동 구동되는 시스템 설계.
* **Link**: [GitHub](https://github.com/neverleaveualong/morning-weather-bot)
