<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:2d1b69,50:5b21b6,100:7c3aed&height=180&section=header&text=WooHyunSim%20(Paul)&fontSize=38&fontColor=f5f3ff&animation=fadeIn&fontAlignY=36&desc=Frontend%20Developer&descSize=16&descColor=c4b5fd&descAlignY=52" width="100%" />

3개 프로덕션 서비스 · 리팩토링 29단계 · 테스트 141개 · 번들 42% 최적화

[![Portfolio](https://img.shields.io/badge/Portfolio-5b21b6?style=flat-square&logo=vercel&logoColor=white)](https://simwoohyun.vercel.app/)&nbsp;&nbsp;
[![Email](https://img.shields.io/badge/Email-5b21b6?style=flat-square&logo=gmail&logoColor=white)](mailto:wmr06244@naver.com)

</div>

<br>

## Career

**하이퍼스타** &nbsp;|&nbsp; 2025.12 ~ 2026.03 &nbsp;|&nbsp; Frontend / Backend / QA

> AI 인플루언서 마케팅 B2B SaaS — [hyper-star.org](https://hyper-star.org)

- QA에서 시작해 UI 수정 → 프론트엔드 API 연동 → 풀스택 통합 개발까지 단계적으로 역할 확장
- 프론트엔드 API 연결 및 캠페인-크리에이터 통합 기능 개발
- Instagram 데이터 크롤링 파이프라인 설계, AWS Demo/Dev 환경 분리 구축

**더존비즈온** 키컴 개발본부 &nbsp;|&nbsp; 2025.10 ~ 2025.12 &nbsp;|&nbsp; SW Developer Intern

> 특허 인텔리전스 B2B 웹앱 TechLens — 풀스택 단독 개발 (FE 138 + BE 124 커밋)

- JWT 이중 토큰 인증 + Zustand 상태관리 기반 풀스택 아키텍처 설계
- KIPRIS API 배치 처리(5건/200ms 스로틀) + IPC 사전 캐싱으로 응답 속도 최적화
- 백엔드 리팩토링 15단계 단독 수행 — SQL 인젝션 방어, Repository 패턴, Zod 검증 도입

**프로그래머스 DevCourse** &nbsp;|&nbsp; 2025.06 ~ 2025.09

> 위치 기반 스포츠 중계 맛집 플랫폼 PlayceV — 6인 팀 프론트엔드 메인 개발자

- FE 코드 기여 52%(125개 파일 중 97개) → 단독 리팩토링 14단계 + 테스트 141개로 확장
- 번들 42% 감소(510→295KB), Vitest 109개 + Playwright 32개 테스트, GitHub Actions CI 구축

**강원대 교양교육원** &nbsp;|&nbsp; 2023.08 ~ 2025.01 &nbsp;|&nbsp; System Administrator

<br>

## Education

**강원대학교(춘천)** &nbsp;|&nbsp; 컴퓨터공학과 (주전공) · 정밀의료융합전공 (부전공) &nbsp;|&nbsp; 2021.03 ~ 2026.02

<br>

## Certifications

`정보처리기사` `빅데이터분석기사` `SQLD` `ADsP` `DAsP` `TOEIC 860`

<br>

## Projects

### PlayceV &nbsp;—&nbsp; 위치 기반 스포츠 중계 맛집 플랫폼

> [Live](https://playce-app.vercel.app) · [GitHub](https://github.com/neverleaveualong/PlayceV) · 6인 팀 FE 메인 개발자 (코드 기여 52%)

카카오맵 위에 주변 식당과 스포츠 중계 일정을 확인할 수 있는 SPA.
프론트엔드 핵심 기능을 전담하고, 이후 단독으로 코드 품질 · 성능 · 테스트 · CI까지 개선했습니다.

**담당 기능** &nbsp; 식당 상세보기(탭 구조) · 즐겨찾기 CRUD · 중계 일정 · 마이페이지 · 카카오맵 마커 연동 · 다중 필터(지역/종목/리그) 검색 · 거리/날짜 정렬

**리팩토링 성과 (14단계, 51개 PR)**
- 서버/클라이언트 상태 분리 — React Query 도입으로 Zustand에서 서버 데이터 분리
- 폼 관리 일원화 — React Hook Form 적용, 코드 스플리팅으로 MypageModal **90% 감소**
- 렌더링 최적화 — memo 10개, useMemo 17개, useCallback 11개, Zustand 개별 셀렉터 34개
- 번들 최적화 — manualChunks 7개 분리, 메인 번들 **510KB → 295KB (42% 감소)**
- 테스트 — Vitest 단위 109개 + Playwright E2E 32개 = **141개**, fake timer · API 모킹 · 모듈 격리
- CI/CD — GitHub Actions로 PR마다 자동 테스트, Playwright 브라우저 캐싱

`React 19` `TypeScript` `Zustand` `TanStack Query` `Tailwind CSS` `Vite` `Vitest` `Playwright` `GitHub Actions`

---

### TechLens &nbsp;—&nbsp; 특허 인텔리전스 분석 대시보드

> [Demo](https://frontend-techlens.vercel.app/login) · [GitHub](https://github.com/Douzone-Keycom-Internship-woohyun-2025) · 풀스택 단독 개발 (262 커밋)

KIPRIS 공공데이터 기반 특허 분석 및 시각화 B2B 웹앱.
더존비즈온 인턴십에서 기획부터 배포까지 풀스택을 단독으로 개발했습니다.

**담당 기능** &nbsp; 특허 검색 · 관심 특허 관리 · Chart.js 대시보드(월별 추이, IPC 분포, 등록 상태) · JWT 이중 토큰 인증

**백엔드 리팩토링 (15단계)**
- 아키텍처 정리 — Controller → Service → Repository 3계층 분리
- 보안 강화 — SQL 인젝션 방어, JWT Access+Refresh 이중 토큰, Zod 입력 검증
- 운영 품질 — 에러 핸들링 표준화, 로깅 시스템, 환경변수 관리, 트랜잭션 처리

`React 19` `TypeScript` `Zustand` `Chart.js` `shadcn/ui` `Express` `PostgreSQL` `Zod`

---

### TechDocs &nbsp;—&nbsp; RAG 기반 특허 문서 AI 검색 플랫폼

> [GitHub](https://github.com/neverleaveualong/TechDocs) · 개인 프로젝트 · 풀스택 단독 개발

KIPRIS 특허 데이터를 벡터 임베딩하여 자연어 의미 검색 + LLM 답변을 생성하는 RAG 시스템.
TechLens에서 쌓은 특허 도메인 지식을 기반으로, AI 검색까지 확장한 프로젝트입니다.

**담당 기능** &nbsp; RAG 파이프라인(임베딩 → Pinecone 유사도 검색 → LLM 답변) · KIPRIS 인제스트 파이프라인 · 특허 탐색 UI · Docker 컨테이너화

**설계 결정**
- 로컬 LLM(Ollama llama3) + 로컬 임베딩(HuggingFace all-MiniLM-L6-v2) → 비용 $0, 프로덕션에서 OpenAI 교체 가능
- 청킹 500자 + overlap 50 — 특허 초록 평균 200~600자 기준 검색 정확도 최적화
- 프롬프트에 할루시네이션 방지 규칙 — 출처 인용 강제, 근거 없으면 미답변

`Next.js` `TypeScript` `Tailwind CSS` `FastAPI` `LangChain` `Pinecone` `Ollama` `Docker` `GitHub Actions`

---

### HyperStar &nbsp;—&nbsp; AI 인플루언서 마케팅 B2B SaaS

> [hyper-star.org](https://hyper-star.org) · 소스코드 비공개 (전 직장)

500만+ 인플루언서 DB 기반 AI 크리에이터 매칭 · 캠페인 관리 · 성과 분석 플랫폼.
QA에서 시작해 프론트엔드 개발 · 인프라까지 역할을 확장했습니다.

**담당** &nbsp; 프론트엔드 API 연동 · 캠페인-크리에이터 통합 기능 개발 · Instagram 크롤링 파이프라인 · AWS 환경 분리(Demo/Dev)

`React 19` `TypeScript` `Zustand` `React Query` `Recharts` `Tailwind CSS` `Node.js` `PostgreSQL` `AWS`

<br>

## Tech Stack

<div align="center">

| Frontend | Testing & CI | Backend & Infra |
|:--------:|:------------:|:---------------:|
| ![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white) ![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black) ![Next.js](https://img.shields.io/badge/Next.js-000?style=flat-square&logo=nextdotjs&logoColor=white) ![Tailwind](https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white) ![Zustand](https://img.shields.io/badge/Zustand-433E38?style=flat-square&logo=react&logoColor=white) | ![Vitest](https://img.shields.io/badge/Vitest-6E9F18?style=flat-square&logo=vitest&logoColor=white) ![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=flat-square&logo=playwright&logoColor=white) ![Actions](https://img.shields.io/badge/Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white) | ![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white) ![Express](https://img.shields.io/badge/Express-000?style=flat-square&logo=express&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) ![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Vercel](https://img.shields.io/badge/Vercel-000?style=flat-square&logo=vercel&logoColor=white) |

</div>

<br>

<div align="center">

![GitHub Activity Graph](https://github-readme-activity-graph.vercel.app/graph?username=neverleaveualong&theme=tokyo-night&area=true&hide_border=true&height=250)

[![Solved.ac Profile](http://mazassumnida.wtf/api/v2/generate_badge?boj=simwoohyun)](https://solved.ac/profile/simwoohyun)

</div>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:2d1b69,50:5b21b6,100:7c3aed&height=100&section=footer" width="100%" />
