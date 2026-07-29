# GitHub 프로필 README 설계 — "The Grimoire of Velkaressia Blutkrone"

- **작성일**: 2026-07-29
- **대상 레포**: `VelkaressiaBlutkrone/VelkaressiaBlutkrone` (신규 **public** 생성 — GitHub 프로필 특수 레포)
- **산출물**: 단일 `README.md` (로컬 이미지 없이 외부 SVG 서비스 활용)
- **상태**: 설계 확정(사용자 승인 완료), 구현 계획 대기

---

## 1. 목표 (Goal)

`VelkaressiaBlutkrone` 계정의 GitHub 프로필 페이지 상단에 렌더링되는 프로필 README를 새로 만든다.
계정의 개인 레포 + 소속 8개 조직의 실제 작업을 반영하여, **"예제·수련에서 분산 AI 플랫폼 아키텍트로 성장"** 하는 솔직한 서사를 **다크 판타지 페르소나("마도서")** 로 연출한다.

## 2. 확정된 방향 (Decisions)

| 항목 | 결정 |
|---|---|
| 톤/컨셉 | **다크 판타지 페르소나** — 아이디(Velkaressia Blutkrone = 피의 왕관) 세계관 활용 |
| 언어 | **한·영 병기** — 핵심 문구를 한국어 + 영어로 |
| 콘텐츠 성격 | **솔직한 성장 아크** — 예제·수련 → 분산 시스템 아키텍처 (과장 금지) |
| 구조 framing | **마도서(Grimoire)** — README 전체가 하나의 마법서, 섹션 = 장(章) |
| 플래그십 | **DevPath AI + Synapse 두 기둥** |
| 시각 요소 | 상단 배너/타이틀 이미지 + 기술 스택 배지 + GitHub 통계 카드 |
| Footer 연락처 | 개인 이메일(deepestdark@gmail.com) **포함** + GitHub |

## 3. 계정 컨텍스트 (실측 데이터, 2026-07-29)

### 3.1 개인 계정 (`VelkaressiaBlutkrone`, 표시명 "Velkaressia")
- 2021 가입, **실질 활동은 2025-11부터 급증** (구조화된 학습 여정)
- 공개 non-fork 38개 스택 분포: Java 12 · Dart 11 · TypeScript 5 · Python 3 · JS 2 · HTML 2 · C++ 2
- 성격: 풀스택 학습 (Spring 백엔드 + React 프론트 + Flutter 모바일 + DevOps/AWS/MSA + 약간의 AI/LLM). `-ex`/`-exam`/`-mng`/`study-lab` 네이밍 다수

### 3.2 소속 조직 (admin, 8개) — 실제 심화 작업의 소재지
- **`DevPathAi`** — 플래그십 A. 이벤트 기반 MSA로 구축한 AI 개발자 학습 플랫폼
  - 서비스: `devpath-gateway`(OAuth2+JWT edge), `devpath-platform-svc`(user/auth, github collector, notification), `devpath-ai-svc`(AI gateway orchestrator, review worker, FinOps), `devpath-learning-svc`(onboarding, path engine, content, mentor), `devpath-sandbox-svc`(**Docker + gVisor 격리 실행**), `devpath-community-svc`(post/reputation/badge/moderation), `devpath-notification-svc`, `devpath-lcs-svc`, `devpath-shared`(event schemas), `devpath-gitops`(K8s manifests), `devpath-frontend`(React web/admin + Flutter mobile), `devpath-svc-template`
  - 부속: landing-page, home-page, workflow-dashboard, workflow-guide, storyboard, prototype
- **`team-project-final` → Synapse** — 플래그십 B. 8개 서비스 MSA 플랫폼
  - `synapse`(submodule 엄브렐러), `synapse-gateway`, `synapse-platform-svc`(auth/audit/billing/notification), `synapse-knowledge-svc`(note/graph/chunking), `synapse-engagement-svc`(community/gamification), `synapse-learning-svc`(card/srs Java + ai Python), `synapse-shared`(Avro 스키마 + 공통 라이브러리), `synapse-frontend`(Flutter web/mobile), `synapse-gitops`(**K8s manifests + ArgoCD ApplicationSet**)
- `proejct-team-alpha` → **HMS** (병원 예약·업무 시스템, Spring Boot + Mustache + MySQL)
- `ai-cli-terminal` → **terminal** (AI CLI 터미널, JS)
- `Public-Project-Area-Oragans` → 도메인 샘플군 (syn/mf/sme/wms/lms/dql)
- `Project-Control-Hub` → pch, msa, documents
- `academy-example-repo` → example-01~07 (아카데미 실습)
- `game-mod-project` → `long_yin_li_zhi_zhuan_mode` (C# 게임 모드)

## 4. README 섹션 설계 (마도서 구조)

### ① 표제 (Cover / Banner)
- `capsule-render` 다크 웨이브 배너 + 타이틀 **"Velkaressia Blutkrone"**
- 부제 타이핑 애니메이션(`readme-typing-svg`) 회전 문구(한·영):
  - "코드의 강령술사 · Necromancer of Code"
  - "수련생에서 아키텍트로 · From apprentice to architect"
  - "분산 시스템을 벼리는 자 · Forging distributed systems"
- 한·영 태그라인 1줄

### ② 소환의 장 (About)
- 페르소나 보이스의 짧은 소개(한·영), 솔직한 사실을 연출로 감쌈:
  - 풀스택: Spring(백엔드) · React(프론트) · Flutter(모바일)
  - 성장 아크: 예제·수련 → 분산 시스템 아키텍처
  - 현재 관심: MSA · 이벤트 드리븐 · K8s/GitOps · AI 오케스트레이션
- 간단한 quick-facts 목록(연출 라벨 + 사실)

### ③ 대마법서 서고 (Grimoires — 플래그십 2기둥)
스택형 2개 섹션(카드형), 각각:
- **📕 DevPath AI** (`DevPathAi`)
  - 한 줄 컨셉: 이벤트 기반 MSA로 구축한 AI 개발자 학습 플랫폼
  - 하이라이트: OAuth2/JWT 게이트웨이 · **gVisor 격리 sandbox-svc** · AI 오케스트레이터/리뷰 워커/FinOps · K8s GitOps · React+Flutter 프론트
  - 구성 레포 링크(gateway · platform-svc · ai-svc · learning-svc · sandbox-svc · community-svc · gitops · frontend)
  - 관련 기술 배지
- **📗 Synapse** (`team-project-final`)
  - 한 줄 컨셉: 8개 서비스 MSA 플랫폼
  - 하이라이트: git submodule 엄브렐러 · Avro 스키마 · **K8s + ArgoCD GitOps** · knowledge/platform/engagement/learning 도메인 서비스 · Flutter 프론트
  - 주요 레포 링크 + 배지

### ④ 무기고 (Arsenal — 기술 스택 배지)
`shields.io` 배지, 페르소나 색(다크 레드/블랙 계열)으로 통일, 그룹핑:
- **Language**: Java · Dart · TypeScript · Python · JavaScript · C#
- **Backend**: Spring Boot · Spring Cloud/Gateway
- **Frontend**: React · Flutter · Riverpod
- **Data**: MySQL · MongoDB · Firestore · Avro
- **Infra/DevOps**: Docker · Kubernetes · ArgoCD · gVisor · AWS
- **AI**: LLM 오케스트레이션 · Python AI 서비스

### ⑤ 연대기 (Chronicle — 성장 타임라인)
과장 없는 3막(한·영 라벨):
- **수련 (2025 말)**: Java/Spring 기초, 서블릿·소켓·게시판 예제, Flutter Firestore/Riverpod
- **확장 (2026 상반기)**: 풀스택 통합(spring-react-flutter), MSA 입문, HMS 팀 프로젝트, Docker/AWS
- **정립 (2026 중반)**: Synapse(8-svc MSA + GitOps), DevPath AI(이벤트 드리븐 + gVisor + AI 오케스트레이션)

### ⑥ 룬 석판 (Runestones — GitHub 통계)
- `github-readme-stats` 통계 카드 + Top Languages (다크 테마, 예: tokyonight/dark)
- `github-readme-streak-stats` 스트릭
- **주의**: 비공개 레포가 많아(29개) 토큰 미연동 시 **공개 기준** 집계 → 카드가 다소 비어 보일 수 있음. 스택 배지/연대기로 실제 역량을 보완한다.

### ⑦ 결계 (Footer)
- `capsule-render` 하단 배너 + 마무리 한 줄
- 연락처: GitHub 프로필 + 이메일(deepestdark@gmail.com) 배지/링크

## 5. 외부 서비스 의존성 (모두 GitHub README 표준 사용)
- `capsule-render` (kyechan99) — 상·하단 배너
- `readme-typing-svg` (DenverCoder1) — 타이핑 부제
- `shields.io` — 기술 스택/연락처 배지
- `github-readme-stats` (anuraghazra) — 통계 · Top Languages
- `github-readme-streak-stats` (DenverCoder1) — 스트릭

> 참고: GitHub README는 아티팩트와 달리 외부 이미지 URL을 허용하므로 위 서비스 사용에 문제 없음. 다만 서비스 다운 시 이미지 미표시 가능성은 감수한다(텍스트 콘텐츠는 독립적으로 읽힘).

## 6. 제약 및 원칙 (Constraints)
- **솔직성**: 실제 존재하는 레포/기술만 기술. 없는 경력·자격 창작 금지.
- **정보-연출 균형**: 페르소나 연출이 기술 정보 가독성을 해치지 않게. 각 연출 라벨 옆에 평문 사실 병기.
- **유지보수성**: 단일 `README.md`, 로컬 바이너리/이미지 자산 없음. 링크는 실제 레포 URL로 검증.
- **접근성**: 이미지에 의미 있는 alt 텍스트. 배지/카드가 로드 안 돼도 문서가 읽히도록 텍스트 우선.

## 7. 브랜치·배포 유의사항 (구현 단계에서 처리)
- 프로필 README는 **레포 기본 브랜치**에 있어야 프로필에 렌더링됨(GitHub 사양).
- 현재 로컬 `velkaressiaBlutkrone`는 커밋·리모트 없는 빈 저장소. 신규 GitHub public 레포 생성 후 연결 필요.
- 사용자 공통 규칙(main 보호, develop 경유)과 "프로필 README는 기본 브랜치 필요"가 상충할 수 있으므로, 구현 계획에서 배포 경로를 명시적으로 확정한다.

## 8. 범위 밖 (Out of Scope)
- 조직 레포 자체의 README/코드 수정
- 프로필 이외 개인 레포들의 정리·아카이브
- GitHub Actions(snake 애니메이션 등) 자동화 — 필요 시 후속 작업으로 분리
