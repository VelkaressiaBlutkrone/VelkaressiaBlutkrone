# 프로필 README 구현 계획 (The Grimoire of Velkaressia Blutkrone)

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** `VelkaressiaBlutkrone/VelkaressiaBlutkrone` 프로필 특수 레포를 생성하고, 다크 판타지 "마도서" 컨셉의 한·영 병기 프로필 `README.md`를 작성해 GitHub 프로필에 렌더링한다.

**Architecture:** 단일 `README.md`(로컬 이미지 자산 없음)를 외부 SVG 서비스(capsule-render·readme-typing-svg·shields.io·github-readme-stats·streak-stats)로 꾸민다. 콘텐츠는 실측한 개인/조직 레포 데이터에 근거한 솔직한 성장 서사(예제·수련 → 분산 AI 플랫폼 아키텍트)를 마도서 은유로 연출한다. 플래그십은 DevPath AI + Synapse 두 기둥.

**Tech Stack:** Markdown · GitHub CLI(`gh`) · git · 외부 SVG 배지/카드 서비스

## Global Constraints

- 대상 레포: `VelkaressiaBlutkrone/VelkaressiaBlutkrone` — **public**, GitHub 프로필 특수 레포. README는 **기본 브랜치(main)** 에 있어야 프로필에 렌더링됨.
- 언어: **한·영 병기**. 톤: **다크 판타지 페르소나(마도서)**. 서사: **솔직** — 실재하는 레포/기술만 기술, 없는 경력·자격 창작 금지.
- 배지 색 통일: 모든 shields 배지 배경 `8B0000`(다크 레드), `logoColor=white`, `style=for-the-badge`.
- 통계 카드 색: `title_color=b22222`, `icon_color=8b0000`, `text_color=c9d1d9`, `bg_color=0d1117`, `hide_border=true`.
- Footer 연락처: GitHub + 이메일 `deepestdark@gmail.com` 포함.
- 외부 서비스 flakiness: `github-readme-stats`(Vercel)는 간헐적 503 발생 가능 → 검증 시 재시도 허용, 실패해도 문서는 독립적으로 읽히게(텍스트 우선).
- 작업 디렉토리: `D:\workspace\velkaressiaBlutkrone` (현재 branch `master`에 스펙 커밋 1개, 리모트 없음).
- 링크는 실측 검증된 org 레포 URL만 사용(계획 작성 시 전부 200 확인 완료).

---

## 파일 구조 (File Structure)

- Create: `README.md` — 프로필 본문(전 섹션). 단일 파일, 유일한 사용자 대면 산출물.
- 기존: `docs/superpowers/specs/2026-07-29-profile-readme-design.md`(설계), `docs/superpowers/plans/2026-07-29-profile-readme.md`(본 계획). 수정 없음.

---

## 브랜치·배포 전략 (확정)

프로필 특수 레포이므로 README는 기본 브랜치(main)에 있어야 한다. 공통 규칙("main 직접 push 금지, PR 경유")을 다음과 같이 절충 적용한다:

1. **부트스트랩**: 로컬 `master`→`main` 리네임 후, 신규 GitHub public 레포를 만들고 기존 스펙/계획 커밋으로 main을 **최초 시드**한다(빈 레포 초기화이므로 예외).
2. **README 작업**: `feat/profile-readme` 브랜치에서 README를 작성·커밋한다.
3. **반영**: `feat/profile-readme` → `main` **PR**을 올려 사용자 승인/머지로 반영한다(직접 push 대신 PR 경유로 규칙 준수). develop 계층은 단일 파일 개인 프로필 레포 특성상 생략한다.

---

## Task 1: 레포 부트스트랩 + 브랜치 셋업

**Files:**
- 없음(레포/브랜치/리모트 설정만)

**Interfaces:**
- Produces: GitHub public 레포 `VelkaressiaBlutkrone/VelkaressiaBlutkrone`(default branch `main`), 로컬 리모트 `origin`, 작업 브랜치 `feat/profile-readme`.

- [ ] **Step 1: 로컬 기본 브랜치를 main으로 정렬**

Run:
```bash
cd "D:/workspace/velkaressiaBlutkrone"
git branch -m master main
git log --oneline   # 스펙+계획 커밋이 보여야 함
```
Expected: 현재 브랜치 `main`, 기존 커밋 유지.

- [ ] **Step 2: 계획 파일까지 커밋(아직 미커밋이면)**

Run:
```bash
cd "D:/workspace/velkaressiaBlutkrone"
git add docs/superpowers/plans/2026-07-29-profile-readme.md
git commit -m "docs: 프로필 README 구현 계획 추가

Co-Authored-By: Claude Opus 4.8 (1M context) <noreply@anthropic.com>" || echo "이미 커밋됨(스킵)"
```
Expected: 계획 파일 커밋 또는 스킵.

- [ ] **Step 3: GitHub public 레포 생성 + origin 연결 + main 시드 push**

Run:
```bash
cd "D:/workspace/velkaressiaBlutkrone"
gh repo create VelkaressiaBlutkrone/VelkaressiaBlutkrone \
  --public \
  --description "🩸 Velkaressia Blutkrone — profile grimoire" \
  --source . --remote origin --push
```
Expected: 레포 생성, `origin` 등록, `main`이 원격으로 push됨.
Note: `--source . --push`는 현재 브랜치(main)를 push한다. 만약 계정 프로필 렌더링을 위해 org가 아닌 개인 네임스페이스가 필요하므로 슬러그는 반드시 `VelkaressiaBlutkrone/VelkaressiaBlutkrone`.

- [ ] **Step 4: 원격 기본 브랜치가 main인지 확인**

Run:
```bash
gh repo view VelkaressiaBlutkrone/VelkaressiaBlutkrone --json defaultBranchRef --jq '.defaultBranchRef.name'
```
Expected: `main`

- [ ] **Step 5: 작업 브랜치 생성**

Run:
```bash
cd "D:/workspace/velkaressiaBlutkrone"
git switch -c feat/profile-readme
git status -sb
```
Expected: 브랜치 `feat/profile-readme`.

---

## Task 2: README.md 작성

**Files:**
- Create: `README.md`

**Interfaces:**
- Consumes: Task 1의 레포/브랜치.
- Produces: 완성된 `README.md`(전 섹션). Task 3이 링크/이미지 URL을 검증.

- [ ] **Step 1: README.md를 아래 내용 그대로 작성**

`D:\workspace\velkaressiaBlutkrone\README.md` 파일에 다음 내용을 **그대로** 쓴다(값 임의 변경 금지):

````markdown
<!-- ═══════════════ ① 표제 · Cover ═══════════════ -->
<div align="center">

<img alt="Velkaressia Blutkrone" width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:2b0000,50:6d0000,100:0a0000&height=230&section=header&text=Velkaressia%20Blutkrone&fontSize=54&fontColor=f2e9e9&fontAlignY=40&desc=Necromancer%20of%20Code&descSize=20&descAlignY=62" />

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Noto+Sans+KR&size=22&duration=3600&pause=900&color=B22222&center=true&vCenter=true&width=820&height=55&lines=코드의+강령술사+·+Necromancer+of+Code;수련생에서+아키텍트로+·+From+apprentice+to+architect;분산+시스템을+벼리는+자+·+Forging+distributed+systems)](https://github.com/VelkaressiaBlutkrone)

**🩸 피의 왕관을 쓴 풀스택 강령술사 · A full-stack necromancer, crowned in blood 🩸**

*예제·수련의 잿더미에서 분산 시스템을 벼려내는 중*
*Forging distributed systems from the ashes of a thousand exercises*

</div>

---

<!-- ═══════════════ ② 소환의 장 · About ═══════════════ -->
## 🩸 소환의 장 · Summoning

> *어둠 속에서 코드가 깨어난다. 백엔드의 관(棺), 프론트의 첨탑, 모바일의 결계를 오가며 시스템에 생명을 불어넣는다.*
> *From the dark, code awakens — I move between the crypt of the backend, the spire of the frontend, and the wards of mobile, breathing life into systems.*

- 🗡️ **풀스택 · Full-stack** — Spring(백엔드) · React(프론트) · Flutter(모바일)을 하나의 의식(儀式)으로
- 🩸 **성장의 아크 · The arc** — 예제·수련 → 이벤트 기반 분산 시스템 아키텍처 · from exercises to event-driven distributed architecture
- 🔮 **현재의 탐구 · Now delving into** — MSA · Event-Driven · Kubernetes / GitOps · AI Orchestration
- 🏰 **거점 · Strongholds** — 8개 조직에서 팀 프로젝트를 이끄는 중 · leading team projects across 8 orgs

---

<!-- ═══════════════ ③ 대마법서 서고 · Flagship ═══════════════ -->
## 📜 대마법서 서고 · The Grimoire Vault

두 권의 대마법서가 서고의 중심을 차지한다. · *Two grand grimoires anchor the vault.*

### 📕 DevPath AI — *AI 개발자 학습 플랫폼 · An AI-driven developer-learning platform*

이벤트 기반 마이크로서비스로 짜인 대규모 학습 플랫폼.
*A large-scale learning platform woven from event-driven microservices.*

- ⚙️ **아키텍처 · Architecture** — OAuth2 / JWT 엣지 게이트웨이 · 이벤트 기반 서비스 분해 · Kubernetes GitOps 배포
- 🧪 **격리 실행 · Isolated execution** — `sandbox-svc`가 **Docker + gVisor**로 사용자 코드를 봉인해 실행
- 🤖 **AI 계층 · AI layer** — AI 게이트웨이 오케스트레이터 · 리뷰 워커 · FinOps 비용 통제
- 🧩 **구성 · Services** —
[gateway](https://github.com/DevPathAi/devpath-gateway) ·
[platform-svc](https://github.com/DevPathAi/devpath-platform-svc) ·
[ai-svc](https://github.com/DevPathAi/devpath-ai-svc) ·
[learning-svc](https://github.com/DevPathAi/devpath-learning-svc) ·
[sandbox-svc](https://github.com/DevPathAi/devpath-sandbox-svc) ·
[community-svc](https://github.com/DevPathAi/devpath-community-svc) ·
[gitops](https://github.com/DevPathAi/devpath-gitops) ·
[frontend](https://github.com/DevPathAi/devpath-frontend)

<p>
<img src="https://img.shields.io/badge/Java-8B0000?style=for-the-badge&logo=openjdk&logoColor=white" />
<img src="https://img.shields.io/badge/Spring_Boot-8B0000?style=for-the-badge&logo=springboot&logoColor=white" />
<img src="https://img.shields.io/badge/Python-8B0000?style=for-the-badge&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/Docker-8B0000?style=for-the-badge&logo=docker&logoColor=white" />
<img src="https://img.shields.io/badge/Kubernetes-8B0000?style=for-the-badge&logo=kubernetes&logoColor=white" />
<img src="https://img.shields.io/badge/gVisor-8B0000?style=for-the-badge&logo=google&logoColor=white" />
</p>

### 📗 Synapse — *8개 서비스 MSA 플랫폼 · An 8-service microservices platform*

git submodule 엄브렐러로 묶인 도메인 지향 분산 시스템.
*A domain-oriented distributed system bound by a git-submodule umbrella.*

- 🕸️ **엄브렐러 · Umbrella** — `synapse` 메타 레포가 서비스/인프라를 submodule로 통합
- 📐 **계약 · Contracts** — `synapse-shared`의 **Avro 스키마** + 공통 라이브러리
- 🚀 **배포 · Delivery** — **Kubernetes + ArgoCD ApplicationSet** GitOps
- 🧩 **도메인 · Domains** —
[🏛 umbrella](https://github.com/team-project-final/synapse) ·
[gateway](https://github.com/team-project-final/synapse-gateway) ·
[platform-svc](https://github.com/team-project-final/synapse-platform-svc) ·
[knowledge-svc](https://github.com/team-project-final/synapse-knowledge-svc) ·
[engagement-svc](https://github.com/team-project-final/synapse-engagement-svc) ·
[learning-svc](https://github.com/team-project-final/synapse-learning-svc) ·
[shared](https://github.com/team-project-final/synapse-shared) ·
[frontend](https://github.com/team-project-final/synapse-frontend) ·
[gitops](https://github.com/team-project-final/synapse-gitops)

<p>
<img src="https://img.shields.io/badge/Java-8B0000?style=for-the-badge&logo=openjdk&logoColor=white" />
<img src="https://img.shields.io/badge/Spring_Boot-8B0000?style=for-the-badge&logo=springboot&logoColor=white" />
<img src="https://img.shields.io/badge/Apache_Avro-8B0000?style=for-the-badge&logo=apache&logoColor=white" />
<img src="https://img.shields.io/badge/Kubernetes-8B0000?style=for-the-badge&logo=kubernetes&logoColor=white" />
<img src="https://img.shields.io/badge/Argo_CD-8B0000?style=for-the-badge&logo=argo&logoColor=white" />
<img src="https://img.shields.io/badge/Flutter-8B0000?style=for-the-badge&logo=flutter&logoColor=white" />
</p>

---

<!-- ═══════════════ ④ 무기고 · Arsenal ═══════════════ -->
## ⚔️ 무기고 · Arsenal

**🩸 Languages**
<p>
<img src="https://img.shields.io/badge/Java-8B0000?style=for-the-badge&logo=openjdk&logoColor=white" />
<img src="https://img.shields.io/badge/Dart-8B0000?style=for-the-badge&logo=dart&logoColor=white" />
<img src="https://img.shields.io/badge/TypeScript-8B0000?style=for-the-badge&logo=typescript&logoColor=white" />
<img src="https://img.shields.io/badge/Python-8B0000?style=for-the-badge&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/JavaScript-8B0000?style=for-the-badge&logo=javascript&logoColor=white" />
<img src="https://img.shields.io/badge/C%23-8B0000?style=for-the-badge&logo=dotnet&logoColor=white" />
</p>

**🗡️ Backend**
<p>
<img src="https://img.shields.io/badge/Spring_Boot-8B0000?style=for-the-badge&logo=springboot&logoColor=white" />
<img src="https://img.shields.io/badge/Spring_Cloud_Gateway-8B0000?style=for-the-badge&logo=spring&logoColor=white" />
</p>

**🔮 Frontend**
<p>
<img src="https://img.shields.io/badge/React-8B0000?style=for-the-badge&logo=react&logoColor=white" />
<img src="https://img.shields.io/badge/Flutter-8B0000?style=for-the-badge&logo=flutter&logoColor=white" />
<img src="https://img.shields.io/badge/Riverpod-8B0000?style=for-the-badge&logo=riverpod&logoColor=white" />
</p>

**🗄️ Data**
<p>
<img src="https://img.shields.io/badge/MySQL-8B0000?style=for-the-badge&logo=mysql&logoColor=white" />
<img src="https://img.shields.io/badge/MongoDB-8B0000?style=for-the-badge&logo=mongodb&logoColor=white" />
<img src="https://img.shields.io/badge/Firestore-8B0000?style=for-the-badge&logo=firebase&logoColor=white" />
<img src="https://img.shields.io/badge/Apache_Avro-8B0000?style=for-the-badge&logo=apache&logoColor=white" />
</p>

**🏰 Infra & DevOps**
<p>
<img src="https://img.shields.io/badge/Docker-8B0000?style=for-the-badge&logo=docker&logoColor=white" />
<img src="https://img.shields.io/badge/Kubernetes-8B0000?style=for-the-badge&logo=kubernetes&logoColor=white" />
<img src="https://img.shields.io/badge/Argo_CD-8B0000?style=for-the-badge&logo=argo&logoColor=white" />
<img src="https://img.shields.io/badge/gVisor-8B0000?style=for-the-badge&logo=google&logoColor=white" />
<img src="https://img.shields.io/badge/AWS-8B0000?style=for-the-badge&logo=amazonwebservices&logoColor=white" />
</p>

**🤖 AI**
<p>
<img src="https://img.shields.io/badge/LLM_Orchestration-8B0000?style=for-the-badge&logo=openai&logoColor=white" />
<img src="https://img.shields.io/badge/Python_AI_Service-8B0000?style=for-the-badge&logo=python&logoColor=white" />
</p>

---

<!-- ═══════════════ ⑤ 연대기 · Chronicle ═══════════════ -->
## 🕯️ 연대기 · Chronicle

> *한 줄의 예제에서 하나의 왕국으로. · From a single exercise to a kingdom of services.*

**🕯️ 제1막 — 수련 · Apprenticeship** *(2025 말 · late 2025)*
Java / Spring 기초, 서블릿·소켓·게시판 예제, Flutter Firestore / Riverpod로 첫 결계를 세우다.

**🔥 제2막 — 확장 · Expansion** *(2026 상반기 · H1 2026)*
풀스택 통합(Spring + React + Flutter), MSA 입문, 병원 시스템 [HMS](https://github.com/proejct-team-alpha/hms) 팀 프로젝트, Docker·AWS로 영역을 넓히다.

**👑 제3막 — 정립 · Ascension** *(2026 중반 · mid 2026)*
[Synapse](https://github.com/team-project-final/synapse)(8-svc MSA + GitOps)와 [DevPath AI](https://github.com/DevPathAi)(이벤트 드리븐 · gVisor 격리 · AI 오케스트레이션)로 분산 시스템의 왕관을 벼리다.

---

<!-- ═══════════════ ⑥ 룬 석판 · Stats ═══════════════ -->
## 🔮 룬 석판 · Runestones

<div align="center">

<img height="165" alt="stats" src="https://github-readme-stats.vercel.app/api?username=VelkaressiaBlutkrone&show_icons=true&hide_border=true&title_color=b22222&icon_color=8b0000&text_color=c9d1d9&bg_color=0d1117" />
<img height="165" alt="top languages" src="https://github-readme-stats.vercel.app/api/top-langs/?username=VelkaressiaBlutkrone&layout=compact&hide_border=true&title_color=b22222&text_color=c9d1d9&bg_color=0d1117" />

<img height="165" alt="streak" src="https://github-readme-streak-stats.herokuapp.com/?user=VelkaressiaBlutkrone&hide_border=true&background=0d1117&stroke=8b0000&ring=b22222&fire=b22222&currStreakLabel=c9d1d9&sideLabels=c9d1d9&dates=8b8b8b&currStreakNum=f2e9e9&sideNums=f2e9e9" />

</div>

> 🩸 *봉인된 서고(비공개 레포)의 힘은 룬에 새겨지지 않는다 — 무기고와 연대기가 진짜 이야기를 전한다.*
> *The sealed vault (private repos) is not etched into these runes — the Arsenal and the Chronicle tell the true tale.*

---

<!-- ═══════════════ ⑦ 결계 · Contact ═══════════════ -->
## 🕸️ 결계 · Wards

<p align="center">
<a href="https://github.com/VelkaressiaBlutkrone"><img src="https://img.shields.io/badge/GitHub-8B0000?style=for-the-badge&logo=github&logoColor=white" /></a>
<a href="mailto:deepestdark@gmail.com"><img src="https://img.shields.io/badge/Email-8B0000?style=for-the-badge&logo=gmail&logoColor=white" /></a>
</p>

<img width="100%" alt="footer" src="https://capsule-render.vercel.app/api?type=waving&color=0:0a0000,50:6d0000,100:2b0000&height=120&section=footer" />
````

- [ ] **Step 2: 파일이 생성되고 섹션 헤더가 모두 있는지 확인**

Run:
```bash
cd "D:/workspace/velkaressiaBlutkrone"
grep -c "^## " README.md   # 소환/서고/무기고/연대기/룬석판/결계 = 6
```
Expected: `6`

- [ ] **Step 3: 커밋**

Run:
```bash
cd "D:/workspace/velkaressiaBlutkrone"
git add README.md
git commit -m "feat: 다크 판타지 마도서 프로필 README 추가

Velkaressia Blutkrone 프로필 — 한·영 병기, 성장 아크 서사.
플래그십 DevPath AI + Synapse, 기술 스택 배지, GitHub 통계 카드.

Co-Authored-By: Claude Opus 4.8 (1M context) <noreply@anthropic.com>"
git log --oneline -1
```
Expected: README 커밋 생성.

---

## Task 3: 링크·이미지 검증 및 로컬 렌더 확인

**Files:**
- 없음(검증만; 실패 시 README.md 수정)

**Interfaces:**
- Consumes: Task 2의 `README.md`.
- Produces: 모든 참조 URL 200 확인(또는 flaky 서비스는 재시도 후 판정).

- [ ] **Step 1: README에 등장하는 모든 github.com 레포 링크가 존재하는지 확인**

Run:
```bash
cd "D:/workspace/velkaressiaBlutkrone"
grep -oE "https://github.com/[A-Za-z0-9_.-]+/[A-Za-z0-9_.-]+" README.md | sort -u | while read url; do
  path="${url#https://github.com/}"
  gh api "repos/$path" --jq '"OK  "+.full_name' 2>/dev/null || echo "MISS  $url"
done
```
Expected: 모든 줄이 `OK` (org 루트 링크 `DevPathAi`/`VelkaressiaBlutkrone`는 repos API 대상이 아니므로 `MISS`로 나올 수 있음 — 이는 정상. repo 형태 링크만 OK면 통과).
Note: `MISS`가 org/user 루트(`DevPathAi`, `VelkaressiaBlutkrone`, `team-project-final`) 외 실제 레포 경로에서 뜨면 오타 → 수정.

- [ ] **Step 2: 외부 이미지 서비스 URL이 응답하는지 확인(플래키 서비스 재시도)**

Run:
```bash
cd "D:/workspace/velkaressiaBlutkrone"
grep -oE "https://(img\.shields\.io|capsule-render\.vercel\.app|readme-typing-svg\.demolab\.com|github-readme-stats\.vercel\.app|github-readme-streak-stats\.herokuapp\.com)[^\" )]+" README.md | sort -u | while read url; do
  code=""
  for i in 1 2 3; do
    code=$(curl -s -o /dev/null -w "%{http_code}" --max-time 20 "$url")
    [ "$code" = "200" ] && break
    sleep 3
  done
  echo "$code  $url"
done
```
Expected: 대부분 `200`. `github-readme-stats.vercel.app`가 재시도 후에도 `503`이면 서비스 일시 장애로 간주하고 통과(카드는 서비스 복구 시 자동 렌더). shields/capsule/typing/streak은 `200`이어야 함 — 아니면 슬러그/URL 오타 수정.

- [ ] **Step 3: 로컬 마크다운 렌더 미리보기(선택)**

Run:
```bash
cd "D:/workspace/velkaressiaBlutkrone"
gh markdown README.md 2>/dev/null | head -40 || echo "gh markdown 미지원 — GitHub 웹에서 육안 확인으로 대체"
```
Expected: 렌더 텍스트 출력 또는 대체 안내(치명적 아님).

- [ ] **Step 4: (수정이 있었으면) 커밋**

Run:
```bash
cd "D:/workspace/velkaressiaBlutkrone"
if ! git diff --quiet; then
  git add README.md
  git commit -m "fix: 프로필 README 링크/배지 URL 교정

Co-Authored-By: Claude Opus 4.8 (1M context) <noreply@anthropic.com>"
fi
git log --oneline -3
```
Expected: 수정분 커밋 또는 변경 없음.

---

## Task 4: 푸시 · PR · 머지 · 프로필 렌더 확인

**Files:**
- 없음

**Interfaces:**
- Consumes: `feat/profile-readme` 브랜치의 완성 README.
- Produces: `main`에 README 반영, GitHub 프로필에 렌더링.

- [ ] **Step 1: 작업 브랜치 push**

Run:
```bash
cd "D:/workspace/velkaressiaBlutkrone"
git push -u origin feat/profile-readme
```
Expected: 원격에 `feat/profile-readme` 생성.

- [ ] **Step 2: PR 생성(feat → main)**

Run:
```bash
cd "D:/workspace/velkaressiaBlutkrone"
gh pr create --base main --head feat/profile-readme \
  --title "feat: 다크 판타지 마도서 프로필 README" \
  --body "$(cat <<'EOF'
## 요약
Velkaressia Blutkrone 프로필 README(마도서 컨셉, 한·영 병기).

- 플래그십: DevPath AI + Synapse 두 기둥
- 무기고(기술 스택 배지) · 연대기(성장 아크) · 룬 석판(GitHub 통계)
- 설계: docs/superpowers/specs/2026-07-29-profile-readme-design.md

🤖 Generated with [Claude Code](https://claude.com/claude-code)
EOF
)"
```
Expected: PR URL 출력.
**STOP — 사용자 승인 대기.** 사용자가 PR을 확인/승인하면 다음 단계 진행.

- [ ] **Step 3: 머지(사용자 승인 후)**

Run:
```bash
cd "D:/workspace/velkaressiaBlutkrone"
gh pr merge feat/profile-readme --merge --delete-branch
git switch main && git pull --ff-only origin main
```
Expected: `main`에 머지, 로컬 main 최신화.

- [ ] **Step 4: 프로필 렌더링 확인**

Run:
```bash
gh api repos/VelkaressiaBlutkrone/VelkaressiaBlutkrone/readme --jq '.name'
echo "브라우저에서 확인: https://github.com/VelkaressiaBlutkrone"
```
Expected: `README.md`. GitHub 프로필 페이지 상단에 카드가 렌더됨(육안 확인).

---

## Self-Review (계획↔스펙 대조)

**1. 스펙 커버리지**
- ① 표제 → Task 2 배너/타이핑/태그라인 ✓
- ② 소환의 장 → Task 2 About 목록 ✓
- ③ 대마법서 서고(DevPath AI + Synapse) → Task 2 두 서브섹션 + 배지 + 실측 레포 링크 ✓
- ④ 무기고(스택 배지, 다크레드 통일) → Task 2 Arsenal 6그룹 ✓
- ⑤ 연대기(3막 솔직 타임라인) → Task 2 Chronicle ✓
- ⑥ 룬 석판(stats/top-langs/streak, 비공개 주의 문구) → Task 2 Runestones + 안내 blockquote ✓
- ⑦ 결계(GitHub + 이메일 + footer) → Task 2 Wards ✓
- 브랜치/배포 상충 처리 → "브랜치·배포 전략" + Task 1/4 ✓
- 외부 서비스 flakiness → Global Constraints + Task 3 Step 2 재시도 ✓

**2. Placeholder 스캔:** TBD/TODO/"적절히 처리" 없음. 모든 URL·배지·문구 확정값. ✓

**3. 타입/값 일관성:** 배지 색 `8B0000`, 카드 색 파라미터, 레포 슬러그(`proejct-team-alpha` 오탈자 그대로 — 실제 org 이름이 그러함) 전 태스크 일치. 통계 카드 username `VelkaressiaBlutkrone` 일치. ✓

**주의(실측 반영):** org 이름 `proejct-team-alpha`, `Public-Project-Area-Oragans`는 실제 GitHub상의 (오타 포함) 정확한 이름이므로 그대로 사용한다.
