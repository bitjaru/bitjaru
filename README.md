# Sunwoo Kim (김선우)

**Fullstack engineer & CTO. 12 years. I ship products — and I keep them running.**

Building fast is table stakes now. Anyone can generate a screen.
What I do is design the thing behind the screen so it doesn't fall over — and then actually operate it.

- 🏗️ CTO @ YAYLABS · Co-founder @ YayPlanet — built **Oildealer solo**: escrow-backed B2B reverse-auction platform, **3 client apps (customer web+mobile, vendor, admin), live on both app stores**, 5 microservices on Kubernetes
- 🎨 I build without designers. Not "AI-looking" UI — I wrote a design system that teaches AI design *judgment*, and open-sourced it
- 📊 ML in production, not in notebooks — LSTM price model at 0.74% MAPE, beat GARCH/VAR/XGBoost
- ⛓️ Web3 at scale — transaction forwarding API serving 300K game users, 100+ TPS
- 🏢 Before this: eBay Korea (led legacy → React SPA migration), Samsung Card (Vue/Nuxt architecture)

---

## What I actually do

| | |
|---|---|
| **Depth, not just breadth** | Led a legacy (JSP/jQuery/.NET) → React SPA migration on a live commerce platform. Page load −60%, DB load −40%. Nothing broke. |
| **0→1 with architecture** | Took a product from "we have an idea" to shipped MVP as a contractor — auth, payments, points, raffle engine, community, admin. |
| **Design without a designer** | [styleseed](https://github.com/bitjaru/styleseed) — 74 design rules, 48 components, 7 brand skins. The tool I built to fix the UI that AI coding tools generate. |
| **Infra that stays up** | Kubernetes, zero-downtime deploys, CI/CD, Saga-pattern event-driven orchestration. Running today, not a demo. |
| **AI as a pipeline, not a demo** | Agent workflows that scan → analyze → render → package, with a human gate before publish. |

---

## Selected work

### Oildealer — escrow-backed B2B reverse-auction platform (built solo, live on both stores)
CTO. Planning → architecture → development → design → operations. **One person, end to end.**

Everything a production service needs, in one project: **reverse auction · escrow payments · community · ML price forecasting · monitoring · web ordering · customer app · vendor app · admin**.
**3 client apps built solo** — customer (web-only + app-only), vendor, admin — **shipped to both iOS/Android stores** and operated since (review cycles, rejections, version rollouts included).
5 microservices (dual frontend / collection API / business backend / scheduler / admin) on Kubernetes, zero-downtime.
MongoDB Time Series + Redis. Playwright-based market data pipeline. GPT-4o news agent with daily briefing.
In-house LSTM price forecasting — **MAPE 0.74%, 88% directional accuracy**, benchmarked against GARCH · VAR · VECM · XGBoost.
Windows agent syncing POS + tank sensors on site. **Zero designers on the project.**

### Transaction forwarding API — LINE × Kaia
Redis + message queue architecture that decouples transaction submission from service logic.
Sidesteps nonce collisions and rate limits by queueing instead of hammering the chain. Retries, backoff, failure replay.
**300K game users. 100+ TPS at peak.**

### NNN — Telegram × TON gamefi launchpad
Launchpad backend (Node/Express, layered), TON smart contracts, Telegram mini-app frontend, partner-game integration API.
Probability-driven mystery box engine with externalized probability tables. Weekly reward distribution via cron, with recovery path on failed payouts.
Partner games integrated in under a day.

### MARKET WHY — AI narration video pipeline
Script → TTS (SSML-controlled) → **scene timing auto-matched to the actual audio length** → subtitles → thumbnail → publish package.
The sync isn't eyeballed on a timeline; the voice length determines the scene length. Change the script, re-render, still in sync.
Runs headless on a schedule. Publishing stays a human decision.

---

## Open source

**[styleseed](https://github.com/bitjaru/styleseed)** — *Teach your AI design judgment. Not just components.*
Design system engine for Claude Code / Codex / Cursor. 74 rules, 48 components, 7 brand skins (Toss/Stripe/Linear/Notion/Raycast/Arc/Vercel), a named motion system. MIT.

**[codesyncer](https://github.com/bitjaru/codesyncer)** — *Claude forgets everything when the session ends. CodeSyncer makes it remember.*
Multi-repo collaboration framework for AI coding agents. Decisions and inferences get recorded as `@codesyncer-*` tags instead of evaporating. On npm. Oildealer actually runs on it.

**[pixelmind](https://github.com/bitjaru/pixelmind)** — *Your LLM is blind to what it creates. We give it eyes.*
Render-aware feedback loop for LLM-generated UI.

---

## Experience

| | | |
|---|---|---|
| 2025.12 – | **YayPlanet** | Co-Founder |
| 2022.05 – | **YAYLABS** | **CTO & Co-Founder** |
| 2021.12 – 2022.05 | **Samsung Card** | Frontend (CL3) — Vue/Nuxt architecture for a new service |
| 2017.07 – 2022.05 | **eBay Korea** | Software Engineer — Smile Club. Led legacy → React SPA migration |
| 2014.01 – 2017.02 | Research (military service) | Intrusion-tolerant systems, Xen hypervisor-based detection |

**M.S. Computer Science**, Hanyang University — Computer Network Security Lab

---

## Stack

**Frontend** React · TypeScript · Next.js · Vite · Capacitor · Tailwind
**Backend** Node.js · Express · NestJS · Python · FastAPI
**Data** MongoDB · PostgreSQL · Redis · pandas · TensorFlow
**Infra** Kubernetes · Docker · GitHub Actions · AWS · GCP
**Web3** Solidity · TON · Kaia · ethers
**AI** Claude · GPT · LangChain · MCP servers · agent pipelines

---

<details>
<summary><b>🇰🇷 한국어</b></summary>

<br>

## 김선우 — 풀스택 엔지니어 / CTO (12년차)

**빠르게 만드는 사람은 많아졌습니다. 저는 그렇게 만든 것을 실제로 운영해서 무너뜨리지 않은 사람입니다.**

화면을 뽑는 것과 아키텍처를 설계하는 것은 다릅니다.
저는 5개 마이크로서비스를 직접 설계해 쿠버네티스에 무중단 배포하고, 지금도 운영하고 있습니다.

### 제가 남들과 다른 지점

**기술 깊이 — 얕게 넓은 게 아니라 깊게 넓습니다**
이베이코리아에서 운영 중인 커머스의 레거시(JSP/jQuery/.NET) 화면을 React SPA로 이관하는 작업을 리드했습니다. 페이지 로드 60% 개선, DB 부하 40% 감소, 기존 동작은 그대로.

**0→1 — 빠른데 설계가 있습니다**
기획도 디자인도 없는 상태에서 외주로 받아 커머스+커뮤니티 MVP를 완주했습니다. 회원·권한, 결제, 포인트, 추첨 엔진, 커뮤니티, 어드민까지 프론트와 백엔드 전부.

**디자이너 없이 만듭니다 — 단, "AI 티 나는 UI"가 아닙니다**
AI 코딩 도구가 만드는 어색한 UI를 고치기 위해, **디자인 판단 기준 자체를 시스템으로 만들어 오픈소스로 공개**했습니다. 74개 룰, 48개 컴포넌트. 그 위에서 작업합니다.

**인프라가 버팁니다**
쿠버네티스 무중단 배포, CI/CD, Saga 패턴 이벤트 드리븐 오케스트레이션. 데모가 아니라 오늘도 돌고 있습니다.

**AI를 파이프라인으로 씁니다**
수집 → 분석 → 렌더 → 발행 패키지 생성까지 에이전트가 자동으로 돌리되, **발행은 사람이 결정**하는 구조로 설계합니다.

### 주요 프로젝트

**Oildealer — 에스크로 결제까지 갖춘 B2B 역경매 플랫폼** (혼자 구축, 양대 스토어 운영 중)
서비스가 필요로 하는 거의 모든 것이 한 프로젝트에: **역경매 · 에스크로 · 커뮤니티 · ML 유가예측 · 모니터링 · 웹주문 · 고객앱 · 벤더앱 · 어드민**.
고객용(웹 전용·앱 전용)·벤더용·관리자용 **3종 앱을 전부 단독 개발**해 iOS·Android **양대 스토어에 정식 출시·운영 중**(심사·반려 대응·버전 배포까지 혼자). 5개 마이크로서비스를 쿠버네티스 무중단 운영. MongoDB Time Series + Redis, Playwright 시장 데이터 파이프라인, GPT-4o 뉴스 에이전트. 자체 LSTM 가격 예측 **MAPE 0.74% · 방향 정확도 88%** (GARCH·VAR·VECM·XGBoost 대비 우위). 주유소 POS·탱크 센서 동기화 Windows 에이전트. **디자이너 0명.**

**트랜잭션 포워딩 API — LINE × Kaia**
Redis + 메시지 큐로 트랜잭션 전송을 서비스 로직에서 분리. 체인을 직접 때리는 대신 큐에 적재해 nonce 충돌과 레이트리밋을 회피하고, 재시도·백오프·실패 재처리 경로를 확보. **게임 유저 30만, 피크 100+ TPS.**

**NNN — 텔레그램 × TON 게임파이 런치패드**
런치패드 백엔드(레이어 분리), TON 스마트컨트랙트, 텔레그램 미니앱 프론트, 파트너 게임 연동 API. 확률 테이블을 코드 밖으로 뺀 미스터리박스 엔진, 주간 리워드 자동 분배(실패 시 리커버리 경로 포함). 파트너 게임 신규 통합을 1일 내로 단축.

**MARKET WHY — AI 나레이션 영상 자동 제작 파이프라인**
대본 → TTS(SSML 제어) → **음성 실제 길이에 맞춰 씬 타이밍 자동 계산** → 자막 → 썸네일 → 발행 패키지. 타임라인에서 눈으로 맞추는 게 아니라 음성 길이가 화면 길이를 결정합니다. 대본이 바뀌어도 재렌더만 하면 싱크가 유지됩니다.

### 경력
- **YayPlanet** Co-Founder (2025.12~)
- **YAYLABS** CTO & Co-Founder (2022.05~)
- **삼성카드** 프론트엔드 CL3 — 신규 서비스 Vue/Nuxt 아키텍처 (2021.12~2022.05)
- **eBay Korea** 소프트웨어 엔지니어 — 스마일클럽, 레거시→React SPA 이관 리드 (2017.07~2022.05)
- 전문연구요원 — 침입감내 시스템 연구 (2014.01~2017.02)

**한양대학교 컴퓨터공학 석사** (컴퓨터네트워크보안연구실)

</details>
