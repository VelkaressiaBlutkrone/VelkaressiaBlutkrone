# 프로필 README 리모델 구현 계획

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** 다크 판타지 콘셉트의 프로필 README를 판타지 언어 전면 제거 + GitHub 다크 뉴트럴 팔레트의 프로페셔널 개발자 프로필로 전면 리라이트한다.

**Architecture:** 기존 7섹션 골격과 검증된 배지 URL 구조를 유지한 채 `README.md` 단일 파일을 전면 교체한다. 색상은 `8B0000(혈적색) → 1f6feb(GitHub accent blue)` 단색 치환, 문구는 표준 개발자 용어로 교체한다.

**Tech Stack:** GitHub Flavored Markdown · shields.io · capsule-render · readme-typing-svg · komarev · github-readme-streak-stats

**Spec:** `docs/superpowers/specs/2026-08-29-profile-remodel-design.md`

## Global Constraints

- 판타지 언어(강령술사·마법서·룬·결계·소환 등) 사용 금지 — 본문·배지·alt 텍스트 전부.
- 팔레트: 배경 `0d1117`, 포인트 `1f6feb`, 보조 `58a6ff`, 텍스트 `c9d1d9`. 배지는 `for-the-badge` + `labelColor=0d1117` 유지.
- 한/영 병기 유지.
- 기존 프로젝트/서비스 링크(DevPath AI 8종, Synapse 9종, HMS)는 URL 변경 없이 전부 유지.
- 작업 브랜치 `feat/profile-remodel`(develop에서 분기, 생성 완료) → develop으로 PR. main 직접 푸시 금지.
- 모든 git 명령에 `-C /d/workspace/velkaressiaBlutkrone` 절대경로 사용.

---

### Task 1: README.md 전면 리라이트

**Files:**
- Modify: `README.md` (전체 교체)

**Interfaces:**
- Consumes: 없음 (스펙 문서만 참조)
- Produces: 완성된 `README.md` — Task 2가 이 파일의 URL을 전수 검증한다.

- [ ] **Step 1: README.md를 아래 내용으로 전체 교체**

아래 내용을 그대로 사용한다(자체 창작·변형 금지):

````markdown
<!-- ═══════════════ ① Cover ═══════════════ -->
<div align="center">

<img alt="Full-Stack Developer" width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:1f6feb,100:0d1117&height=230&section=header&text=Full-Stack%20Developer&fontSize=50&fontColor=ffffff&fontAlignY=40&desc=Distributed%20Systems%20%C2%B7%20MSA%20%C2%B7%20Event-Driven&descSize=20&descAlignY=62" />

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Noto+Sans+KR&size=22&duration=3600&pause=900&color=58A6FF&center=true&vCenter=true&width=820&height=55&lines=%EC%9D%B4%EB%B2%A4%ED%8A%B8+%EA%B8%B0%EB%B0%98+%EB%B6%84%EC%82%B0+%EC%8B%9C%EC%8A%A4%ED%85%9C%EC%9D%84+%EB%A7%8C%EB%93%AD%EB%8B%88%EB%8B%A4+%C2%B7+Building+event-driven+distributed+systems;Spring+%C2%B7+React+%C2%B7+Flutter+%ED%92%80%EC%8A%A4%ED%83%9D+%C2%B7+Full-stack+across+Spring%2C+React%2C+Flutter;Kubernetes+GitOps+%C2%B7+AI+Orchestration)](https://github.com/VelkaressiaBlutkrone)

**[@VelkaressiaBlutkrone](https://github.com/VelkaressiaBlutkrone)**

*이벤트 기반 분산 시스템을 설계하고 만드는 풀스택 개발자*
*A full-stack developer designing and building event-driven distributed systems*

</div>

---

<!-- ═══════════════ ② About Me ═══════════════ -->
## 👋 About Me

- **풀스택 · Full-stack** — Spring(백엔드) · React(프론트) · Flutter(모바일)
- **성장 궤적 · Growth arc** — 기초 학습에서 이벤트 기반 분산 시스템 아키텍처로 · from fundamentals to event-driven distributed architecture
- **현재 관심 · Current focus** — MSA · Event-Driven · Kubernetes / GitOps · AI Orchestration
- **협업 · Collaboration** — 8개 조직에서 팀 프로젝트를 이끄는 중 · leading team projects across 8 orgs

---

<!-- ═══════════════ ③ Featured Projects ═══════════════ -->
## 🚀 Featured Projects

### DevPath AI — AI 개발자 학습 플랫폼 · An AI-driven developer-learning platform

이벤트 기반 마이크로서비스로 구성된 대규모 학습 플랫폼.
*A large-scale learning platform built on event-driven microservices.*

- **Role** — 시스템 설계 및 팀 리딩 · system design & team lead
- **Architecture** — OAuth2 / JWT 엣지 게이트웨이 · 이벤트 기반 서비스 분해 · Kubernetes GitOps 배포
- **Isolated execution** — `sandbox-svc`가 **Docker + gVisor**로 사용자 코드를 격리 실행 · user code sandboxed with Docker + gVisor
- **AI layer** — AI 게이트웨이 오케스트레이터 · 리뷰 워커 · FinOps 비용 통제
- **Services** —
[gateway](https://github.com/DevPathAi/devpath-gateway) ·
[platform-svc](https://github.com/DevPathAi/devpath-platform-svc) ·
[ai-svc](https://github.com/DevPathAi/devpath-ai-svc) ·
[learning-svc](https://github.com/DevPathAi/devpath-learning-svc) ·
[sandbox-svc](https://github.com/DevPathAi/devpath-sandbox-svc) ·
[community-svc](https://github.com/DevPathAi/devpath-community-svc) ·
[gitops](https://github.com/DevPathAi/devpath-gitops) ·
[frontend](https://github.com/DevPathAi/devpath-frontend)

<p>
<img src="https://img.shields.io/badge/Java-1f6feb?style=for-the-badge&logo=openjdk&logoColor=white" />
<img src="https://img.shields.io/badge/Spring_Boot-1f6feb?style=for-the-badge&logo=springboot&logoColor=white" />
<img src="https://img.shields.io/badge/Python-1f6feb?style=for-the-badge&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/Docker-1f6feb?style=for-the-badge&logo=docker&logoColor=white" />
<img src="https://img.shields.io/badge/Kubernetes-1f6feb?style=for-the-badge&logo=kubernetes&logoColor=white" />
<img src="https://img.shields.io/badge/gVisor-1f6feb?style=for-the-badge&logo=google&logoColor=white" />
</p>

### Synapse — 8개 서비스 MSA 플랫폼 · An 8-service microservices platform

git submodule 엄브렐러로 묶인 도메인 지향 분산 시스템.
*A domain-oriented distributed system managed as a git-submodule umbrella.*

- **Role** — 아키텍처 설계 및 팀 리딩 · architecture design & team lead
- **Umbrella** — `synapse` 메타 레포가 서비스/인프라를 submodule로 통합
- **Contracts** — `synapse-shared`의 **Avro 스키마** + 공통 라이브러리
- **Delivery** — **Kubernetes + ArgoCD ApplicationSet** GitOps
- **Domains** —
[umbrella](https://github.com/team-project-final/synapse) ·
[gateway](https://github.com/team-project-final/synapse-gateway) ·
[platform-svc](https://github.com/team-project-final/synapse-platform-svc) ·
[knowledge-svc](https://github.com/team-project-final/synapse-knowledge-svc) ·
[engagement-svc](https://github.com/team-project-final/synapse-engagement-svc) ·
[learning-svc](https://github.com/team-project-final/synapse-learning-svc) ·
[shared](https://github.com/team-project-final/synapse-shared) ·
[frontend](https://github.com/team-project-final/synapse-frontend) ·
[gitops](https://github.com/team-project-final/synapse-gitops)

<p>
<img src="https://img.shields.io/badge/Java-1f6feb?style=for-the-badge&logo=openjdk&logoColor=white" />
<img src="https://img.shields.io/badge/Spring_Boot-1f6feb?style=for-the-badge&logo=springboot&logoColor=white" />
<img src="https://img.shields.io/badge/Apache_Avro-1f6feb?style=for-the-badge&logo=apache&logoColor=white" />
<img src="https://img.shields.io/badge/Kubernetes-1f6feb?style=for-the-badge&logo=kubernetes&logoColor=white" />
<img src="https://img.shields.io/badge/Argo_CD-1f6feb?style=for-the-badge&logo=argo&logoColor=white" />
<img src="https://img.shields.io/badge/Flutter-1f6feb?style=for-the-badge&logo=flutter&logoColor=white" />
</p>

---

<!-- ═══════════════ ④ Tech Stack ═══════════════ -->
## 🛠️ Tech Stack

**Languages**
<p>
<img src="https://img.shields.io/badge/Java-1f6feb?style=for-the-badge&logo=openjdk&logoColor=white" />
<img src="https://img.shields.io/badge/Dart-1f6feb?style=for-the-badge&logo=dart&logoColor=white" />
<img src="https://img.shields.io/badge/TypeScript-1f6feb?style=for-the-badge&logo=typescript&logoColor=white" />
<img src="https://img.shields.io/badge/Python-1f6feb?style=for-the-badge&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/JavaScript-1f6feb?style=for-the-badge&logo=javascript&logoColor=white" />
<img src="https://img.shields.io/badge/C%23-1f6feb?style=for-the-badge&logo=dotnet&logoColor=white" />
</p>

**Backend**
<p>
<img src="https://img.shields.io/badge/Spring_Boot-1f6feb?style=for-the-badge&logo=springboot&logoColor=white" />
<img src="https://img.shields.io/badge/Spring_Cloud_Gateway-1f6feb?style=for-the-badge&logo=spring&logoColor=white" />
</p>

**Frontend**
<p>
<img src="https://img.shields.io/badge/React-1f6feb?style=for-the-badge&logo=react&logoColor=white" />
<img src="https://img.shields.io/badge/Flutter-1f6feb?style=for-the-badge&logo=flutter&logoColor=white" />
<img src="https://img.shields.io/badge/Riverpod-1f6feb?style=for-the-badge&logo=riverpod&logoColor=white" />
</p>

**Data**
<p>
<img src="https://img.shields.io/badge/MySQL-1f6feb?style=for-the-badge&logo=mysql&logoColor=white" />
<img src="https://img.shields.io/badge/MongoDB-1f6feb?style=for-the-badge&logo=mongodb&logoColor=white" />
<img src="https://img.shields.io/badge/Firestore-1f6feb?style=for-the-badge&logo=firebase&logoColor=white" />
<img src="https://img.shields.io/badge/Apache_Avro-1f6feb?style=for-the-badge&logo=apache&logoColor=white" />
</p>

**Infra & DevOps**
<p>
<img src="https://img.shields.io/badge/Docker-1f6feb?style=for-the-badge&logo=docker&logoColor=white" />
<img src="https://img.shields.io/badge/Kubernetes-1f6feb?style=for-the-badge&logo=kubernetes&logoColor=white" />
<img src="https://img.shields.io/badge/Argo_CD-1f6feb?style=for-the-badge&logo=argo&logoColor=white" />
<img src="https://img.shields.io/badge/gVisor-1f6feb?style=for-the-badge&logo=google&logoColor=white" />
<img src="https://img.shields.io/badge/AWS-1f6feb?style=for-the-badge&logo=amazonwebservices&logoColor=white" />
</p>

**AI**
<p>
<img src="https://img.shields.io/badge/LLM_Orchestration-1f6feb?style=for-the-badge&logo=openai&logoColor=white" />
<img src="https://img.shields.io/badge/Python_AI_Service-1f6feb?style=for-the-badge&logo=python&logoColor=white" />
</p>

---

<!-- ═══════════════ ⑤ Journey ═══════════════ -->
## 📈 Journey

**Foundations** *(late 2025)*
Java / Spring 기초, 서블릿·소켓·게시판 예제, Flutter Firestore / Riverpod 학습.
*Java/Spring fundamentals, servlet·socket·board exercises, Flutter with Firestore/Riverpod.*

**Expansion** *(H1 2026)*
풀스택 통합(Spring + React + Flutter), MSA 입문, 병원 시스템 [HMS](https://github.com/proejct-team-alpha/hms) 팀 프로젝트, Docker·AWS 확장.
*Full-stack integration, first MSA work, the HMS hospital-system team project, Docker & AWS.*

**Distributed Systems** *(mid 2026)*
[Synapse](https://github.com/team-project-final/synapse)(8-svc MSA + GitOps)와 [DevPath AI](https://github.com/DevPathAi)(이벤트 드리븐 · gVisor 격리 · AI 오케스트레이션) 설계·구축.
*Designing and building Synapse (8-svc MSA + GitOps) and DevPath AI (event-driven · gVisor isolation · AI orchestration).*

---

<!-- ═══════════════ ⑥ GitHub Stats ═══════════════ -->
## 📊 GitHub Stats

<div align="center">

<img alt="Profile Views" src="https://komarev.com/ghpvc/?username=VelkaressiaBlutkrone&style=for-the-badge&color=1f6feb&labelColor=0d1117&label=PROFILE+VIEWS" />
<img alt="Followers" src="https://img.shields.io/github/followers/VelkaressiaBlutkrone?style=for-the-badge&logo=github&logoColor=white&label=FOLLOWERS&color=1f6feb&labelColor=0d1117" />
<img alt="Following 5" src="https://img.shields.io/badge/FOLLOWING-5-1f6feb?style=for-the-badge&logo=github&logoColor=white&labelColor=0d1117" />
<br />
<img alt="Role: Full-Stack Developer" src="https://img.shields.io/badge/ROLE-Full--Stack_Developer-1f6feb?style=for-the-badge&labelColor=0d1117" />
<img alt="Orgs: 8" src="https://img.shields.io/badge/ORGS-8-1f6feb?style=for-the-badge&labelColor=0d1117" />
<img alt="Focus: MSA & Event-Driven" src="https://img.shields.io/badge/FOCUS-MSA_%26_Event--Driven-1f6feb?style=for-the-badge&labelColor=0d1117" />
<img alt="Since Jan 2021" src="https://img.shields.io/badge/SINCE-Jan_2021-1f6feb?style=for-the-badge&labelColor=0d1117" />

<br /><br />

<img height="165" alt="streak" src="https://github-readme-streak-stats.herokuapp.com/?user=VelkaressiaBlutkrone&hide_border=true&background=0d1117&stroke=1f6feb&ring=58a6ff&fire=58a6ff&currStreakLabel=c9d1d9&sideLabels=c9d1d9&dates=8b8b8b&currStreakNum=f0f6fc&sideNums=f0f6fc" />

</div>

> 주요 작업은 비공개/조직 레포에 있어 공개 통계에 모두 잡히지 않습니다 — Featured Projects와 Journey가 실제 작업을 보여줍니다.
> *Most work lives in private & org repos and isn't fully reflected here — see Featured Projects and Journey for the real picture.*

---

<!-- ═══════════════ ⑦ Contact ═══════════════ -->
## 📫 Contact

<p align="center">
<a href="https://github.com/VelkaressiaBlutkrone"><img src="https://img.shields.io/badge/GitHub-1f6feb?style=for-the-badge&logo=github&logoColor=white" /></a>
<a href="mailto:deepestdark@gmail.com"><img src="https://img.shields.io/badge/Email-1f6feb?style=for-the-badge&logo=gmail&logoColor=white" /></a>
</p>

<img width="100%" alt="footer" src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:1f6feb,100:0d1117&height=120&section=footer" />
````

- [ ] **Step 2: 판타지 잔존 문구 검사**

Run: `grep -inE "necromancer|강령|마법|마도|룬|결계|소환|봉인|왕관|grimoire|rune|ward|awakened|stronghold|의식|석판|혈|blood" /d/workspace/velkaressiaBlutkrone/README.md`
Expected: 매치 0건 (exit code 1). 매치가 나오면 해당 문구를 스펙 §3의 대응 문구로 교체 후 재실행.

- [ ] **Step 3: 구색상 잔존 검사**

Run: `grep -icE "8B0000|B22222|6d0000|2b0000|0a0000" /d/workspace/velkaressiaBlutkrone/README.md`
Expected: `0` (exit code 1). 매치가 나오면 `1f6feb` 팔레트로 교체 후 재실행.

- [ ] **Step 4: 커밋**

```bash
git -C /d/workspace/velkaressiaBlutkrone add README.md
git -C /d/workspace/velkaressiaBlutkrone commit -m "feat: 프로필 README 프로페셔널 리모델 (판타지 콘셉트 제거)"
```

### Task 2: 외부 URL 전수 검증

**Files:**
- Modify: `README.md` (검증 실패 URL 발견 시에만 수정)

**Interfaces:**
- Consumes: Task 1이 작성한 `README.md`
- Produces: 전체 URL이 HTTP 200을 반환하는 검증 완료된 `README.md`

- [ ] **Step 1: URL 전수 추출 및 상태 코드 확인**

```bash
grep -oE 'https://[^")<> ]+' /d/workspace/velkaressiaBlutkrone/README.md | sort -u | while read u; do
  code=$(curl -s -o /dev/null -w '%{http_code}' -L --max-time 30 "$u")
  echo "$code $u"
done
```

Expected: 모든 행이 `200`으로 시작.
- `github-readme-streak-stats.herokuapp.com`은 콜드 스타트로 첫 요청이 503일 수 있음 — 해당 URL만 1회 재시도해 200이면 통과.
- `mailto:` 링크는 https가 아니므로 검증 대상에 포함되지 않음(정상).

- [ ] **Step 2: 실패 URL이 있으면 수정 후 Step 1 재실행**

실패 원인은 대부분 URL 인코딩 오류(한글·`·`·`&` 문자). 스펙 §2의 인코딩 값과 대조해 교정한다. 수정이 없었다면 이 단계와 Step 3을 건너뛴다.

- [ ] **Step 3: 수정이 있었다면 커밋**

```bash
git -C /d/workspace/velkaressiaBlutkrone add README.md
git -C /d/workspace/velkaressiaBlutkrone commit -m "fix: 배지/이미지 URL 교정"
```

### Task 3: PR 생성 및 머지 (develop → 릴리스)

**Files:**
- 없음 (git 작업만)

**Interfaces:**
- Consumes: Task 1·2가 완성한 `feat/profile-remodel` 브랜치
- Produces: `main`에 머지된 리모델 README (프로필 공개 반영)

- [ ] **Step 1: 브랜치 푸시 및 develop 대상 PR 생성**

```bash
git -C /d/workspace/velkaressiaBlutkrone push -u origin feat/profile-remodel
gh pr create --repo VelkaressiaBlutkrone/VelkaressiaBlutkrone --base develop --head feat/profile-remodel --title "feat: 프로필 README 프로페셔널 리모델" --body "판타지 콘셉트 전면 제거, GitHub 다크 뉴트럴 팔레트 적용. 스펙: docs/superpowers/specs/2026-08-29-profile-remodel-design.md

🤖 Generated with [Claude Code](https://claude.com/claude-code)"
```

- [ ] **Step 2: PR 머지 (이 레포는 CI 없음 — 상태 체크 없이 머지)**

```bash
gh pr merge --repo VelkaressiaBlutkrone/VelkaressiaBlutkrone --merge feat/profile-remodel
```

- [ ] **Step 3: 릴리스 PR (develop → main) 생성 및 머지**

```bash
gh pr create --repo VelkaressiaBlutkrone/VelkaressiaBlutkrone --base main --head develop --title "release: 프로필 README 프로페셔널 리모델" --body "develop → main 릴리스. 프로필 리모델 반영.

🤖 Generated with [Claude Code](https://claude.com/claude-code)"
gh pr merge --repo VelkaressiaBlutkrone/VelkaressiaBlutkrone --merge develop
```

- [ ] **Step 4: 최종 확인**

Run: `git -C /d/workspace/velkaressiaBlutkrone fetch origin && git -C /d/workspace/velkaressiaBlutkrone log origin/main --oneline -3`
Expected: 릴리스 머지 커밋이 최상단에 존재. 이후 https://github.com/VelkaressiaBlutkrone 프로필 페이지에서 렌더링을 확인한다.
