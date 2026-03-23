<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1a2e,100:16213e&height=200&section=header&text=Woo%20Hyun%20Sim&fontSize=42&fontColor=e2e8f0&animation=fadeIn&fontAlignY=38&desc=Frontend%20Developer&descSize=18&descColor=94a3b8&descAlignY=55" width="100%" />

<br>

`51개 PR` `673 커밋` `141개 테스트` `번들 42% 최적화` `리팩토링 29단계`

<br>

[![Portfolio](https://img.shields.io/badge/Portfolio-18181b?style=for-the-badge&logo=vercel&logoColor=white)](https://simwoohyun.vercel.app/)&nbsp;
[![Email](https://img.shields.io/badge/Email-18181b?style=for-the-badge&logo=gmail&logoColor=white)](mailto:wmr06244@naver.com)

</div>

<br>

## `>` Career

<table>
<tr>
<td width="140"><b>2025.12 ~ 2026.03</b></td>
<td><b>하이퍼스타</b> — Frontend / Backend / QA<br><sub>PlayceV 프론트엔드 메인 개발 (6인 팀, FE 코드 기여 52%) · 단독 리팩토링 14단계 · 테스트 141개 + CI 파이프라인 구축</sub></td>
</tr>
<tr>
<td><b>2025.10 ~ 2025.12</b></td>
<td><b>더존비즈온</b> 키컴 개발본부 — SW Developer Intern<br><sub>TechLens 풀스택 단독 개발 · KIPRIS 특허 API 연동 · 백엔드 리팩토링 15단계</sub></td>
</tr>
<tr>
<td><b>2024.09 ~ 2024.11</b></td>
<td><b>고용노동부 플립드 메타버스</b> — SW Developer Intern</td>
</tr>
<tr>
<td><b>2023.08 ~ 2025.01</b></td>
<td><b>강원대 교양교육원</b> — System Administrator</td>
</tr>
</table>

<br>

## `>` Projects

### PlayceV &nbsp;—&nbsp; 위치 기반 스포츠 중계 맛집 플랫폼

> 6인 팀 (FE 3 + BE 3) &nbsp;·&nbsp; **프론트엔드 메인 개발자** &nbsp;·&nbsp; [Live](https://playce-app.vercel.app) &nbsp;·&nbsp; [GitHub](https://github.com/neverleaveualong/PlayceV)

<table>
<tr>
<td align="center" width="150"><b>코드 기여</b><br><h3>52%</h3><sub>FE 125개 파일 중<br>97개 직접 작성</sub></td>
<td align="center" width="150"><b>PR</b><br><h3>51개</h3><sub>P1 ~ P14<br>단독 리팩토링</sub></td>
<td align="center" width="150"><b>번들 최적화</b><br><h3>-42%</h3><sub>510KB → 295KB<br>7개 청크 분리</sub></td>
<td align="center" width="150"><b>테스트</b><br><h3>141개</h3><sub>Vitest 109<br>Playwright 32</sub></td>
</tr>
</table>

**핵심 기능** &nbsp; 상세보기 · 즐겨찾기 · 중계 일정 · 마이페이지 · 카카오맵 연동 · 다중 필터 검색

<details>
<summary><b>리팩토링 14단계 상세</b></summary>
<br>

| 단계 | 내용 | 수치 |
|:---:|------|------|
| **P1~P3** | 데드코드 제거 · 구조 정리 · 버그 수정 | Path Alias 적용, 미사용 코드 삭제 |
| **P4** | React Query 도입 | 서버/클라이언트 상태 분리 |
| **P5** | React Hook Form 도입 | 폼 관리 일원화 |
| **P6** | 코드 스플리팅 | MypageModal **-90%** (311→31KB) |
| **P7** | 렌더링 최적화 + 번들 분리 | memo 10개, useMemo 17개, 번들 **-42%** |
| **P8~P9** | UI/UX 개선 · 반응형 | 모바일 터치 대응, 토스트 시스템 |
| **P10~P12** | 기능 추가 · 랜딩 리디자인 | 카카오 공유, 도시 퀵네비, B2C UI |
| **P13** | Vitest + Playwright | 단위 109개 + E2E 32개 = **141개** |
| **P14** | GitHub Actions CI | PR마다 자동 테스트, 브라우저 캐싱 |

</details>

<br>

`React 19` `TypeScript` `Zustand` `TanStack Query` `Tailwind CSS` `Vite` `Vitest` `Playwright` `GitHub Actions`

---

### TechLens &nbsp;—&nbsp; 특허 인텔리전스 분석 대시보드

> 더존비즈온 인턴십 &nbsp;·&nbsp; **풀스택 단독 개발** &nbsp;·&nbsp; [Demo](https://frontend-techlens.vercel.app/login) &nbsp;·&nbsp; [GitHub](https://github.com/Douzone-Keycom-Internship-woohyun-2025)

<table>
<tr>
<td align="center" width="150"><b>커밋</b><br><h3>262개</h3><sub>FE 138 + BE 124</sub></td>
<td align="center" width="150"><b>리팩토링</b><br><h3>15단계</h3><sub>백엔드 아키텍처<br>전면 재설계</sub></td>
<td align="center" width="150"><b>API 최적화</b><br><h3>5건/200ms</h3><sub>KIPRIS 배치 처리<br>+ IPC 캐싱</sub></td>
<td align="center" width="150"><b>보안</b><br><h3>JWT 이중 토큰</h3><sub>Access + Refresh<br>+ Zod 검증</sub></td>
</tr>
</table>

**핵심 기능** &nbsp; 특허 검색 · Chart.js 대시보드 (월별 추이, IPC 분포, 등록 상태) · 관심 특허 관리

<details>
<summary><b>백엔드 리팩토링 15단계 상세</b></summary>
<br>

| 단계 | 내용 |
|:---:|------|
| **P1~P3** | 아키텍처 정리 · SQL 인젝션 방어 · 인증 강화 |
| **P4~P6** | 에러 핸들링 표준화 · API 응답 일관성 · 입력 검증 |
| **P7~P9** | 로깅 시스템 · 환경변수 관리 · 트랜잭션 처리 |
| **P10~P12** | Repository 패턴 · 비즈니스 로직 분리 · 캐싱 |
| **P13~P15** | API 문서화 · 성능 최적화 · 배포 설정 |

</details>

<br>

`React 19` `TypeScript` `Zustand` `Chart.js` `shadcn/ui` `Express` `PostgreSQL` `Zod`

<br>

## `>` Tech Stack

<div align="center">

| Frontend | Testing & CI | Backend & Infra |
|:--------:|:------------:|:---------------:|
| ![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white) ![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black) ![Tailwind](https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white) ![Next.js](https://img.shields.io/badge/Next.js-000?style=flat-square&logo=nextdotjs&logoColor=white) | ![Vitest](https://img.shields.io/badge/Vitest-6E9F18?style=flat-square&logo=vitest&logoColor=white) ![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=flat-square&logo=playwright&logoColor=white) ![Actions](https://img.shields.io/badge/Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white) | ![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white) ![Express](https://img.shields.io/badge/Express-000?style=flat-square&logo=express&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) ![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Vercel](https://img.shields.io/badge/Vercel-000?style=flat-square&logo=vercel&logoColor=white) |

</div>

<br>

## `>` Education & Certifications

**강원대학교(춘천)** &nbsp; 컴퓨터공학과 (주전공) · 정밀의료융합 (부전공) &nbsp;|&nbsp; 2021.03 ~ 2026.02

`정보처리기사` `빅데이터분석기사` `SQLD` `ADsP` `DAsP` `TOEIC 860`

<br>

<div align="center">

![GitHub Activity Graph](https://github-readme-activity-graph.vercel.app/graph?username=neverleaveualong&theme=tokyo-night&area=true&hide_border=true&height=250)

[![Solved.ac Profile](http://mazassumnida.wtf/api/v2/generate_badge?boj=simwoohyun)](https://solved.ac/profile/simwoohyun)

</div>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1a2e,100:16213e&height=100&section=footer" width="100%" />
