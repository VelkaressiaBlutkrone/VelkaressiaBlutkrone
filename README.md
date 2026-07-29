<!-- ═══════════════ ① 표제 · Cover ═══════════════ -->
<div align="center">

<img alt="Velkaressia Blutkrone" width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:2b0000,50:6d0000,100:0a0000&height=230&section=header&text=Velkaressia%20Blutkrone&fontSize=54&fontColor=f2e9e9&fontAlignY=40&desc=Necromancer%20of%20Code&descSize=20&descAlignY=62" />

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Noto+Sans+KR&size=22&duration=3600&pause=900&color=B22222&center=true&vCenter=true&width=820&height=55&lines=%EC%BD%94%EB%93%9C%EC%9D%98+%EA%B0%95%EB%A0%B9%EC%88%A0%EC%82%AC+%C2%B7+Necromancer+of+Code;%EC%88%98%EB%A0%A8%EC%83%9D%EC%97%90%EC%84%9C+%EC%95%84%ED%82%A4%ED%85%8D%ED%8A%B8%EB%A1%9C+%C2%B7+From+apprentice+to+architect;%EB%B6%84%EC%82%B0+%EC%8B%9C%EC%8A%A4%ED%85%9C%EC%9D%84+%EB%B2%BC%EB%A6%AC%EB%8A%94+%EC%9E%90+%C2%B7+Forging+distributed+systems)](https://github.com/VelkaressiaBlutkrone)

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
