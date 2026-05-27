# 심우현

**Frontend Engineer x AI Agent Engineer**

React/TypeScript 기반 제품 개발 경험을 바탕으로 RAG, AI 검색, 자동화 워크플로우를 구현합니다.  
사용자 인터페이스부터 API, 데이터 흐름, LLM 응답 품질까지 연결해 실제 문제를 해결하는 개발자를 지향합니다.

[![Portfolio](https://img.shields.io/badge/Portfolio-111827?style=flat-square&logo=vercel&logoColor=white)](https://simwoohyun.vercel.app/)
[![Email](https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:wmr06244@naver.com)

---

## 대표 프로젝트

| Project | Description | Links |
|---|---|---|
| **TechDocs** | RAG 기반 특허 문서 AI 검색 서비스 | [GitHub](https://github.com/neverleaveualong/TechDocs) · [Demo](https://techdocs-psi.vercel.app) |
| **TechLens** | 특허 공공데이터 기반 검색·분석 서비스 | [GitHub](https://github.com/Douzone-Keycom-Internship-woohyun-2025) · [Demo](https://frontend-techlens.vercel.app/login) |
| **Playce** | 위치 기반 스포츠 중계 장소 검색 서비스 | [GitHub](https://github.com/neverleaveualong/PlayceV) · [Demo](https://playce-app.vercel.app) |

### TechDocs

**RAG 기반 특허 문서 AI 검색 서비스**  
`FastAPI` `LangChain` `Pinecone` `OpenAI` `BM25` `RAGAS` `Docker`

- KIPRIS 특허 문서를 임베딩하고 Pinecone에 저장하는 RAG 파이프라인 구현
- BM25 키워드 검색과 Vector Search를 결합한 하이브리드 검색 구조 적용
- RAGAS 기반으로 답변 품질을 평가하고 chunk 설정을 비교
- 검색 로그와 피드백 루프를 저장해 답변 개선 근거를 남기는 구조 설계

### TechLens

**특허 공공데이터 기반 검색·분석 서비스**  
`React` `TypeScript` `Express` `PostgreSQL` `Zod` `Chart.js`

- KIPRIS API 기반 특허 데이터 수집, 검색, 분석 기능 구현
- JWT Access/Refresh 인증과 PostgreSQL 기반 데이터 관리 구조 설계
- 특허 출원 추이, IPC 분포, 등록 상태를 확인하는 대시보드 구현
- Controller, Service, Repository 계층 분리와 Zod 검증으로 API 안정성 개선

### Playce

**위치 기반 스포츠 중계 장소 검색 서비스**  
`React` `TypeScript` `Zustand` `TanStack Query` `Vitest` `Playwright`

- Kakao Maps 기반 위치 검색과 주변 장소 탐색 UI 구현
- 서버 상태와 클라이언트 상태를 분리하기 위해 React Query 도입
- Vitest 109개, Playwright 28개 테스트와 GitHub Actions CI 구축
- 코드 스플리팅과 번들 최적화로 초기 로딩 비용 개선

---

## Toy Projects

### Morning Weather Bot

**GitHub Actions 기반 아침 브리핑 자동화 봇**  
`Python` `Open-Meteo API` `Google Calendar iCal` `Telegram Bot API` `GitHub Actions`

- GitHub: https://github.com/neverleaveualong/morning-weather-bot
- 매일 오전 8시 GitHub Actions cron으로 자동 실행
- 오늘/내일 할일과 원주·서울 날씨를 텔레그램으로 전송
- GitHub Secrets 기반으로 Telegram token과 Calendar iCal URL 관리

---

## 기술

| Area | Stack |
|---|---|
| Frontend | `React`, `TypeScript`, `Next.js`, `Zustand`, `TanStack Query` |
| Backend | `FastAPI`, `Express`, `PostgreSQL` |
| AI/RAG | `OpenAI API`, `LangChain`, `Pinecone`, `BM25`, `RAGAS` |
| Automation | `GitHub Actions`, `Telegram Bot API`, `Google Calendar iCal` |
| Testing | `Vitest`, `Playwright` |
| Infra | `Docker`, `Vercel`, `AWS` |

---

## 관심 분야

- AI Agent와 RAG 기반 검색 시스템
- LLM 응답 품질 평가와 피드백 루프
- 외부 API를 연결한 업무 자동화
- 안정적인 프론트엔드 구조, 테스트, 리팩토링
