# 프로필 README 리모델 설계 스펙 — 프로페셔널 개발자 프로필

- **날짜**: 2026-08-29
- **대상**: `README.md` (VelkaressiaBlutkrone 프로필 레포)
- **대체 문서**: 본 스펙은 `2026-07-29-profile-readme-design.md`(다크 판타지 마도서 콘셉트)를 대체한다.

## 1. 배경과 목표

현재 프로필은 다크 판타지 세계관("Necromancer of Code", 소환의 장·룬 석판 등) 기반이다.
창업·투자·채용 등 비즈니스 맥락에서 레포가 공개될 때 신뢰를 깎을 수 있으므로,
**판타지 콘셉트를 전면 제거하고 프로페셔널 개발자 프로필로 리모델**한다.

- **톤**: 완전 프로페셔널. 판타지 언어·수식어 전면 제거.
- **타깃 독자**: 투자자·창업 파트너, 채용 담당자·리크루터, 동료 개발자·오픈소스 커뮤니티 모두.
- **언어**: 한/영 병기 유지.
- **장식 요소**: 현행 수준 유지(웨이빙 헤더·타이핑 SVG·통계 카드·배지) — 색상과 문구만 교체.
- **접근**: 기존 7섹션 골격과 검증된 배지 URL 구조를 유지한 채 전면 리라이트(접근안 A).

## 2. 디자인 시스템

| 항목 | 값 |
|---|---|
| 배경 | `#0d1117` (GitHub 다크) |
| 포인트 | `#1f6feb` (GitHub accent blue) |
| 보조 포인트 | `#58a6ff` (타이핑 SVG·스트릭 강조) |
| 본문 보조 텍스트 | `#c9d1d9` |
| 배지 패턴 | 현행 shields.io `for-the-badge` 구조 유지, 배경색 `8B0000 → 1f6feb` 단색 교체, `labelColor=0d1117` 유지 |

- **헤더(capsule-render)**: 웨이빙 타입 유지, 그라데이션 `0:0d1117,50:1f6feb,100:0d1117` 계열.
  큰 글씨 **"Full-Stack Developer"**, desc "Distributed Systems · MSA · Event-Driven".
  헤더 아래 작은 텍스트로 `@VelkaressiaBlutkrone` 표기(역할 타이틀 중심, 계정명은 보조).
- **타이핑 SVG**: 유지, 색상 `58A6FF`, 문구 3줄 —
  1. `이벤트 기반 분산 시스템을 만듭니다 · Building event-driven distributed systems`
  2. `Spring · React · Flutter 풀스택 · Full-stack across Spring, React, Flutter`
  3. `Kubernetes GitOps · AI Orchestration`
- **푸터(capsule-render)**: 웨이빙 유지, 동일 뉴트럴 그라데이션.

## 3. 섹션 구성 (7섹션 골격 유지)

| # | 현재 | 리모델 후 |
|---|---|---|
| ① | 표제 · Cover | Cover (역할 타이틀 헤더) |
| ② | 🩸 소환의 장 · Summoning | 👋 About Me |
| ③ | 📜 대마법서 서고 · The Grimoire Vault | 🚀 Featured Projects |
| ④ | ⚔️ 무기고 · Arsenal | 🛠️ Tech Stack |
| ⑤ | 🕯️ 연대기 · Chronicle | 📈 Journey |
| ⑥ | 🔮 룬 석판 · Runestones | 📊 GitHub Stats |
| ⑦ | 🕸️ 결계 · Wards | 📫 Contact |

### ② About Me
세계관 인용구 제거. 불릿 4개, 한/영 병기:
- **풀스택** — Spring(백엔드) · React(프론트) · Flutter(모바일)
- **성장 궤적** — 기초 학습 → 이벤트 기반 분산 시스템 아키텍처
- **현재 관심** — MSA · Event-Driven · Kubernetes / GitOps · AI Orchestration
- **협업** — 8개 조직에서 팀 프로젝트 리딩

### ③ Featured Projects
DevPath AI·Synapse 두 프로젝트의 기술 설명·서비스 링크·스택 배지를 전부 유지하고
판타지 수식어만 제거한다. 각 프로젝트에 **Role 한 줄**(설계·리딩 범위)을 추가한다
— 투자자·리크루터 독자 보강.

- **DevPath AI**: OAuth2/JWT 엣지 게이트웨이 · 이벤트 기반 서비스 분해 · K8s GitOps 배포 ·
  Docker+gVisor 격리 실행(sandbox-svc) · AI 게이트웨이 오케스트레이터/리뷰 워커/FinOps.
  서비스 링크 8종 유지.
- **Synapse**: git submodule 엄브렐러 · Avro 스키마 계약(synapse-shared) ·
  K8s + ArgoCD ApplicationSet GitOps. 도메인 링크 9종 유지.

### ④ Tech Stack
현행 6카테고리(Languages / Backend / Frontend / Data / Infra & DevOps / AI)와
배지 목록 유지, 색상만 교체. 카테고리 앞 판타지 이모지(🩸🗡️🔮🏰)는 제거하고 볼드 텍스트 카테고리명만 남긴다.

### ⑤ Journey
3단계 구성 유지, 명칭 교체:
- **Foundations** *(late 2025)* — Java/Spring 기초, 서블릿·소켓·게시판, Flutter Firestore/Riverpod
- **Expansion** *(H1 2026)* — 풀스택 통합, MSA 입문, [HMS](https://github.com/proejct-team-alpha/hms) 팀 프로젝트, Docker·AWS
- **Distributed Systems** *(mid 2026)* — [Synapse](https://github.com/team-project-final/synapse)(8-svc MSA + GitOps), [DevPath AI](https://github.com/DevPathAi)(이벤트 드리븐 · gVisor 격리 · AI 오케스트레이션)

### ⑥ GitHub Stats
- 유지: 방문자 수(komarev) · Followers · Following(정적) · 스트릭 카드 — 색상만 블루 계열로.
- 배지 문구 교체:
  - `CLASS: Full-Stack Necromancer` → `ROLE: Full-Stack Developer`
  - `STRONGHOLDS: 8 Orgs` → `ORGS: 8`
  - `AWAKENED: Jan 2021` → `SINCE: Jan 2021`
  - `FOCUS: MSA & Event-Driven` → 문구 유지
- 각주 평문화: "주요 작업은 비공개/조직 레포에 있습니다 · Most work lives in private & org repos."

### ⑦ Contact
GitHub·Email 배지 유지, 색상 교체. 푸터 웨이빙 이미지 뉴트럴 그라데이션으로 교체.

## 4. 구현 방식

- **변경 파일**: `README.md` 전면 리라이트 1건. (본 스펙 문서 신규 1건)
- **브랜치 전략**: `develop` 생성(완료) → `feat/profile-remodel` 분기 →
  develop으로 PR·머지 → 릴리스 시 develop→main PR.
- **검증**:
  - 배지·이미지 URL 전수 확인(한글 문구 URL 인코딩 포함).
  - shields.io 동적 배지는 기존 검증된 패턴만 재사용(github/following 미지원 등 과거 이슈 반영).
  - 최종 렌더링 확인.

## 5. 범위 밖 (Non-goals)

- 계정명(핸들) 변경 — GitHub 설정 영역이며 본 리모델 범위 밖.
- 프로필 외 레포(DevPath AI·Synapse 등) 문서 정비.
- 새 통계 위젯·GitHub Actions 자동화 추가.
